# Bài tập 6: Hệ quản trị CSDL
Chủ đề: Câu lệnh Select
Yêu cầu bài tập: 
Cho file sv_tnut.sql (1.6MB)
1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server của em
2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)
3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
6. nhập sql để tìm xem có những sv nào trùng tên với em?
7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.
9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)

DEADLINE: 23H59:59 NGÀY 25/4/2025

Ghi chú: Giải thích tại sao lại có SQL như vậy.
# Bài làm  
## 1. Các bước để import dữ liệu trong sv_tnut.sql  
- Kết nối vào sql server vào phần file >> open >> files    
![{3523081A-CDFE-48FC-83A8-90B278D041A5}](https://github.com/user-attachments/assets/d061e1b1-ee71-4bb2-827c-c92bb890ec10)
- Chọn file mà mình cần import  
![{A4858F34-94E2-4F44-8032-1E5ABBD8BBFE}](https://github.com/user-attachments/assets/431513a3-a60f-4704-bc47-2dc3ddf39390)
- Sau khi import file ta có  
![{8DDD46CD-70D5-424D-93F6-4F17AA5A8E77}](https://github.com/user-attachments/assets/bd4ab957-4c6a-471d-b705-dbc413749d8d)
## 2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)  
![1](https://github.com/user-attachments/assets/d1956d43-14b0-4c52-a647-8ff3fe146586)
## 3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?  
![{934B4588-E508-47E6-949D-8EC6186F70B2}](https://github.com/user-attachments/assets/8d009625-779e-4fe5-9580-dd2d83538451)
## 4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?  
- sử dụng câu lệnh Where với hàm Day và Month để truy xuất thông tin về ngày sinh và tháng sinh:  
![{4965D78F-FD03-4979-8CC1-FB38C784403B}](https://github.com/user-attachments/assets/947921db-51d1-4256-9870-14c571933309)
## 5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?  
![1](https://github.com/user-attachments/assets/c8f46ce9-f96e-4a23-b66a-0edd069a1700)
## 6. nhập sql để tìm xem có những sv nào trùng tên với em?  
![1](https://github.com/user-attachments/assets/ee236786-62e8-4c8f-8148-8b9122c585ed)
## 7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
![{A2382C47-F5FF-4CEF-91AF-9FD5451F3736}](https://github.com/user-attachments/assets/87fab6ba-bab9-48eb-aed4-1c3aa40a3533)
## 8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.  
![{4CC047BF-C5E7-4ABC-922D-AB12220CC682}](https://github.com/user-attachments/assets/36cb52df-948f-4dad-97bb-79c200182d88)
```
Where (
    (CASE WHEN SUBSTRING(sdt,1,1) <> SUBSTRING('0363650618',1,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,2,1) <> SUBSTRING('0363650618',2,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,3,1) <> SUBSTRING('0363650618',3,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,4,1) <> SUBSTRING('0363650618',4,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,5,1) <> SUBSTRING('0363650618',5,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,6,1) <> SUBSTRING('0363650618',6,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,7,1) <> SUBSTRING('0363650618',7,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,8,1) <> SUBSTRING('0363650618',8,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,9,1) <> SUBSTRING('0363650618',9,1) THEN 1 ELSE 0 END +
     CASE WHEN SUBSTRING(sdt,10,1) <> SUBSTRING('0363650618',10,1) THEN 1 ELSE 0 END)
) = 1
```
- Dòng lệnh được dùng để so sánh từng con số trong sđt của em và xuất ra dữ liệu ta cần và có vẻ không có ai có sdt gần trùng với en :((
## 9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.  
```
WHERE lop LIKE '%KTP%'
```
Được dùng để lọc các sinh viên có lớp có chứa từ KTP  
```
ORDER BY 
    ten COLLATE Vietnamese_CI_AS, 
    hodem COLLATE Vietnamese_CI_AS;
```
Được dùng để sắp xếp tên và họ theo cột và chuẩn tiếng việt  
![{EAD422C4-33E6-415D-BFB6-4E3BAF6F1223}](https://github.com/user-attachments/assets/c15415d2-3593-4f25-a26b-4876096d74e5)
## 10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)
- Theo em thấy vì bài toán csdl trong file sv_tnut.sql của thầy chưa cho em trường thuộc tính "Giới tính" nên việc xác định các SV nữ trong ngành KTP là 1 việc bất khả thi, trừ khi em mò từng sv trong nganh và gán giới tính cho họ nhưng việc đó cũng quá mất thời gian, vậy nên để giải được yêu cầu này của thầy thì em cần phải xin thầy 1 file excel hay file csdl mới có đầy đủ các trường thuộc tính để import vào sql và chạy. Em cảm ơn thầy đã xem bài của em.
# Giải thích
Bài tập SQL được thiết kế dựa trên mô phỏng thực tế trong việc quản lý sinh viên tuy vậy thầy đang lược bỏ mất thuộc tính giới tính em câu 10 em chịu không làm được thầy ạ.
