`Descryption`

[Link tải challange](https://drive.google.com/file/d/1NviejQAGKBE45m6L260WrZ6_I9icJz1-/view?usp=sharing)

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/0c3fc8d1-f9d3-498c-94a9-6f7e7e5242eb)

`Solution`

Bài này thật ra theo thói quen bật log Powershell Operational lên đọc thì có 1 đoạn mã tấn công đồng thời chứa luôn flag cần tìm

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/7f1a6dcb-3fc8-40ab-befd-398737930f9c)

Giờ chúng ta cần 3 thứ phải tìm đó là PID của powershell.exe chạy script tấn công, tên user bao gồm cả tên miền nếu có, ngày giờ tấn công

`Get-Date.ToString()`

Phần này là phần có lẽ đơn giản nhất khi có ngay trên log

`5/22/2023 5:09:58 PM`

`PID`

Phần này vào xem log Sercurity để xem nó đã sinh ra PID là bao nhiêu và căn cứ vào thời gian tấn công là 5h09p chiều

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/d98e4a4c-73e6-4eb8-9206-9977edcdaad7)

phần new process id: 0x1030 chuyển sang decimal là 4144

`Account name-Account domain`

Có ngay ở phần log 4688 bên trên thì lấy được account name: long, account domain: KMA

Tiến hành thay các thông số vào và chạy để lấy flag

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/b0f69d5d-10fc-495f-8dfc-9f83f071a617)

`Flag: KMACTF{0da4ab044b8e929ec9c75bc44d24777e}`
