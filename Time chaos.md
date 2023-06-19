***Time chaos***

`Description`

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/8268f434-5f30-426d-96a5-e7f056fb2733)

`Solution`

Mở file ra bằng wireshark và sort theo thời gian có thể thấy ngay được flag

Let's go đầu tiên dùng tshark lấy data icmp ra và frametime để xử lý

`tshark -r Time_chaos.pcap -Y 'icmp' -T fields -e frame.time_relative -e data.data  > data`

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/3d5ecd7c-ffaa-46cf-b733-1ac86484ea95)

Giờ chúng ta dùng awk để xử lý tiếp
`awk '{print $0}' data | sort -n -k1 | awk '{print $2}'`

*giải thích một chút về script: Đầu tiên ta in ra màn hình và dùng pipe để sort theo hàng đầu tiên và cuối cùng in ra hàng thứ 2 để lấy data decode*

lấy được phần data đưa lên cyberchef để lấy flag 
![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/41268bab-dbda-4c1d-a966-06081a720a90)
`flag: KMACTF{C0d3_cun9_du0c_t0Ol_Cun9_DuOc_nHun9_h1_v0n9_b4n_kh0n9_l@m_m0t_c4cH_tHu_C0nG}`
