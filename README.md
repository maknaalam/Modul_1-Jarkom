# Modul_1-Jarkom

Name: Makna Alam Pratama <br />
NRP: 5025241077<br />


## Preblem 1
### How many pockets are recorded in pcapng file?
Answer: 9596 <br />
- Look at the footer information where the packets number of the pcapng file shown <br />
![1.1](images/1.1.png)<br />
### How many types of protocol (totals) are recorded in the traffic?
Answer: 12 <br />
- Statictic menu --> protocol hierarchy --> count each row <br />
![1.2](images/1.2.png)<br />
### How many types ofTCP-based applications protocol are recorded in the traffic?
Answer: 8 <br />
- Statictic menu --> protocol hierarchy --> count each row after Transmission Control Protocol <br />
![1.3](images/1.3.png)<br />
### How many packets with pure TCP protocol are recorded in the traffic (without data)?
Answer: 3223
- in filter, type: "tcp.len == 0" (the length of the TCP segment payload that carrys 0 data), which display 3222 packets. In some condition, Wireshark have minor problem by simply excluding 1 packets of data displayed in the number.
![1.4](images/1.4.png)<br />
