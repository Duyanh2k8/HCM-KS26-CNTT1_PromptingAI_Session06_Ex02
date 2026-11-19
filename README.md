# [Phân tích] So sánh Trade-off các giải pháp ra lệnh cho Ứng dụng AI trong Học tập & Nghiên cứu
## 1. Mục tiêu
Đề xuất hai cách viết Prompt để xây dựng AI gia sư theo phương pháp Feynman và tự động chấm bài dựa trên Rubric. Sau đó so sánh ưu, nhược điểm để chọn ra phương án phù hợp nhất.
## 2. Bước 1: Đề xuất 2 Prompt mẫu
**Giải pháp 1: Prompt đơn giản**
```text
Bạn là AI gia sư hỗ trợ học tập.

Hãy sử dụng phương pháp Feynman để giúp tôi hiểu bài bằng cách giải thích kiến thức đơn giản, dễ hiểu và đưa ra ví dụ thực tế.

Sau khi tôi trình bày lại kiến thức, hãy sử dụng Rubric để chấm điểm theo thang 10, nhận xét ưu điểm, chỉ ra lỗi sai và đề xuất cách cải thiện.

Trình bày ngắn gọn, dễ hiểu.
```
**Giải pháp 2: Prompt chi tiết**
```text
[CONTEXT]
Tôi đang sử dụng AI để hỗ trợ học tập và nghiên cứu.

[ROLE]
Bạn là AI gia sư có kinh nghiệm giảng dạy và đánh giá kiến thức.

[TASK]
Thực hiện quy trình học tập theo phương pháp Feynman gồm:

1. Giải thích: Giải thích kiến thức bằng ngôn ngữ đơn giản, kèm ví dụ thực tế.
2. Kiểm tra: Đặt 3 câu hỏi để kiểm tra mức độ hiểu bài.
3. Đánh giá: Yêu cầu tôi tự giải thích lại kiến thức bằng lời của mình.
4. Chấm điểm: Sử dụng Rubric để đánh giá phần trình bày.

[RUBRIC]
- Độ chính xác kiến thức: 4 điểm.
- Khả năng giải thích: 3 điểm.
- Ví dụ minh họa: 2 điểm.
- Cách trình bày: 1 điểm.

[RULES]
- Tổng điểm tối đa là 10.
- Không tự ý cho điểm khi chưa có câu trả lời.
- Không đánh giá dựa trên độ dài câu trả lời.
- Nếu thiếu thông tin, hãy yêu cầu tôi bổ sung.
- Không tự bịa kiến thức hoặc kết quả đánh giá.
- Chỉ rõ nội dung sai và giải thích lý do.

[OUTPUT]
Trình bày kết quả theo bảng gồm:
Tiêu chí | Điểm đạt được | Nhận xét.

Cuối cùng, đưa ra tổng điểm và 3 gợi ý cải thiện.
```
## 3. Bước 2: Bảng so sánh Trade-off
|Tiêu chí|	Giải pháp 1 (Đơn giản)	|Giải pháp 2 (Chi tiết)|
|---|---|---|
|Độ dễ hiểu|	Cao	|Trung bình|
|Tốn Token|	Ít	|Nhiều hơn|
|Tốc độ phản hồi	|Nhanh|	Có thể chậm hơn|
|Độ chính xác|	Khá|	Cao hơn|
|Chặn lỗi biên	|Trung bình|	Tốt|
|Khả năng chấm điểm|	Cơ bản|	Có Rubric rõ ràng|
|Tính linh hoạt|	Cao	|Thấp hơn|
|Khả năng tái sử dụng|	Khá|	Cao|
## 4. Bước 3: Lựa chọn và chạy thử
**Phương án được chọn:** Giải pháp 2 (Prompt chi tiết).

Lý do lựa chọn:

Mặc dù tốn nhiều Token hơn nhưng giải pháp 2 có quy trình rõ ràng, tiêu chí chấm điểm cụ thể và hạn chế việc AI tự đưa ra kết quả thiếu căn cứ. Đặc biệt, AI có thể vừa hướng dẫn học vừa kiểm tra mức độ hiểu bài.

Chạy thử:
- Chủ đề: Bộ nhớ RAM trong máy tính.
- Yêu cầu: Giải thích RAM bằng phương pháp Feynman, sau đó kiểm tra kiến thức.
Kết quả chạy thử:

---
### 1. AI giải thích kiến thức
RAM là bộ nhớ tạm thời của máy tính, dùng để lưu dữ liệu và chương trình đang chạy. Khi tắt máy, dữ liệu trong RAM sẽ mất.

Ví dụ: Khi mở nhiều ứng dụng cùng lúc, RAM giúp máy tính xử lý các ứng dụng đó nhanh hơn.
### 2. AI đặt câu hỏi kiểm tra
- RAM dùng để làm gì?
- Điều gì xảy ra với dữ liệu trong RAM khi tắt máy?
- Vì sao máy tính cần RAM?
### 3. Kết quả chấm thử
Giả sử sinh viên trả lời đúng phần lớn kiến thức, giải thích được công dụng của RAM nhưng chưa có ví dụ thực tế rõ ràng.
|Tiêu chí|	Điểm|
|---|---|
|Độ chính xác kiến thức|	3.5/4|
|Khả năng giải thích|	2.5/3|
|Ví dụ minh họa|	1/2|
|Cách trình bày|	1/1|
|Tổng điểm	|8/10|
---
