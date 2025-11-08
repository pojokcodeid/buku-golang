# GO (GO-LANG)

## Pengantar dan Instalasi Bahasa Pemrograman Go (Golang)

### Apa Itu Go

Go, atau Golang, adalah bahasa pemrograman open-source yang dikompilasi dan bertipe statis. Bahasa ini dikembangkan oleh Google dan pertama kali dirilis pada November 2009. Tiga tokoh utama di balik pengembangan Go adalah Rob Pike, Ken Thompson, dan Robert Griesemer.
Go dirancang sebagai bahasa pemrograman umum yang sederhana, efisien, dan memiliki pustaka standar yang kuat. Bahasa ini sangat cocok untuk membangun aplikasi web yang skalabel dan system dengan kebutuhan tinggi, serta dapat digunakan untuk aplikasi CLI, desktop, maupun mobile.

### Keunggulan Go

- Sintaks yang Sederhana: Mudah dibaca dan dipelihara karena tidak dipenuhi fitur yang kompleks.
- Dukungan Konkuren Bawaan: Goroutine dan channel memudahkan penulisan program multithreaded.
- Bahasa Terkompilasi: Kode sumber dikompilasi menjadi biner native, berbeda dengan bahasa interpreted seperti JavaScript.
- Kompilasi Cepat: Compiler Go dirancang untuk kecepatan sejak awal.
- Static Linking: Semua dependensi dapat digabungkan dalam satu file biner, memudahkan proses deployment.
- Tooling Bawaan: Termasuk gofmt (format otomatis), vet (analisis kode), dan staticcheck (pengecekan gaya kode).
- Garbage Collection: Manajemen memori otomatis yang mendukung pemrograman konkuren.
- Spesifikasi Bahasa yang Ringkas: Dokumentasi lengkap dan cukup sederhana untuk dipahami, bahkan untuk menulis compiler sendiri.
- Open Source: Siapa pun dapat berkontribusi dalam pengembangan bahasa Go.

### Produk Populer yang Menggunakan Go

- Kubernetes – Platform orkestrasi container yang dikembangkan oleh Google.
- Docker – Platform containerisasi yang dibangun menggunakan Go.
- Dropbox – Memigrasikan komponen penting dari Python ke Go.
- Infoblox – Mengembangkan produk jaringan generasi berikutnya dengan Go.

### Panduan Instalasi Go

#### Mac OS

- Unduh installer dari https://go.dev/dl/
- Instalasi akan menempatkan Go di /usr/local/go
- Tambahkan /usr/local/go/bin ke variabel lingkungan PATH

#### Windows

- Unduh file MSI dari situs yang sama
- Instalasi akan menempatkan Go di C:\Go
- Tambahkan C:\Go\bin ke variabel lingkungan PATH

#### Linux

- Unduh file tar dari situs resmi
- Ekstrak ke direktori /usr/local
- Tambahkan /usr/local/go/bin ke variabel lingkungan PATH

✅ Verifikasi Instalasi
Setelah instalasi selesai, jalankan perintah berikut di terminal:

```bash
go version
```

Jika berhasil, akan muncul versi Go yang terinstal, misalnya:

```bash
go version go1.19.2 linux/amd64
```
