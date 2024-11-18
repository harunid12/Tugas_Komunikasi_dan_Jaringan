# Tugas 1 : Analisis Koneksi TCP dengan Socket Programming dan Wireshark

Tugas ini bertujuan untuk mempelajari komunikasi TCP antara client dan server menggunakan socket programming serta melakukan monitoring jaringan dengan Wireshark. Proses ini mencakup pengiriman data sederhana dan analisis paket TCP untuk memahami alur komunikasi, termasuk Connection establishment using three-way handshaking, Data Transfer dan Connection termination using three-way handshaking.

## Deskripsi Singkat

Pada tugas ini, saya memanfaatkan socket programming sederhana dari [Repository Github](https://github.com/ferryastika/socket-programming-simple-server-and-client) untuk mengimplementasikan komunikasi client-server. Server dijalankan pada port **8000**, dan client terhubung ke server tersebut. Data yang dikirim berupa karakter **A** dan selanjutnya dianalisis alur transmisinya menggunakan Wireshark.

hasil analisis Wireshark digambarkan dalam diagram TCP Sequence, yang menunjukkan detail komunikasi TCP secara berurutan dimulai dari connection establishment hingga connection termination

## TCP Connection Sequence Diagram

**Connection Establishment (Three-way handshaking)**

- **Step 1: SYN (Synchronize)**  
   Client mengirimkan paket **SYN** dengan `Seq=0` ke Server untuk memulai koneksi.

- **Step 2: SYN-ACK (Synchronize-Acknowledgment)**
  Server merespons dengan paket **SYN+ACK** yang memiliki Seq=0, Ack=1, menunjukkan bahwa server siap untuk menerima komunikasi.

- **Step 3: ACK**
  Client mengirimkan paket **ACK** dengan Seq=1, Ack=1, mengonfirmasi koneksi telah terjalin.

**Data Transfer**
pada tahap ini, **Client** dan **Server** saling bertukar data. prosesnya melibatkan flag **PSH + ACK** dan **ACK**.

- **Step 4: PSH + ACK**  
   Client mengirimkan data dengan paket : Seq = 1, Ack = 1.

- **Step 5: ACK**
  Server mengkonfirmasi penerimaan data dengan paket: Seq = 1, Ack = 2.

- **Step 6: PSH + ACK**
  Server mengirimkan data balik ke Client dengan paket : Seq = 1, Ack = 2.

- **Step 7: ACK**
  Client mengkonfirmasi penerimaan data dengan paket : Seq = 2, Ack =2.
