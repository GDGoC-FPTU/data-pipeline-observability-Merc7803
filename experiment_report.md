# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600427
**Name:** Trần Long Hải
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 9 | Dữ liệu được làm sạch, category chuẩn hóa, giúp agent suy luận ổn định. |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 3 | Dữ liệu chứa giá không hợp lý, category trống và định dạng không đúng, gây nhiễu đầu vào. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Garbage data thường chứa nhiều vấn đề như giá trị sai kiểu, giá âm hoặc bằng 0, category trống và giá trị null. Khi agent nhận đầu vào này, nó phải dựa vào thông tin không đáng tin cậy, nên kết luận dễ bị lệch. Duplicate IDs có thể khiến hệ thống nhầm lẫn về sản phẩm nào thực sự cần phân tích. Wrong data types như chuỗi trong trường `price` cũng phá vỡ việc tính toán và so sánh.

Bên cạnh đó, outliers và giá trị cực đoan khiến mô hình giả định sai về phân phối dữ liệu. Null values và trường trống làm giảm khả năng agent hiểu ngữ cảnh đúng. Tóm lại, chất lượng dữ liệu kém làm suy giảm hiệu quả của cả prompt tốt nhất, vì mô hình đang làm việc với bằng chứng sai hoặc thiếu.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** 
Đồng ý. Một prompt tốt giúp hướng agent, nhưng nếu dữ liệu đầu vào bị sai lệch, thì kết quả vẫn không thể chính xác. Dữ liệu sạch, nhất quán và đầy đủ vẫn là yếu tố quan trọng nhất để đảm bảo AI đưa ra phản hồi hợp lý.
