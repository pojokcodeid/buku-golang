# GO (GO-LANG)

## DAFTAR ISI

- [Pengantar dan Instalasi](<#Pengantar-dan-Instalasi-Bahasa-Pemrograman-Go-(Golang)>)
  - [Apa Itu Go](#Apa-Itu-Go)
  - [Keunggulan Go](#Keunggulan-Go)
  - [Produk Populer yang Menggunakan Go](#Produk-Populer-yang-Menggunakan-Go)
  - [Panduan Instalasi Go](#Panduan-Instalasi-Go)
- [Hello World](#Hello-World)
- [Variabel](#Variabel)

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
go version go1.25.2 windows/amd64
```

## Hello World

Tidak ada cara yang lebih baik untuk belajar bahasa pemrograman selain langsung menulis kode. Mari kita mulai dengan program Go pertama kita.

### Menyiapkan lingkungan pengembangan

Buatlah sebuah direktori untuk menulis program hello world. Buka terminal dan jalankan perintah berikut:

```bash
mkdir goexample
cd goexample
```

Perintah diatas akan membuat folder baru bernama goexample didalam folder yang terpilih di terminal saat ini. selanjutnya perintah cd goexample digunakan untuk mengacess folder yang sebelumnya sudah kita buat.

### Membuat Go Module

Langkah selanjutnya adalah membuat sebuah module GO dengan nama go example didalam folder goexample. Module Go digunakan untuk melacak dependensi aplikasi kita dan versinya. Kita akan membahas module Go lebih dalam ketika kita mempelajari paket (packages).

```bash
go mod init goexample
```

Ini akan membuat file bernama go.mod. Setelah menjalankan go mod init goexample, akan muncul:

```bash
go: creating new go.mod: module goexample
```

Isi dari file go.mod adalah sebagai berikut:

```go
module goexample

go 1.25.2
```

Baris pertama module goexample menunjukkan nama module. Baris berikutnya 1.25.2 menunjukkan bahwa file-file dalam module ini menggunakan versi Go 1.25.2.

### Membuat Hello World

Buatlah sebuah file bernama main.go di dalam direktori goexample menggunakan editor favorit Anda dengan isi sebagai berikut:

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello World")
}
```

Konvensinya dalam Go adalah menamai file yang berisi fungsi main sebagai main.go, tetapi nama lain juga bisa bekerja.

### Menjalankan program go

Ada beberapa cara berbeda untuk menjalankan program Go. Mari kita lihat satu per satu.

1. go install

Metode pertama adalah menggunakan perintah go install. Pertama, lakukan:

```bash
cd goexample
go install
```

Perintah di atas akan mengompilasi program dan menginstal (menyalin) binary ke lokasi GOPATH. Nama binary akan sama dengan nama module Go kita. Dalam contoh ini, namanya akan goexample. Untuk menemukan letak GOPATH gunakan perintah berikut

```bash
go env GOPATH
```

selanjutnya acess folder hasil install go dan jalankan:

```bash
cd C:\Users\asep\go
.\bin\goexample

Hello World
```

2. go build

Opsi kedua untuk menjalankan program adalah menggunakan go build. go build mirip dengan go install, kecuali bahwa ia tidak menginstal (menyalin) binary ke ~/go/bin/, melainkan menciptakan binary di lokasi direktori saat go build dijalankan.

```bash
cd goexample
go build
```

Perintah di atas akan menciptakan binary bernama goexample di direktori saat ini. Menjalankan ls akan menunjukkan file bernama goexample telah dibuat.
Ketikan ./goexample untuk menjalankan program tersebut, dan Anda akan melihat:

```bash
Hello World
```

Kita berhasil menjalankan program Go pertama kita menggunakan go build juga

3. go run

Cara ketiga menjalankan program adalah menggunakan perintah go run. Ketik:

```bash
cd goexample
go run main.go
```

Nanti keluarannya adalah:

```bash
Hello World
```

Perbedaan antara go run dan go build/go install adalah: go run membutuhkan nama file .go sebagai argumennya.
Di bawah permukaan, go run bekerja mirip dengan go build. Alih-alih mengompilasi dan menginstal program ke direktori standar, ia mengompilasi file ke lokasi sementara dan menjalankannya dari lokasi tersebut. Jika Anda tertarik untuk mengetahui di mana go run mengompilasi file, jalankan go run dengan argumen --work:

```bash
go run --work main.go
WORK=C:\Users\asep\AppData\Local\Temp\go-build1742785585
Hello World
```

Nilai dari kunci WORK menunjukkan lokasi sementara tempat program dikompilasi. Dalam kasus saya, program dikompilasi ke lokasi C:\Users\asep\AppData\Local\Temp\go-build1742785585. Ini mungkin berbeda pada kasus Anda

4. Go Playground

Cara terakhir menjalankan program adalah menggunakan playground Go. Meskipun terdapat beberapa batasan, metode ini sangat berguna ketika kita ingin menjalankan program sederhana karena menggunakan browser dan tidak memerlukan Go terpasang secara lokal. Untuk mencobanya kamu bisa menggunakan link yang disediakan oleh go

```
https://go.dev/play/
```

Sekarang kita tahu 4 cara berbeda menjalankan program. Anda mungkin bingung memilih metode yang tepat. Jawabannya: tergantung. Saya umumnya menggunakan playground ketika ingin melakukan pengecekan cepat terhadap logika atau mempelajari bagaimana fungsi library standar bekerja. Dalam banyak kasus lainnya, saya lebih memilih go install karena memberi opsi untuk menjalankan program dari direktori mana pun di terminal karena semua program dikompilasi ke jalur standar.

### Penjelasan singkat program hello world

Berikut kode program hello world yang kita tulis:

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello World")
}
```

Mari kita bahas secara singkat apa fungsi tiap baris.

package main — Setiap berkas Go harus diawali dengan pernyataan nama paket (package). Paket-paket digunakan untuk menyediakan pemisahan kode dan kemampuan reuse. Nama paket main digunakan di sini. Fungsi main harus selalu berada di paket main.
golangbot

import "fmt" — Pernyataan import digunakan untuk mengimpor paket lain. Dalam kasus ini, paket fmt diimpor dan akan digunakan di dalam fungsi main untuk mencetak teks ke output standar.
golangbot

func main() — Kata kunci func menandai awal sebuah fungsi. main adalah fungsi spesial. Eksekusi program dimulai dari fungsi main. Tanda { dan } menunjukkan awal dan akhir fungsi main.
golangbot

fmt.Println("Hello World") — Fungsi Println dari paket fmt digunakan untuk menulis teks ke output standar. Sintaks paket.Fungsi() digunakan untuk memanggil fungsi di dalam paket.

## Variabel

Variabel adalah nama yang diberikan untuk sebuah lokasi memori yang digunakan untuk menyimpan nilai dengan tipe tertentu. Dalam Go, terdapat beberapa cara untuk mendeklarasikan variabel. Berikut penjelasan lengkapnya:

1. Deklarasi Variabel Tunggal

Perintah Dasar :

```go
var namaVariabel tipeData
```

Contoh :

```go
var umur int
fmt.Println("Umur awal saya adalah", umur)
```
