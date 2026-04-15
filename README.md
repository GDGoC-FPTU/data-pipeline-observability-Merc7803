[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23572433&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.haitl@vinuni.edu.vn
**Name:** Trần Long Hải

---

## Mo ta

Bài lab này xây dựng một pipeline ETL đơn giản để đọc dữ liệu từ `raw_data.json`, kiểm tra chất lượng, chuẩn hóa các trường và lưu kết quả ra `processed_data.csv`.

Pipeline thực hiện:
- Extract: đọc dữ liệu JSON từ file
- Validate: bỏ các record không hợp lệ như giá <= 0 hoặc category trống
- Transform: chuẩn hóa category sang Title Case và thêm thời gian `processed_at`
- Load: lưu DataFrame ra CSV để sử dụng cho phân tích và mô phỏng agent

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Tổng số record đầu vào: 5
- Số record hợp lệ được giữ lại: 3
- Số record bị loại: 2
- Lý do loại: một record có giá âm / giá <= 0 và một record có category trống
- File đầu ra: `processed_data.csv` chứa 3 record đã được làm sạch và chuẩn hóa với cột `processed_at`.
