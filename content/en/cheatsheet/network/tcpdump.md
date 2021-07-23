+++
title = "Tcpdump"
date = 2021-07-21T11:49:22+09:00
draft = false
featured = true
categories = [
  "Cheet Sheet"
]
tags = [
  "network", "css", "Math"
]
series = [
  "User Manual"
]
images = [
]
+++

## tcpdump 파라미터 (간단히)
```
-i ethx       : 대상 네트워크 카드를 지정
-w filename   : 출력을 특정 파일로 지정
-r filename   : 특정 파일을 text포맷형식으로 변환하여 확인
-c NUM        : NUM만큼 패킷의 head를 확인
-s NUM        : 패킷의 길이(1500이 패킷의 전체길이를 의미, 물론 변경될 수도 있슴). (ifconfig확인)
-tcp port XX  : tcp XX포트만 지정
-host IP      : 특정 IP만 캡쳐
-Xqnr         : 저장한 데이터를 ASCII모드로 파일 내용을 확인
-v            : 많은 정보를 보여준다.
-vv           : -v보다 더 많은 정보를 보여준다.
-nn           : port 번호를 번역하지 않는다 (기본은 알려진 포트번호를 번역한다) 페도라계열 (Centos, Redhat)
```


## tcpdump 옵션 combine & grouping
* combine
  * and ( && ) , or ( || ) , not ( ! ) 으로 여러가지를 조합해서 사용 가능
* grouping : ( )

## tcpdump 사용예


* 인터페이스 eth0 을 지나는 패킷 확인
  ```bash
  tcpdump -i eth0
  ```
* 결과를 파일로 저장, txt 가 아닌 bin 형식으로 저장됨
  ```bash
  tcpdump -w tcpdump.log
  ```

* 저장한 파일을 읽기
  ```bash
  tcpdump -r tcpdump.log
  ```

* 카운터 10개만 확인
  ```bash
  tcpdump -i eth0 -c 10
  ```

* 인터페이스 eth0 을 지나고 tcp 80 포트로 통신하는 패킷 확인
  ```bash
  tcpdump -i eth0 tcp port 80
  ```

* 인터페이스 eth0 을 지나고 source ip 가 192.168.0.1인 패킷 확인
  ```bash
  tcpdump -i eth0 src 192.168.0.1
  ```

* 인터페이스 eth0 을 지나고 dest ip 가 192.168.0.1인 패킷 확인
  ```bash
  tcpdump -i eth0 dst 192.168.0.1
  ```

* 인터페이스 em2에서 tcp 포트 443(https) 를 오가는 패킷 확인. (port 번호를 https가 아니라 443으로 그대로 표시)
  ```bash
  tcpdump -i em2 -nn tcp port 443
  ```

* source ip 가 192.168.0.1이고 tcp port 80 인 패킷 확인
  ```bash
  tcpdump -i eth0 src 192.168.0.1 and tcp port 80
  ```

* UDP 이고 src 포트가 53 인 것
  ```bash
  tcpdump udp and src port 53
  ```

* src ip 가 192.168.0.1 이고 dst 포트가 22 가 아닌 것
  ```bash
  tcpdump src 192.168.0.1 and not dst port 22
  ```

* src ip 가 192.168.0.1 이고 ( dst 포트가 3389 또는 22 ) 인 것
  ```bash
  # ' ' 가 반드시 있어야 한다.
  tcpdump 'src 192.168.0.1 and ( dst port 3389 or 22 )'
  ```

* bond0 인터페이스에서 destination ip 가 224.110.110.110이면서 destination port가 9999 인 패킷 캡춰
  ```bash
  tcpdump -i bond0 dst 224.110.110.110 and dst port 9999
  ```

* To print all packets arriving at or departing from sundown:
  ```bash
  tcpdump host sundown
  ```

* To print traffic between helios and either hot or ace:
  ```bash
  tcpdump host helios and \( hot or ace \)
  ```
* To print all IP packets between ace and any host except helios:
  ```bash
  tcpdump ip host ace and not helios
  ```

* To print all traffic between local hosts and hosts at Berkeley:
  ```bash
  tcpdump net ucb-ether
  ```

* To print all ftp traffic through internet gateway snup: (note that the expression is quoted to prevent the shell from (mis-)interpreting the parentheses):
  ```bash
  tcpdump 'gateway snup and (port ftp or ftp-data)'
  ```

* To print traffic neither sourced from nor destined for local hosts (if you gateway to one other net, this stuff should never make it onto your local net).
  ```bash
  tcpdump ip and not net localnet
  ```

* To print the start and end packets (the SYN and FIN packets) of each TCP conversation that involves a non-local host.
  ```bash
  tcpdump 'tcp[tcpflags] & (tcp-syn|tcp-fin) != 0 and not src and dst net localnet'
  ```

* To print the TCP packets with flags RST and ACK both set. (i.e. select only the RST and ACK flags in the flags field, and if the result is "RST and ACK both set", match)
  ```bash
  tcpdump 'tcp[tcpflags] & (tcp-rst|tcp-ack) == (tcp-rst|tcp-ack)'
  ```

* To print all IPv4 HTTP packets to and from port 80, i.e. print only packets that contain data, not, for example, SYN and FIN packets and ACK-only packets. (IPv6 is left as an exercise for the reader.)
  ```bash
  tcpdump 'tcp port 80 and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'
  ```

* To print IP packets longer than 576 bytes sent through gateway snup:
  ```bash
  tcpdump 'gateway snup and ip[2:2] > 576'
  ```

* To print IP broadcast or multicast packets that were not sent via Ethernet broadcast or multicast:
  ```bash
  tcpdump 'ether[0] & 1 = 0 and ip[16] >= 224'
  ```

* To print all ICMP packets that are not echo requests/replies (i.e., not ping packets):
  ```bash
  tcpdump 'icmp[icmptype] != icmp-echo and icmp[icmptype] != icmp-echoreply'
  ```
