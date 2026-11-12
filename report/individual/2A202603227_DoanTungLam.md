# Báo cáo thực hành Day 3 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên [LMS](https://aithucchien.vinuni.edu.vn). Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](../../reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202603227
- Ngày / CVAT local: 11/11/2026
- Công cụ đã dùng: Brush/Polygon; có hỗ trợ AI (Claude)

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task            | File ZIP đúng tên   | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --------------- | ------------------- | -----------------: | ---------------------------: |
| easy_semantic   | easy_semantic.zip   |              3 / 3 |                           20 |
| medium_instance | medium_instance.zip |              3 / 3 |                           32 |
| hard_panoptic   | hard_panoptic.zip   |              2 / 2 |                           30 |
| cp1_holes       | cp1_holes.zip       |              1 / 1 |                            3 |
| cp2_slice       | cp2_slice.zip       |              1 / 1 |                            3 |
| cp5_occlusion   | cp3_thin.zip        |              1 / 1 |                            3 |
| cp3_thin        | cp4_curb.zip        |              1 / 1 |                            3 |
| cp4_curb        | cp5_occlusion.zip   |              1 / 1 |                            3 |
| cp6_coverage    | cp6_coverage.zip    |              1 / 1 |                            3 |
| **Tổng tối đa** |                     |            14 / 14 |                      **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: Ảnh 1 (`000000181542.jpg`), chiếc xe máy ở góc dưới bên phải, là xe gần camera nhất, bánh sau lớn và hơi mờ do chuyển động. Được vẽ bằng công cụ Brush (object #5, class `motorcycle`)
- Class và quy tắc dùng để chọn biên: Class `motorcycle`. Tô theo mép nhìn thấy của thân xe và bánh trước. Dừng mask ở chỗ chân và thân người lái đè lên xe, vì phần bị che đó thuộc class `person`, không thuộc `motorcycle`. Mỗi xe là một instance riêng, nên không gộp xe này với chiếc xe phía sau
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: không dùng
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng: `medium_instance`, ảnh 1 (`000000181542.jpg`), nhóm xe máy ở giữa và bên trái ảnh, ngay dưới các người lái xe
- Lỗi thuộc loại: Thiếu vật (một xe máy có trong ảnh nhưng chưa có polygon).
- Bằng chứng tôi nhìn thấy: Khi vẽ xong, đối chiếu danh sách object ở bảng bên phải với ảnh. Trong ảnh có 5 chiếc xe máy, nhưng danh sách chỉ có 4 object `motorcycle`
- Quy tắc và hành động sửa: chưa sửa
- Sau sửa đã Save và export lại chưa? chưa sửa

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): … / chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

|     | Ảnh/vị trí                                                                                          | Hai cách hiểu có thể                                                                           | Quy tắc/chứng cứ                                                                                                             | Quyết định hoặc câu hỏi cho coach                                                                                                                       |
| --- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | `hard_panoptic`, ảnh 2 (`000000460147.jpg`), xe tải chở ô tô ở giữa ảnh                             | (a) Các ô tô chở trên xe tải là một phần của `truck`; (b) mỗi ô tô là một instance `car` riêng | Nhìn thấy rõ hình dạng từng ô tô (kính, đèn, bánh xe) trên hai tầng sàn xe. Quy tắc: vật đếm được, nhìn rõ thì tách instance | Đã vẽ 3 ô tô là `car` riêng, đè lên polygon `truck`                |
| 2   | `hard_panoptic`, ảnh 1 (`000000350023.jpg`), dải phân cách màu nâu giữa hai chiều đường, có bồn cây | (a) Dải phân cách là `road`; (b) là `sidewalk` vì cao hơn mặt đường, không phải làn xe chạy    | Dải có màu và vật liệu khác mặt nhựa nhưng không có người đi bộ. Bồn cây trên dải có lá xanh rõ                              | Đã gán dải phân cách là `road`, riêng bồn cây là `vegetation`                        |
| 3   | `medium_instance`, ảnh 3 (`000000458325.jpg`), hàng ô tô đậu sát nhau hai bên đường                 | (a) Mỗi xe đậu là một instance riêng; (b) gộp các xe ở xa bị che khuất thành một vùng          | Các xe gần nhìn rõ ranh giới. Xe ở xa nhỏ và chồng lên nhau, khó thấy đâu là xe sau                                          | Đã tách từng xe nhìn rõ thành instance `car` riêng, biên dừng ở chỗ xe trước che xe sau. Bỏ qua vài xe quá nhỏ ở cuối đường vì không xác định được biên |
