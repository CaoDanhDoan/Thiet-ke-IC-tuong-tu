Thiết kế mạch Op-Amp sử dụng công nghệ CMOS
🎓 Giới thiệu
Đây là bài tập lớn môn học liên quan đến thiết kế vi mạch tương tự, với mục tiêu thiết kế và mô phỏng mạch khuếch đại thuật toán (Operational Amplifier – Op-Amp) bằng công nghệ CMOS, sử dụng công cụ Electric VLSI và LTspice.

🧠 Mục tiêu
Hiểu nguyên lý và cấu trúc ba tầng của mạch Op-Amp: khuếch đại vi sai, khuếch đại trung gian, và tầng đệm.

Thiết kế schematic và layout trên Electric VLSI.

Gán các tham số công nghệ, viết mã SPICE và mô phỏng AC, TRAN để đánh giá hiệu suất mạch.

Tối ưu layout để pass các kiểm tra DRC, LVS.

🧩 Cấu trúc mạch
Tầng 1 – Vi sai đầu vào:

Transistor: NMOS M5, M6; PMOS M1, M2, M3; NMOS M7

So sánh tín hiệu Vp và Vm, tạo ra tín hiệu vi sai khuếch đại đầu tiên

Tầng 2 – Khuếch đại trung gian:

Transistor: M13, M14, M15, M10–M12

Khuếch đại mạnh hơn tín hiệu và tạo dòng thiên ổn định

Tầng 3 – Đệm đầu ra:

Transistor: M18, M19, M20

Đảm bảo tín hiệu đầu ra đủ công suất kéo tải, giảm trở kháng

Khối Bias – Cấp dòng phân cực:

Mirror current sử dụng M7, M10–M12, M16–M17

Đảm bảo mạch hoạt động ổn định trong vùng bão hòa

🛠️ Công cụ sử dụng
Công cụ	Mục đích
Electric VLSI	Thiết kế schematic & layout
LTspice	Mô phỏng AC, TRAN
SPICE	Viết mô phỏng và kiểm tra tính đúng của mạch
DRC / LVS / ERC	Xác minh layout và schematic

📊 Kết quả mô phỏng
TRAN (.tran): Khi cấp Vp = Vm = 2.5V → Vout ổn định tại ~2.5015V.

AC (.ac dec 100 10 10Meg):

Độ lợi lớn: ~88 dB

Băng thông: ~1–2 MHz

Ổn định pha tốt, đáp ứng đạt yêu cầu khuếch đại open-loop

Tại tần số 100.9 Hz: Gain đạt ~38.3 dB

Bandwidth (–3 dB): đạt ~2.738 kHz

📐 Layout
Bố trí transistor đối xứng (NMOS phía dưới, PMOS phía trên)

Dùng via và metal routing hợp lý, tránh short

Pass DRC, LVS

Matching tốt ở cặp vi sai đầu vào

Bố trí chân GND, VDD, Vbias, Vout hợp lý, sẵn sàng tích hợp padframe

📌 Kết luận
Mạch Op-Amp CMOS có hiệu suất tốt, phù hợp với các ứng dụng khuếch đại tín hiệu yếu.

Cấu trúc 3 tầng đảm bảo độ lợi, độ ổn định và khả năng tải.

Có thể mở rộng để dùng trong ADC front-end, mạch lọc, cảm biến analog,...
