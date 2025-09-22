Bộ dữ liệu apache thường xuyên được sử dụng để thực hành, thử nghiệm trong software defection prediction, các paper được nghiên cứu hiện tại được hướng đến trong việc đẩy cao performance của mô hình bao gồm: machine learning, deep learning và hứu hẹn trong tương lai với sự nâng cấp của NLP.
Bộ dữ liệu apache bao gồm các file csv thống kê từ các đoạn code java, dataset cung cấp để huấn luyện mô hình phát hiện(detect) các lỗi tiềm ẩn(defection) trong đoạn ode, nhằm xử lí cho các version code được cập nhật mới trong tương lai.
Các model cho thấy kết quả từ ổn đến tốt:
- Stacking: kết hợp base model và meta model
- Ensemble các model(voting)
- Random Forest

Đối với riêng bộ Promise thì gồm các projects, mỗi project gồm nhiều version, version sau được cập nhật thêm nhiều hơn version trước, nên sẽ có 2 việc cần chú ý là train cross và train within.

Vấn đề chung của hầu hết toàn bộ bộ dữ liệu là:
- Dữ liệu chưa được chuẩn hóa
- Bộ Promise cung cấp các samples có 20 features trong đó rất nhiều features gây nhiễu mô hình
- Dữ liệu bị mất cân bằng nặng, trong hàng nghàn đoạn code thì chỉ có vài đoạn có bug
- Phân bố dữ liệu trong tập train và test khi train cross khác nhau

Các giải pháp:
1. Chuẩn hóa dữ liệu bằng minmaxscaler
2. SelectKBest features, đánh giá feature bằng trọng số
3. Smote để oversampling dữ liệu( có thể bootstrapping)
4. ORAL (paper 2019 lụm được) ( nhưng chưa tối ưu nên chưa áp dụng với model ML)

LƯU Ý: FILE ĐI KÈM BAO GỒM FILE SOURCE CODE CỦA TỪNG ĐOẠN SAMPLE, VỚI MODEL ML THÌ SẼ THỰC HIỆN TRÊN CÁC FILE CSV, SOURCE CODE ĐỂ CẢI THIỆN THÊM VỚI MODEL DEEP LEARNING.
LINK GITHUB PROMISE BACKUP MASTER ĐỂ LẤY SOURCE CODE: https://github.com/feiwww/PROMISE-backup/tree/master
GOOGLE SHEET KẾT QUẢ(đang cập nhật thêm) :https://docs.google.com/spreadsheets/d/1iaPVsiFAdF1dfd2IqVaMOMt2Dn56KREwVhsmhuCpw2w/edit?usp=sharing
