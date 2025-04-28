# Nama : Moh. Yusril
# Nim : 09011382429124
# kelas : SKU2B

![Screenshot 2025-04-28 140931](https://github.com/user-attachments/assets/913f00c3-0816-44ca-8992-07961bdf3e72)

## Arsitektur Symmetric Multiprocessing (SMP)

Diagram yang disajikan mengilustrasikan arsitektur Symmetric Multiprocessing (SMP), sebuah desain sistem komputasi yang mengoptimalkan kinerja melalui penggunaan beberapa prosesor identik. Sistem ini terdiri dari empat unit pemrosesan (CPU) yang masing-masing beroperasi pada kecepatan 3.2 GHz, semuanya terhubung ke pengontrol memori pusat yang mengimplementasikan akses memori terpadu (UMA). Pengontrol memori ini berfungsi sebagai jembatan kritis, memfasilitasi komunikasi antara CPU dan komponen memori sistem, termasuk memori utama berkapasitas 64GB DDR5 dan empat cache L3 masing-masing 16MB.
Dalam arsitektur ini, data mengalir dari CPU ke pengontrol memori melalui jalur komunikasi berkecepatan tinggi yang digambarkan dengan garis putus-putus biru. Pengontrol memori kemudian mendistribusikan dan mengatur aliran data antara prosesor dan komponen memori melalui koneksi yang ditandai dengan garis putus-putus ungu. Cache L3 berperan penting sebagai penyimpanan sementara berkecepatan tinggi yang mengurangi latensi dengan menyimpan data yang sering diakses, sehingga menjembatani kesenjangan kinerja antara CPU yang cepat dan memori utama yang relatif lebih lambat.
Sistem input/output diimplementasikan melalui Port System, sebuah interkoneksi berkecepatan tinggi yang menghubungkan cache memori dengan perangkat penyimpanan dan jaringan. Port System ini memungkinkan komunikasi yang efisien antara subsistem memori dan perangkat eksternal, dengan garis putus-putus hijau menunjukkan jalur dari cache dan garis merah menghubungkannya ke penyimpanan NVMe SSD dan antarmuka jaringan Ethernet 10Gbps. Desain hierarkis ini memaksimalkan throughput data dan meminimalkan bottleneck, sangat penting untuk aplikasi yang membutuhkan pemrosesan paralel dan akses memori intensif.
Arsitektur SMP ini memiliki empat karakteristik utama yang disorot dalam diagram: memori bersama yang memungkinkan semua prosesor mengakses ruang memori yang sama, desain UMA yang menjamin waktu akses memori yang seragam untuk semua prosesor, koherensi cache yang memastikan konsistensi data di seluruh subsistem memori, dan infrastruktur berbasis bus yang memfasilitasi komunikasi yang terorganisir antar komponen. Dengan fitur-fitur ini, arsitektur SMP memberikan solusi yang seimbang dan efisien untuk komputasi paralel dalam server performa tinggi, workstation, dan sistem database yang memerlukan pemrosesan data simultan dan responsif.

![Screenshot 2025-04-28 145329](https://github.com/user-attachments/assets/bb4801fa-4073-48d2-9cef-133fdbcdba0c)

## Arsitektur Multiple Processor (AMP)

Arsitektur multiple processor yang ditampilkan merupakan sistem komputasi yang menggunakan beberapa prosesor berbeda untuk menjalankan berbagai tugas komputasi secara paralel. Sistem ini dirancang untuk meningkatkan kinerja keseluruhan dengan mendistribusikan beban kerja di antara beberapa unit pemrosesan, yang memungkinkan penyelesaian tugas secara bersamaan daripada berurutan seperti pada arsitektur prosesor tunggal.

## Komponen dan Hubungan
# 1. Processor (Prosesor)
Sistem ini memiliki empat prosesor dengan teknologi dan kecepatan yang berbeda:
* Processor 1 (Core i7 - 3.5GHz): Prosesor Intel dengan arsitektur x86, biasanya digunakan untuk komputasi tujuan umum dan kinerja tinggi. Terhubung ke cache L1 miliknya dan ke system bus.
* Processor 2 (AMD - 3.2GHz): Prosesor alternatif dengan arsitektur x86, seringkali memiliki keunggulan dalam pemrosesan paralel. Juga terhubung ke cache L1 dan system bus.
* Processor 3 (ARM - 2.8GHz): Prosesor dengan arsitektur RISC (Reduced Instruction Set Computing) yang umumnya lebih efisien energi, ideal untuk perhitungan tertentu atau aplikasi mobile. Terhubung ke cache L1 dan system bus.
* Processor 4 (RISC - 3.0GHz): Prosesor dengan set instruksi yang disederhanakan untuk efisiensi eksekusi. Terhubung ke cache L1 dan system bus.

Fungsi: Setiap prosesor bertanggung jawab untuk eksekusi instruksi program, perhitungan, dan manipulasi data. Keragaman prosesor memungkinkan sistem untuk mengalokasikan tugas yang paling sesuai dengan karakteristik prosesor tertentu.

# 2. Cache Memory (Memori Cache)
Setiap prosesor memiliki cache L1 sendiri yang terhubung langsung ke prosesor dan system bus.
* Fungsi: Cache L1 menyimpan data dan instruksi yang sering diakses untuk mengurangi latensi memori. Cache memungkinkan prosesor mengakses data dengan lebih cepat dibandingkan jika harus mengambil dari memori utama. Hal ini sangat penting dalam arsitektur multiple processor karena dapat mengurangi bottleneck pada akses memori bersama.

# 3. System Bus (Bus Sistem)
Bus sistem adalah jalur utama yang menghubungkan semua prosesor (melalui cache mereka) dengan komponen sistem lainnya seperti memori utama, sistem controller, dan subsistem I/O.
* Fungsi: Bus sistem menangani semua transfer data dan sinyal kontrol antar komponen sistem. Bus ini memfasilitasi komunikasi antara berbagai bagian sistem komputer, memungkinkan prosesor untuk mengakses memori, berkomunikasi dengan perangkat I/O, dan berkoordinasi dengan prosesor lainnya.

# 4. Main Memory (Memori Utama)
Memori utama berupa 64GB DDR5 RAM yang terhubung ke system bus, sehingga dapat diakses oleh semua prosesor dalam sistem.
* Fungsi: Memori utama menyimpan data dan program yang sedang dieksekusi oleh prosesor. Dalam arsitektur multiple processor, desain memori harus mampu menangani permintaan akses bersamaan dari berbagai prosesor tanpa mengalami degradasi kinerja signifikan.

# 5. System Controller (Kontroler Sistem)
Sistem kontroler terhubung ke system bus dan berperan dalam manajemen bus.
* Fungsi: System controller mengelola dan mengkoordinasikan lalu lintas data pada bus sistem. Ini termasuk pengaturan prioritas akses bus, menyelesaikan konflik ketika beberapa prosesor mencoba mengakses sumber daya yang sama secara bersamaan, dan memastikan koherensi cache di seluruh sistem.

# 6. I/O Subsystem (Subsistem I/O)
Subsistem I/O terhubung ke system bus dan ke berbagai perangkat peripheral.
* Fungsi: Subsistem I/O menangani semua komunikasi antara sistem komputer dan dunia luar. Ini mengelola input dan output data, melakukan kontrol perangkat, dan mengkoordinasikan transfer data antara perangkat eksternal dan memori sistem atau prosesor.
  
# 7. Peripheral Devices (Perangkat Peripheral)
Tiga tipe perangkat peripheral yang terhubung ke subsistem I/O:

* Storage (SSD/HDD): Perangkat penyimpanan untuk data permanen.
* Network (10Gbps): Antarmuka jaringan untuk komunikasi eksternal.
* Peripherals (USB/Display): Berbagai perangkat tambahan seperti USB dan tampilan visual.

* Fungsi: Perangkat peripheral menyediakan fungsionalitas tambahan ke sistem komputer, termasuk penyimpanan data persisten, konektivitas jaringan, dan interaksi pengguna.

# Alur Data dan Operasi Sistem
Dalam arsitektur multiple processor ini, alur data beroperasi sebagai berikut:

## 1. Ketika program perlu dieksekusi, instruksi dan data diambil dari memori utama melalui system bus ke cache L1 prosesor yang ditugaskan.
## 2. Prosesor mengeksekusi instruksi, menggunakan data dari cache L1 bila memungkinkan, atau meminta data tambahan dari memori utama jika diperlukan.
## 3. System controller memastikan semua permintaan akses memori diproses secara efisien, menghindari konflik akses dan mempertahankan koherensi data di seluruh sistem.
## 4. Jika operasi memerlukan input atau output, subsistem I/O mengelola komunikasi dengan perangkat peripheral yang sesuai.
## 5. Data dari atau ke perangkat peripheral diproses melalui subsistem I/O, yang kemudian mentransfer data melalui system bus ke memori atau prosesor yang membutuhkan.

Keunggulan utama dari arsitektur multiple processor ini adalah kemampuannya untuk menjalankan beberapa tugas secara bersamaan dengan prosesor yang berbeda. Ini sangat bermanfaat untuk aplikasi yang membutuhkan komputasi tinggi seperti pemodelan 3D, analisis data, pemrosesan video, dan server aplikasi skala besar.
