***Time chaos***

`Description`

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/1ac814fe-4635-4989-a512-7322bb618853)

`Solution`

Mở file ra bằng wireshark và sort theo thời gian có thể thấy ngay được flag

Let's go đầu tiên dùng tshark lấy data icmp ra và frametime để xử lý

`tshark -r Time_chaos.pcap -Y 'icmp' -T fields -e frame.time_relative -e data.data  > data`

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/118341d6-2600-4baf-8a63-89b8809b1dfc)

Giờ chúng ta dùng awk để xử lý tiếp
`awk '{print $0}' data | sort -n -k1 | awk '{print $2}'`

*giải thích một chút về script: Đầu tiên ta in ra màn hình và dùng pipe để sort theo hàng đầu tiên và cuối cùng in ra hàng thứ 2 để lấy data decode*

lấy được phần data đưa lên cyberchef để lấy flag 

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/4bbc605a-0d45-48ba-a714-8b5f750c6c83)

`flag: KMACTF{C0d3_cun9_du0c_t0Ol_Cun9_DuOc_nHun9_h1_v0n9_b4n_kh0n9_l@m_m0t_c4cH_tHu_C0nG}`
