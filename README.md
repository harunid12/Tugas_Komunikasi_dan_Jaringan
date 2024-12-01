# Ujian Akhir Semester - Komunikasi dan Jaringan Komputer

**Semester Gasal Tahun Ajaran 2024/2025** 

**PROGRAM PASCASARJANA** 

**TEKNIK INFORMATIKA & KOMPUTER** 

**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA** 

Kampus PENS Jl. Raya ITS Keputih Sukolilo Surabaya 60111

<table>
  <tr>
    <td>
      <strong>Mata Kuliah</strong>: Komunikasi dan Jaringan Komputer<br>
      <strong>Kelas</strong>: S2 IT A<br>
      <strong>Waktu dan Jam</strong>: 13:00-17:00 (4 jam)
    </td>
    <td>
      <strong>Dosen</strong>: Ferry Astika Saputra<br>
      <strong>Sifat</strong>: Terbuka<br>
      <strong>Hari / Tgl</strong>: Senin, 2 Desember 2024
    </td>
  </tr>
</table>

Question  below are based on the trace file tcp-ethereal-trace-1 in in http://gaia.cs.umass.edu/wireshark-labs/wireshark-traces.zip

Answer the following questions for the TCP segments:

**1. What is the IP address and TCP port number used by your client computer (source) to transfer the file to gaia.cs.umass.edu? (10%)**

_Answer_:

![figure1](./UAS_Ahmad%20Harun_1224800014/assets/figure1.jpg)

<p align="center">
  <strong>Figure 1</strong>. IP Address and TCP Port Number of the client computer
</p>

From Figure 1, the IP address used by the client computer to transfer files to the server gaia.cs.umass.edu is **192.168.1.102**, with TCP port number **1161**. The identification method involves searching for TCP packets in Wireshark that have the HTTP POST protocol, which is typically used to transfer data from the client to the server. Then, check the Source Address in the Internet Protocol Version 4 tab and the Source Port in the Transmission Control Protocol tab. 

**2. What does gaia.cs.umass.edu use the IP address and port number to receive the file. (Attach the screenshot of your Wireshark's display) (10%)**

_Answer_:

![figure2](./UAS_Ahmad%20Harun_1224800014/assets/figure2.jpg)

<p align="center">
  <strong>Figure 2</strong>. IP Address and TCP Port Number of gaia.cs.umass.edu
</p>

The IP address used by the server gaia.cs.umass.edu to receive files is **128.119.245.12**, with TCP port number **80**. The identification method involves searching for TCP packets in Wireshark that use the HTTP Response protocol, particularly packets with a status such as 200 OK, which indicates the acceptance of the request or the successful transfer of the file.

**3. What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? What is it in the segment that identifies the segment as a SYN segment? (Attach the screenshot of your Wireshark's display) (10%)**

_Answer_:

![figure3](./UAS_Ahmad%20Harun_1224800014/assets/figure3.jpg)

<p align="center">
  <strong>Figure 3</strong>. Sequence Number of the TCP SYN Segment
</p>

The sequence number of the TCP SYN segment used to initiate the connection between the client computer and gaia.cs.umass.edu is **0**. This segment is identified as a SYN segment by the SYN flag visible in the TCP **Flags: 0x002 (SYN)** and also the binary value **.... ..0. .... = Syn: Set**, which indicates that this segment is the initial step in the three-way handshake process.

**4.	What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is the value of the ACKnowledgement field in the SYNACK segment? How did gaia.cs.umass.edu determine that value? What is it in the segment that identifies the segment as a SYNACK segment? (Attach the screenshot of your Wireshark's display) (10%)**

_Answer_:

![figure4](./UAS_Ahmad%20Harun_1224800014/assets/figure4.jpg)

<p align="center">
  <strong>Figure 4</strong>. Sequence and Acknowledgement Number of the SYN-ACK Segment
</p>

The sequence number of the SYN-ACK segment sent by gaia.cs.umass.edu to the client computer in response to the SYN is **0**. 
The value in the Acknowledgement column of the SYN-ACK segment is **1**. 
This acknowledgement value is determined by the server gaia.cs.umass.edu by adding 1 to the initial sequence number of the SYN segment sent by the client computer. Since the initial sequence number of the SYN segment is 0, the acknowledgement value in the SYN-ACK segment becomes 1.






