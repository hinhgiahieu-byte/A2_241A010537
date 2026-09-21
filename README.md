BÁO CÁO LAB A2 – QUẢN LÝ VÒNG ĐỜI ACTIVITY
1. Thông tin sinh viên  
Họ tên: Huỳnh Ngọc Hiếu  
MSSV: 241A010541  
Lớp: K26  
Thiết bị: Pixel 7 Emulator – Android API 37  
2. Ứng dụng Stopwatch

Ứng dụng có các chức năng:

Bắt đầu / Tạm dừng.  
Đặt lại thời gian.  
Hiển thị thời gian Stopwatch.  
Lưu và khôi phục trạng thái Activity.  
Quản lý Handler và vòng đời Activity.  

<img width="1917" height="1078" alt="Ảnh chụp màn hình 2026-09-20 012432" src="https://github.com/user-attachments/assets/2eced990-e601-49ea-96a4-2e05ab3d5c40" />

Hình 1. Giao diện ứng dụng Stopwatch.

3. Kiểm thử 5 kịch bản
STT	Kịch bản	Kết quả  
1	Xoay màn hình	Thời gian không bị reset  
2	Home, chờ 10 giây, mở lại	Thời gian được duy trì  
3	Tạm dừng rồi xoay	Thời gian và trạng thái được giữ  
4	Bật Don't keep activities	Activity tạo lại nhưng trạng thái được khôi phục  
5	Back thoát, mở lại	Stopwatch trở về 00:00.0  

 <img width="1907" height="1078" alt="Ảnh chụp màn hình 2026-09-20 012505" src="https://github.com/user-attachments/assets/49a76c40-2348-4324-811f-fe2da969bb66" />

Hình 2. Kết quả Home, chờ 10 giây, mở lại	Thời gian được duy trì.  


<img width="1912" height="1071" alt="Ảnh chụp màn hình 2026-09-20 102719" src="https://github.com/user-attachments/assets/4ac37464-df6d-4915-beb5-21fdf61ea436" />
<img width="1917" height="1078" alt="Ảnh chụp màn hình 2026-09-20 102728" src="https://github.com/user-attachments/assets/236a5d07-d65b-41ee-bcc7-0a67d9b46de2" />

<img width="1917" height="1077" alt="Ảnh chụp màn hình 2026-09-20 102735" src="https://github.com/user-attachments/assets/d7d2afcd-4bf0-46b1-96ea-47f18f031e6d" />
Hình 3. Kết quả xoay màn hình	Thời gian không bị reset  



<img width="1917" height="1078" alt="Ảnh chụp màn hình 2026-09-20 012823" src="https://github.com/user-attachments/assets/fd60c1ba-e975-4e66-a87f-9dbc6a1ef535" />
Hình 4. Kết quả tạm dừng rồi xoay	Thời gian và trạng thái được giữ.  
<img width="633" height="1035" alt="Ảnh chụp màn hình 2026-09-20 104501" src="https://github.com/user-attachments/assets/035a0a28-ebe8-412c-866e-b3384dfda081" />
<img width="615" height="1077" alt="Ảnh chụp màn hình 2026-09-20 104509" src="https://github.com/user-attachments/assets/3f3342f3-5c49-4c4b-af4d-36f20a6943e0" />
<img width="535" height="977" alt="Ảnh chụp màn hình 2026-09-20 104535" src="https://github.com/user-attachments/assets/237165be-a6bc-4cad-a8e1-4b4ac2cfa962" />

Hình 5. Kết quả Back thoát, mở lại	Stopwatch trở về 00:00.0 
4. Logcat – Kịch bản 4

Logcat dùng để kiểm tra vòng đời Activity và quá trình lưu/khôi phục trạng thái.
<img width="1857" height="380" alt="Ảnh chụp màn hình 2026-09-20 104828" src="https://github.com/user-attachments/assets/5f085dc9-8549-4487-be92-92f86217f0cb" />

Hình 6. Logcat thể hiện onSaveInstanceState và khôi phục trạng thái trong onCreate.

5. Trả lời câu hỏi phân tích

Câu 1: Kịch bản 4 khôi phục được trạng thái vì Android lưu trạng thái bằng onSaveInstanceState(). Kịch bản 5 thoát hoàn toàn nên mở lại Activity mới và thời gian trở về 00:00.0.

Câu 2: Nếu bỏ stopTicking() trong onPause(), Handler có thể tiếp tục cập nhật không cần thiết, gây tốn CPU và pin.

Câu 3: Nếu chỉ tăng biến đếm mỗi 100 ms, khi ứng dụng xuống nền có thể bị thiếu thời gian vì các lần cập nhật không chạy liên tục.

Câu 4: onPause() dùng để xử lý khi Activity mất trạng thái tương tác; onSaveInstanceState() dùng để lưu trạng thái tạm thời nhằm khôi phục Activity.

6. GitHub
Repository: Private
Số commit: ≥ 3
Có .gitignore
Đã thực hiện quản lý mã nguồn bằng Git/GitHub.

<img width="1855" height="380" alt="Ảnh chụp màn hình 2026-09-20 135948" src="https://github.com/user-attachments/assets/546057cb-26e8-4775-88e0-f819ec5c505d" />



Hình 4. Git Log của project với ít nhất 3 commits.

<img width="502" height="406" alt="image" src="https://github.com/user-attachments/assets/b6e3ec66-8e77-4cab-b37d-b3c964155be1" />


Hình 5. Repository Lab A2 trên GitHub.

Link Repository: https://github.com/hinhgiahieu-byte/A2_241A010537.git

7. Phần nâng cao

Chọn 2 nội dung: NC1 và NC2.

NC1 – Nút Vòng (Lap)

Thêm nút Lap để lưu và hiển thị các mốc thời gian trong quá trình chạy Stopwatch.

<img width="555" height="863" alt="Ảnh chụp màn hình 2026-09-21 222930" src="https://github.com/user-attachments/assets/27958387-91b6-4f2d-a654-1c4fd3fc87a2" />

NC2 – Dừng khi ra nền

Thêm Checkbox “Dừng khi ra nền”. Khi được chọn, Stopwatch sẽ tạm dừng khi ứng dụng chuyển xuống nền và trạng thái Checkbox được lưu khi Activity tạo lại.

<img width="482" height="918" alt="Ảnh chụp màn hình 2026-09-21 223456" src="https://github.com/user-attachments/assets/f879c94d-9f83-4873-8dff-bf2653e7c69d" />
<img width="465" height="853" alt="Ảnh chụp màn hình 2026-09-21 223601" src="https://github.com/user-attachments/assets/cbe971a6-31cc-422b-8a6b-d8eb725a88db" />
<img width="456" height="932" alt="Ảnh chụp màn hình 2026-09-21 223552" src="https://github.com/user-attachments/assets/cafddb71-6d9d-4d1a-a59c-fc5b65dae6c8" />

8. Kết luận

Hoàn thành ứng dụng Stopwatch, kiểm thử vòng đời Activity, lưu/khôi phục trạng thái, kiểm tra Logcat và quản lý mã nguồn bằng Git/GitHub.
