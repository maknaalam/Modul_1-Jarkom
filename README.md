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
Answer: 3223 <br />
- in filter, type: "tcp.len == 0" (the length of the TCP segment payload that carrys 0 data), which display 3222 packets. In some condition, Wireshark have minor problem by simply excluding 1 packets of data displayed in the number.
![1.4](images/1.4.png)<br />



## Preblem 3
### In what port is the telnet client open?
Answer: 54184 <br />
- click any of the packets that has telnet protocol and in the info it says byte of data (which mean rechieve data), then look up the Transmission Control Protocol of that packet to find its port <br />
![3.1](images/3.1.png)<br />
### How many bytes of the response files are sent from the server?
Answer: 1449 <br />
- right click the choosen port for number 3.1 --> click follow --> TCP stream --> look at the dropdown of entire conversation, there you will see the bytes it sends <br />
![3.2](images/3.2.png)<br />
### What telnet client's username is used to connect with the server?
Answer: joyvan <br />
- Still in the same TCP stream as number 3.2, try to find a word after "login:" <br />
![3.3](images/3.3.png)<br />
### What is the telnet client's password?
Answer: 123 <br />
- Still in the same TCP stream as number 3.2, try to find a word after "password:" <br />
![3.4](images/3.4.png)<br />

## Preblem 4
### What is the first command that the client wrote on telnet connection?
Answer: echo <br />
- Still in the same TCP stream as number 3.2, try to find any command word in programming <br />
![4.1](images/4.1.png)<br />
### What is the name of .txt file on the server?
Answer: test.txt <br />
- Still in the same TCP stream as number 3.2, try to find any .txt written <br />
![4.2](images/4.2.png)<br />
### What is the first word that the client inserted into the previous file?
Answer: Jarkom <br />
- Still in the same TCP stream as number 3.2, try to find a word after "echo" <br />
![4.3](images/4.3.png)<br />

## Preblem 5
### How many HTTP packets are recorded in the pcapng file?
Answer: 298 <br />
- in filter, type: "http", then see the displayed packets <br />
![5.1](images/5.1.png)<br />
### How many response HTTP packets are recorded in the traffic?
Answer:149 <br />
- in filter, type: "http.response", then see the displayed packets <br />
![5.2](images/5.2.png)<br />
### How many HTTP packets that succeed?
Answer: 296 <br />
- in filter, type: "http", then see the displayed packets. In here, we must also count the packets that labeled with color black and red which we don't want to count them. <br />
![5.3](images/5.3.png)<br />
### What is the client HTTP address in the connection with other local machine?
Answer: 172.16.16.101 <br />
- click any HTTP packets that has the usual client protocol use in the info, like "GET" --> Go to Internet Protocol Version to find the address  <br />
![5.4](images/5.4.png)<br />

## Preblem 6
### Did you find the fake flage?
Answer: FakeFlag{JarkomGampang} <br />
- in filter, type: 'frame contains "flag"' (packets where the raw packet data (the entire frame) contains the string "flag"), then right click the HTTP protocol one --> click follow --> TCP/HTTP stream --> find keyword like "FakeFlag" <br />
![6.1](images/6.1.png)<br />
### Write the written username and password!
Answer: Rey:123 <br />
- From the TCP/HTTP strem in 6.1 we know that there is no user or password displayed, however there is a passwd.txt file being shared. So by downloading the file, we can know the hidden string that are not fisible in the network <br />
![6.2](images/6.2.png)<br />

## Preblem 7
### What is the image that is being requested by the client?
Answer: donalbebek.jpg <br />
- click File menu --> go to export object --> choose http --> search for any extention for image which jpg is one of them <br />
![7](images/7.png)<br />

## Preblem 8
### How many FTP packets are recorded in the pcapng file?
Answer: 81 <br />
- in filter, type: "ftp or ftp-data", then see the displayed packets <br />
![8.1](images/8.1.png)<br />
### What is the client's username and password in the FTP connection?
Answer: rey:password123lingangu <br />
- after the filter in 8.1, choose any of the packets --> click follow --> TCP stream --> find keyword like "user" and "pass" <br />
![8.2](images/8.2.png)<br />
### What is the client's command for showing server directory that was sent on request packet?
Answer: LIST <br />
- Still in the same TCP stream as 8.2, find any information that provide "transfer" word in it, since it is a sent request. And for the word that come before it should be the command behind it <br />
![8.3](images/8.3.png)<br />





## Preblem 10
### What is the filename that contains encoded string?
Answer: secret.txt <br />
- click File menu --> go to export object --> choose ftp-data and you'll see all the file, which to contain string ususally located in .txt file <br />
![10.1](images/10.1.png)<br />
### What is the filename of the previous file copy?
Answer: secret1.txt <br />
- Still the same export ofject for ftp-data as 10.1. To find copied filename, usualy has the same extension and the base name is the same but with additional letter <br />
![10.2](images/10.2.png)<br />
### What is the decoded string from previous file?
Answer: Pada suatu hari Rey bertemu dengan Nailong the Milk Dragon. Ketika bertemu, Rey mengajarkan Nailong apa itu Jaringan Komputer. Nailong pun senang karena ternyata Jaringan Komputer itu gampang. <br />
- We save the object of the answer in 10.1, then open the file to copy the encoded string. Next we try to decode with every decoding methode out on public, and for the most common one is Base64  <br />
![10.3](images/10.3.png)<br />
