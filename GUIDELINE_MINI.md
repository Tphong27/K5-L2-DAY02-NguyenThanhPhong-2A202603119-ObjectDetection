# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp     | Định nghĩa của bạn                                                                                       | Ví dụ/điểm phân biệt                                                                                                               |
| ------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `car`   | Xe con thông thường chở người, gồm sedan, hatchback, SUV, xe bán tải/cabin nhỏ. Xe đang đỗ vẫn là `car`. | Phân biệt với `van`: `car` không có thùng/khoang dài kiểu xe van. Phân biệt với `truck`: xe bán tải cabin nhỏ vẫn là `car`.        |
| `truck` | Xe tải chở hàng và xe đầu kéo, có cabin tách riêng với thùng hàng.                                       | Phân biệt với `car`: xe bán tải nhỏ không phải `truck`. Phân biệt với `van`: `truck` có thùng hàng riêng, `van` là thân liền khối. |
| `bus`   | Xe buýt và minibus chở khách, thân dài, nhiều cửa sổ dọc thân.                                           | Phân biệt với `van`: xe van chở người cỡ nhỏ thuộc `van`, không phải `bus`.                                                        |
| `van`   | Xe van, minivan chở hàng hoặc chở người, thân liền khối, nhỏ hơn `bus` và lớn hơn xe con thông thường.   | Phân biệt với `bus`: xe buýt lớn là `bus`. Phân biệt với `car`: xe con thông thường là `car`.                                      |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: các cạnh box chạm vào phần thân xe nhìn thấy được, không lấy thêm mặt đường, bầu trời hay xe bên cạnh, và không cắt mất một phần xe. Mỗi xe có đúng một box riêng, kể cả khi cùng lớp.
- Vật thể bị che khuất: vẫn gán box quanh phần nhìn thấy được nếu nhận ra được lớp. Hai xe chồng lên nhau thì vẽ hai box riêng trên phần nhìn thấy của từng xe.
- Vật thể bị cắt bởi rìa ảnh: box chạm đúng rìa ảnh, không đoán phần nằm ngoài ảnh.
- Vật thể rất nhỏ/mơ hồ: nếu nhìn thấy đủ để xác định chắc lớp thì gán; nếu chỉ còn mảnh rất nhỏ hoặc không chắc lớp thì không tự đoán, ghi lại vào bảng bên dưới và hỏi giảng viên.
- Không gán: người đi bộ, xe đạp, mô tô/xe máy, biển báo, đèn giao thông, xe phản chiếu trong kính/gương, hình xe trên bảng quảng cáo.
- Ảnh không có xe thuộc bốn lớp vẫn có file `.txt` rỗng.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh         | Tình huống                                                                                                                                                                                                                                    | Quyết định cuối                                                            | Lý do theo schema                                                                                                                                                                      |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `drive_024` | Xe tối màu ở góc trên bên phải, rất nhỏ vì ở xa camera. Phần dưới bị xe phía trước che, nên không thấy rõ phần đuôi và chiều cao khoang sau. Hình dáng khó phân biệt giữa `car` và `van`.                                                     | Giữ `van`, box ôm phần thân nhìn thấy.                                     | Xe thân liền khối, nhỏ hơn `bus`, còn xe con thông thường là `car`. Với độ phân giải và phần bị che hiện có, chưa đủ dấu hiệu để loại trừ `van`, nên giữ nhãn `van` đã chọn lúc duyệt. |
| `drive_035` | Xe màu bạc đỗ sát lề ngay sau mái che trạm xe buýt, ở phía bên trái ảnh. Một cột trạm chờ che dọc thân xe, và vài người đứng phía trước che thêm phần dưới. Ảnh độ phân giải thấp, hơi mờ; box khoảng 67.6×60.3 px nên ranh giới xe không rõ. | Giữ `car`, một box ôm phần xe nhìn thấy (gồm cả vùng bị cột và người che). | Xe bị che một phần vẫn gán box quanh phần nhìn thấy nếu nhận ra được lớp. Hình dáng thân, kính và bánh xe đủ để xác định là xe con. Xe đang đỗ vẫn là `car`.                           |
| `drive_047` | Xe màu bạc ở sát mép trái ảnh, bị cắt một phần bởi rìa khung nên không thấy trọn phần đầu/đuôi xe. Thân xe liền khối, mui cao, hai hàng cửa sổ, hình dáng giống minivan, nhưng cũng có thể bị nhầm với `car` (xe con cỡ lớn).                 | Giữ `van`, một box ôm phần xe nhìn thấy, cạnh trái chạm đúng rìa ảnh.      | Thân liền khối, nhỏ hơn `bus`, lớn hơn xe con thông thường. Hình dáng cao, khoang hành khách dài liền khối phù hợp với `van` hơn `car`.                                                |
