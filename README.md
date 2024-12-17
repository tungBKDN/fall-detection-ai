# Hướng dẫn cài đặt và chạy chương trình step-by-step

## Folder Dataset

- Các folder ADL và Falling là dữ liệu gốc nhóm tự thu thập được, trong đó có 7 kiểu hành động ADL (Activities of Daily Living) và 6 kiểu hành động ngã (Falling).

- Folder LongData chứa dữ liệu có thời gian dài do nhóm tự thu thập được, trong đó có các mẫu chứa 2 đến 3 hành động ngã tại các thời điểm khác nhau.

- Folder SplittedLongData chứa các frame có độ dài 1 giây được tách ra từ các mẫu thu thập được ở LongData.

- File dataset_raw.csv chứa các feature vector tương ứng với mỗi mẫu dữ liệu có trong hai folder ADL và Falling.

- File dataset_extract.csv chứa các feature vector sau quá trình feature selection (vector đặc trưng 22 chiều).

## File best_model.joblib và best_model.pkl

Đây là hai file chứa model sau quá trình khảo sát tham số, được dùng để nhúng vào Jetson Nano (chỉ file pkl là nhúng được)

## File SVM_model.ipynb là file huấn luyện model chính dùng SVM 

- Trong chương trình có chú thích từng đoạn code làm gì, chạy từ trên xuống.
- Những đoạn code được đánh 4 dấu * (****) và dùng lần đầu thì không chạy (nếu đã có file dataset_extract.csv)
- Cần lưu thư muc Dataset vào Drive (do nhóm chạy chương trình bằng colab), nếu không, phải thay đổi đường dẫn thư mục đến các file trong folder Dataset.
- Quá trình lựa chọn đặc trưng thông qua trực quan hóa dữ liệu thể hiện ở file Visualization.ipynb (chưa đầy đủ)

## File SVM_Embedded là code gọi model xử lý dữ liệu thu được ở Jetson (bên phần cứng cần điều chỉnh lại kiểu dữ liệu truyền vào hàm)
