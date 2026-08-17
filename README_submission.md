# Submission Report - Lab 17: Multi-Memory Agent

## 1. Phân tích Benchmark

* **Layer có hit rate thấp nhất:** Ở baseline `no_memory`, cả 3 tầng **Long-term, Episodic, Semantic** đều đạt **0% hit rate** (FAIL 9/11 case: E02–E09, E11) do không lưu context cross-session. Với `student`, cả 4 tầng đều đạt **100% hit rate (11/11 PASS)**.
* **Query retrieve nhiều token nhất:** Case **`E07`** (Mixed query: code retry payment theo preference của Minh) tiêu tốn **485 tokens** (sau khi budget gộp 324 tokens long-term + 148 tokens semantic).
* **Case E07:** Cần kết hợp **Long-term Memory** (user preference) và **Semantic Memory** (domain policy). Hai evidence bắt buộc là: `Python` và `Idempotency-Key`.
* **Token reduction:** Đạt trung bình **14.2%** với Memory-enabled (giảm tải token nhưng giữ đủ 100% evidence). Baseline `no_memory` có reduction cao (**81.8%**) chỉ vì nó không truy xuất được gì (0 token ở 9 case), dẫn đến hit rate rớt xuống **18.2% (2/11)**. Cắt giảm token chỉ có giá trị khi đi kèm độ chính xác evidence.

---

## 2. Reflection Bắt Buộc

* **Layer quan trọng nhất:** **Long-term Memory** chiếm tỷ trọng lớn nhất (**4/11 cases**: E02, E03, E08, E09), là xương sống để agent duy trì identity, open loops, user isolation và giải quyết mâu thuẫn dữ liệu qua nhiều session.
* **Trade-off Zep Context Block vs Redis + Qdrant:** 
  * *Zep Cloud:* Tự động hóa graph indexing, temporal facts ranking, tự trích xuất và nén context thông minh, nhưng phụ thuộc độ trễ mạng (~1.9s) và cloud API.
  * *Redis + Qdrant:* Tốc độ siêu nhanh, kiểm soát 100% hạ tầng nhưng đòi hỏi chi phí bảo trì lớn và phải tự viết toàn bộ logic entity extraction, graph search và conflict resolution.
* **Guardrail chống Memory Poisoning:** Áp dụng **Opt-in Consent registry** (`consent.json`), khử khuẩn/ẩn danh hóa PII (email, phone) trước khi ingest, và quy định tiến trình nền (Heartbeat) chỉ chạy quyền Read-only/Dry-run, tuyệt đối không tự cấp quyền hay ghi đè System Prompt.
* **E08 Recency & E10 Compaction:** 
  * **E08 Recency:** Xử lý xung đột theo scope — với dự án công ty `BLUEBIRD-42`, fact mới nhất ghi đè sang `TypeScript/NestJS`, trong khi scope cá nhân `ORCHID-27` vẫn giữ `Python`.
  * **E10 Compaction:** Khi vượt ngưỡng token, hội thoại được nén thành summary nhưng trích xuất và bảo lưu nguyên vẹn ràng buộc bền vững `REVIEW-DEADLINE-1600` vào thẻ `<DURABLE_NOTES>`.
