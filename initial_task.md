# 🎮 CodeAlpha_Steam_Analytics

![CodeAlpha Badge](https://img.shields.io/badge/Internship-CodeAlpha-blue)
![Data Analytics](https://img.shields.io/badge/Domain-Data_Analytics-success)
![Python](https://img.shields.io/badge/Python-3.9+-yellow)

## 📌 Project Overview
[cite_start]Dự án này được thực hiện trong khuôn khổ chương trình thực tập Data Analytics tại CodeAlpha[cite: 1, 2]. Mục tiêu của dự án là xây dựng một luồng dữ liệu (End-to-End Data Pipeline) hoàn chỉnh nhằm phân tích thông tin và đánh giá của người dùng trên nền tảng Steam. 

[cite_start]Dự án bao trùm toàn bộ vòng đời dữ liệu, từ việc thu thập tự động (Web Scraping) [cite: 23][cite_start], làm sạch và khám phá dữ liệu (EDA) [cite: 30][cite_start], trực quan hóa (Data Visualization) [cite: 34][cite_start], cho đến ứng dụng NLP để phân tích cảm xúc (Sentiment Analysis)[cite: 39, 42].

**Chủ đề phân tích (Topic):** Đánh giá trải nghiệm người chơi đối với các tựa game nổi bật trên Steam (Ví dụ: Tập trung phân tích chuyên sâu dữ liệu review của series *Resident Evil* hoặc Top 100 game thịnh hành).

---

## 🛠️ Tech Stack & Môi trường
* **Ngôn ngữ:** Python
* [cite_start]**Thu thập dữ liệu (Task 1):** `requests`, `BeautifulSoup`[cite: 24], Steam Store API
* **Xử lý & Khám phá dữ liệu (Task 2):** `pandas`, `numpy`
* [cite_start]**Trực quan hóa (Task 3):** `matplotlib`, `seaborn` [cite: 36]
* **Phân tích cảm xúc (Task 4):** `nltk` (VADER Sentiment), `re` (Regular Expressions)
* **Môi trường phát triển:** Jupyter Notebook, Git. Khuyến nghị chạy trên môi trường Linux (WSL2 trên Windows) hoặc macOS để tối ưu hóa quá trình xử lý văn bản và NLP.

---

## 🚀 Phương pháp thực hiện (Methodology)

### Task 1: Web Scraping (Thu thập dữ liệu)
* [cite_start]Sử dụng Python để gửi request và thu thập dữ liệu từ các trang công khai của Steam[cite: 24, 25].
* **Dữ liệu trích xuất:**
  * Thông tin Game: AppID, Tên, Thể loại (Tags), Nhà phát triển, Giá tiền.
  * Dữ liệu Text: Từ 500 - 1000 bình luận (reviews) của người dùng cho mỗi tựa game, kèm theo nhãn "Recommended" hoặc "Not Recommended".
* [cite_start]**Lưu ý:** Tùy chỉnh script xử lý cấu trúc HTML để lấy dữ liệu chính xác [cite: 27] và xuất ra file `steam_reviews.csv`.

### Task 2: Exploratory Data Analysis - EDA (Khám phá dữ liệu)
* [cite_start]Load dataset vừa tạo [cite: 28] [cite_start]vào Pandas Dataframe để kiểm tra cấu trúc dữ liệu và kiểu biến[cite: 31].
* Xử lý dữ liệu nhiễu (Missing values, bình luận rác/chứa ký tự đặc biệt).
* [cite_start]Phát hiện xu hướng và sự bất thường [cite: 32][cite_start]: Ví dụ như hiện tượng "Review Bombing" (nhận bão 1 sao trong thời gian ngắn) hoặc sự chênh lệch giữa giá trị game và đánh giá[cite: 33].

### Task 3: Data Visualization (Trực quan hóa dữ liệu)
* [cite_start]Chuyển đổi dữ liệu thô thành các biểu đồ trực quan [cite: 35] [cite_start]bằng Matplotlib và Seaborn[cite: 36].
* **Các biểu đồ chính:**
  * Bar Chart: Top các thể loại game được yêu thích nhất.
  * Scatter Plot: Tương quan giữa Giá tiền (Price) và Độ phổ biến (Total Reviews).
  * Word Cloud: Những từ khóa xuất hiện nhiều nhất trong các bình luận tích cực.
* [cite_start]Mục tiêu: Xây dựng các biểu đồ truyền tải thông điệp rõ ràng, hỗ trợ ra quyết định[cite: 36, 37].

### Task 4: Sentiment Analysis (Phân tích cảm xúc)
* [cite_start]Áp dụng kỹ thuật Xử lý ngôn ngữ tự nhiên (NLP) [cite: 42] trên cột chứa nội dung bình luận (text data).
* [cite_start]Sử dụng VADER Sentiment Lexicon [cite: 42] [cite_start]để tính điểm số phân cực (Polarity Score) cho từng câu, từ đó phân loại bình luận thành Tích cực (Positive), Tiêu cực (Negative), hoặc Trung tính (Neutral)[cite: 41].
* [cite_start]So sánh kết quả phân loại của mô hình NLP với nhãn đánh giá thực tế của người dùng Steam để đánh giá độ chính xác và hiểu rõ hơn về ý kiến công chúng[cite: 44].

---

## 📂 Cấu trúc Repository
Dự án được tổ chức theo tiêu chuẩn như sau:

```text
CodeAlpha_Steam_Analytics/
│
├── data/                       # Chứa dữ liệu đầu vào và đầu ra
│   ├── raw_steam_data.csv      # Dữ liệu gốc thu thập từ Task 1
│   └── clean_steam_data.csv    # Dữ liệu sau khi qua EDA (Task 2)
│
├── notebooks/                  # Chứa mã nguồn cho từng Task
│   ├── 01_web_scraping.ipynb
│   ├── 02_eda_analysis.ipynb
│   ├── 03_visualization.ipynb
│   └── 04_sentiment_analysis.ipynb
│
├── README.md                   # Tổng quan dự án
└── requirements.txt            # Danh sách thư viện Python cần thiết