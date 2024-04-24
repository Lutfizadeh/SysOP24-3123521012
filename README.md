# Kumpulan Tugas


## Tugas 1
Referensi : Topik 1 Sejarah OS
1. Apa hubungan antara perangkat lunak aplikasi dan sistem operasi?
- Sistem operasi adalah wadah untuk menjalankan perangkat lunak aplikasi
2. Apa yang dimaksud dengan sistem operasi? Apakah itu perangkat keras atau perangkat lunak?
- Sistem operasi adalah program yang bertindak sebagai antarmuka antara pengguna komputer dengan perangkat keras komputer, itu adalah perangkat lunak
3. Sebutkan fungsi utama suatu sistem operasi!
- Membuat komputer nyaman digunakan
4. Jelaskan secara singkat evolusi sistem operasi!
- Generasi pertama : Operasi hands-on ke operasi closed shop ke pengembangan sistem operasi mono-programmed
- Generasi kedua : Transistor menggantikan tabung vakum sebagai komponen perangkat keras
- Generasi ketiga : Teknoogi perangkat keras mulai menggunakan Integrated Circuit(ICs) yang bisa lebih cepat dan dan hemat biaya
- Generasi keempat : Kemunculan komputer pribadi dan workstation
5. Apa saja elemen kunci dari sistem operasi?
- Kernel
- Manajemen memori
- Manajemen proses
- Manajemen sumber daya
- Manajemen sistem file
- Antarmuka pengguna
- Keamanan sistem
- Manajemen perangkat I/O
- Jasa jaringan
6. Apa yang Anda maksud dengan istilah generasi komputer?
- Suatu masa yang menunjukkan perkembangan komputer
7. Siapa yang memberikan gambaran tentang program tersimpan dan pada tahun berapa? Siapa yang memberikan struktur dasar komputer?
- IBM pada tahun 1964. Yang memberikan struktur dasar komputer adalah John Von Neumann
8. Sebutkan kekurangan komputer generasi pertama dibandingkan komputer generasi kedua!
- Penggunaan sumber daya sistem yang tidak efisien
- Kernel sistem operasi tidak terlindungi dari penimpaan program aplikasi yang salah
- Program penggunna lain dalam antrean tidak terlindungi dari kehancuran oleh program yang sedang berjalan
9. Berdasarkan sistem manakah komputer generasi kedua? Apa saja penemuan baru pada komputer generasi kedua?
- Sebagian besar sistem komputer tetap merupakan sistem yang berorientasi pada kartu dan tape
Penemuan barunya :
- Transistor menggantikan tabung vakum sebagai komponen perangkat keras
- Mengatasi masalah penundaan prosesor pusat yang berlebihan karena menunggu operasi input/output
- Saluran data, yaitu sebuah komputer integral yang bertujuan khusus dengan set instruksi, register, dan unit kontrolnya sendiri yang dirancang untuk memproses input/output secara terpisah dan tidak sinkron dengan pengoperasian CPU utama komputer menjelang akhir generasi pertama, dan digunakan secara luas pada generasi kedua
10. Deskripsikan apa itu IC / sirkuit terpadu!
- IC (Integrated Circuit) adalah teknologi elektronika di mana transistor, resistor, kapasitor, dioda, dan perangkat elektronika lainnya digabung menjadi satu dalam satu keping silikon atau substrat semikonduktor
11. Apa inovasi terpenting komputer generasi ketiga?
- Munculnya multipemrograman
12. Berikan gambaran singkat tentang komputer generasi keempat. Bagaimana teknologinya lebih baik dari generasi sebelumnya?
- Komputer generasi keempat ditandai dengan munculnya komputer pribadi dan workstation
- Lebih baik dari generasi sebelumnya karena Large Scale Integration (LSI) pada generasi ketiga diganti dengan Very Large Scale Integration (VSLI) pada generasi keempat, yang dapat memuat ribuan transistor pada sebuah chip kecil, yang memungkinkan pegembangan komputer desktop dengan kemampuan yang melebihi komputer yan memenuhi seluruh ruangan dan lantai gedung 20 puluh sebelumnya
13. Berapakah masa komputer generasi kelima dan bandingkan inovasi dari generasi sebelumnya?
- Awal 1980-an sampai pertengahan 1990-an
Perbandingan :
Generasi kelima :
- Berfokus pada pengembangan kecerdasan buatan
- Pemrosesan paralel lebih sering digunakan, khususnya pada penelitian dan eksperimen
- Ukuran lebih kecil
Generasi sebelumnya :
- Berfokus pada peningkatan kerja dan efisiensi perangkat keras
- Pemrosesan paralel belum sebesar generasi kelima
- Ukuran lebih besar
14. Apa perbedaan antara perangkat keras dan perangkat lunak?
- Perangkat keras berbentuk fisik
- Perangkat lunak berbentuk nonfisik
15. Apa perbedaan antara perangkat lunak sistem dan perangkat lunak aplikasi?
- Perangkat lunak sistem adalah perangkat yang  menyediakan wadah untuk menjalankan aplikasi, contoh: Windows, MacOS, Linux
- Perangkat lunak aplikasi adalah perangkat lunak yang memiliki fungsi khusus dalam membantu pengguna, contoh:  Browser, Microsoft Office, Aplikasi desain, dll


## Tugas 2
### Boot Process
![boot process lutfi zadeh filoshof](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8727f5df-1126-459e-8436-f0210f79f8c9)
1. Setelah menyalakan mesin, BIOS (atau EFI) mendapatkan kendali prosesor. BIOS membaca Master Boot Record dari Hard disk ke memori fisik dan mengatur register mikroprosesor untuk melompat ke Kode Master Boot Record.
2. Master Boot Record (MBR) adalah area khusus yang berisi informasi tentang hard disk, tabel partisi dan partisi mana adalah partisi bootable aktif pada hard disk. Kontrol kemudian diteruskan ke loader sistem operasi yaitu MBR memuat Volume Boot Record (VBR) ke dalam memori.
3. Poin 2 adalah kasus ketika hanya ada satu sistem operasi diinstal pada mesin. Jika ada beberapa operasi sistem (seperti kasus dual boot) maka MBR perlu melakukan operasi yang lebih kompleks. Karena terbatas ukuran Master Boot Record tidak dapat berisi kumpulan yang sangat besar atau kompleks peraturan. Oleh karena itu dapat memuat boot loader pada titik ini, bukan sistem operasi. Misalnya dalam kasus dari sistem dual boot boot loader seperti GRUB dimuat yang dapat memberi Anda Beberapa opsi untuk dipilih untuk mem-boot sistem operasi.
4. Melanjutkan dengan contoh GRUB, itu berisi pengidentifikasi partisi tempat OS diinstal. Jika pengguna memilih untuk boot di Windows GRUB akan meneruskan kontrol ke Volume Boot Sector dari partisi yang diharapkan Windows ada. Proses memuat OS melalui Boot loader (seperti grub) disebut chain Loading.
5. NT Boot Sector melayani tujuannya membaca dari sistem file NTFS, Kami sekarang berada di dalam sistem file NTFS dan dari sini Seterusnya file dengan ekstensi .exe akan mulai muncul.
Tujuan utama dari sektor NT Boot adalah untuk membaca dan memuat file BOOTMGR yang merupakan sistem tersembunyi file yang terletak di partisi %SYSTEMROOT% atau di partisi EFI, oleh karena itu tidak akan ditampilkan jika dicari di hard disk menggunakan Windows Penjelajah. File tidak dapat dieksekusi karena memiliki header 16 bit, itu dimulai mengeksekusi dalam 32 bit kemudian, secara otomatis.
6. File BOOTMGR terletak di 'c: \ folder'. Dalam banyak teks, bootmgr disebut bootmgr.exe
7. BOOTMGR, pada dasarnya, menggantikan file NTLDR dari era pra-Vista. BOOTMGR memeriksa status sistem jika Sistem sedang hibernasi. Pada titik ini proses boot dapat bercabang menjadi dua Cara.
8. BOOTMGR memeriksa Konfigurasi Boot File data (BCD) yang terletak di Partisi Sistem EFI, oleh karena itu BCD tidak akan ditampilkan jika dicari menggunakan Windows Explorer seperti pada Partisi Sistem yang berbeda. File BCD berisi informasi mengenai proses boot. Tujuan BCD dapat dengan mudah dipahami Mengetahui bahwa itu menggantikan file boot.ini dari era pra-Vista.
Format isi BCD sama seperti Windows Registry, dan itu sangat cocok untuk BCD untuk memiliki Binary Windows Registry seperti format sebagai konten berkas BCD dimuat di registri Windows di bawah kunci: HKEY_LOCAL_MACHINE\BCD0000.
BCD disimpan dalam format registri windows dan dapat diedit menggunakan bcedit.exe, juga dapat diedit menggunakan Editor registri karena dimuat ke registri, dan bisa juga diedit menggunakan Windows Management Instrumentation atau alat pihak ketiga lainnya.
9. Jika sistem dalam hibernasi atau tidur maka Bootmgr melewati kontrol ke WINRESUME.EXE.
10. WINRESUME.EXE, seperti namanya, resume Windows ke keadaan itu sebelum masuk ke Hibernasi.
11. Kalau mesin tidak dalam hibernasi, kontrol dari BOOTMGR akan diteruskan ke WINLOAD.exe
12. Penting untuk dicatat di sini bahwa dengan Winresume.exe dan Winload.exe kita telah memasuki ranah file exe windows. Ini juga merupakan bagian di mana proses boot bercabang berdasarkan keputusan pada apakah proses boot setelah shutdown atau hibernasi.
Memuat salah satu winload.exe atau winresume.exe adalah tujuan utama dari Windows Boot Manager alias bootmgr(.exe).
13. Pertama-tama kita akan menyusuri jalan WINLOAD.EXE. WINLOAD.EXE mengimplementasikan apa yang sebelumnya merupakan fungsi NTLDR. WINLOAD.EXE melakukan hal berikut:
a. Memuat driver kelas boot, ini adalah driver dibutuhkan pada saat startup. Jika driver ini tidak dimuat saat ini kesalahan seperti: "Perangkat boot tidak dapat diakses", "Pengaturan tidak dapat menentukan mesin Anda jenis" atau "Pengaturan tidak dapat menemukan hard drive apa pun di komputer Anda" dapat berupa Dihadapi.
b. Memuat dependensi untuk kernel.
c. Banyak HAL.DLL (dibahas di bawah)
d. Kernel dari Microsoft Windows yaitu, NTOSKERNEL.EXE
e. Memuat kumpulan registri SISTEM.
f. Memuat driver perangkat kelas 'boot' dan kernel-mode dll diimpor oleh hal.dll

### Identifikasi Laptop
ASUS TUF GAMING F15

1. CPU :

![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/88708c4f-84ee-40a8-af92-008d951fa105)
- Menggunakan processor : Intel Core I5 10300H dengan cores : 4

2. Mainboard :

![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/37189289-e893-472d-9e38-b9bdc19bda10)
- Menggunakan motherboard : ASUSTeK COMPUTER INC. dengan model : FX506LHB dan brand BIOS : American Megatrends Inc.

3. Memory :

![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/64d4c52e-614f-47af-987c-aa60628bee7b)
- Dual DDR4 dengan ukuran 16GBytes

4. SPD :

![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/dc2a6d2c-4c53-47ad-b9cd-e918ebb0c81c)
![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/b678a527-b086-4484-a657-fd124f28c6b2)
- Slot 1 menggunakan DDR4 8GB dengan module manuf Micron Technology dan slot 3 menggunakan DDR4 8GB dengan module manuf Lexar

5. Graphics  :

![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/ea1336ea-e417-418d-a09c-fb512cb83b98)
![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/b8e40454-e7a8-4b6f-992a-a75ca7a897fe)
- Menggunakan Intel(R) UHD Graphics dan NVIDIA GeForce GTX 1650

6. Bench :

![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/18777b78-0e5e-47cb-9702-80fd5879aecc)
- Menggunakan benchmark versi 17.01.64

### Mindmap Sejarah, Cara Kerja, dan Fungsi-fungsi Sistem Operasi
![Mind Map sistem operasi](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/46e45d27-be69-4d32-90c3-1988f98e8623)

### Perbedaan BIOS dan EFI
1. Arsitektur dan Desain:
- BIOS: Tradisionalnya, BIOS menggunakan model arsitektur firmware yang berbeda dan sering kali terbatas dalam kemampuan dan fleksibilitasnya. BIOS menggunakan MBR (Master Boot Record) untuk menyimpan informasi partisi dan kode bootloader.
- EFI: EFI dirancang dengan arsitektur yang lebih modern dan modular. EFI menggunakan GPT (GUID Partition Table) sebagai pengganti MBR, dan ini memungkinkan dukungan untuk partisi yang lebih besar dan lebih banyak partisi.

2. Bootloader:
- BIOS: Menggunakan bootloader yang terintegrasi dengan firmware dan biasanya terbatas pada bootloaders seperti GRUB atau LILO.
- EFI: Dapat menggunakan bootloader yang terpisah dari firmware. EFI mendukung bootloader seperti GRUB, rEFInd, atau Microsoft Boot Manager.

3. Antarmuka Pengguna:
- BIOS: Umumnya menggunakan antarmuka pengguna yang sederhana dan terbatas, sering kali hanya dapat diakses melalui tombol khusus saat boot.
- EFI: Menyediakan antarmuka pengguna yang lebih canggih, sering kali dengan dukungan untuk mouse dan grafis. EFI Shell memungkinkan pengguna untuk berinteraksi dengan firmware secara lebih kompleks.

4. Dukungan Perangkat Keras:
- BIOS: Terbatas dalam mendukung perangkat keras modern dan fitur canggih seperti booting dari disk berkapasitas besar atau keamanan boot yang tinggi.
- EFI: Lebih fleksibel dan mendukung perangkat keras modern dengan lebih baik, seperti boot dari disk berkapasitas besar (lebih dari 2 TB) dan keamanan boot berbasis UEFI Secure Boot.

5. Kompatibilitas Sistem Operasi:
- BIOS: Umumnya lebih terbatas dalam mendukung sistem operasi modern, terutama sistem operasi 64-bit.
- EFI: Lebih mendukung sistem operasi modern dan dapat bekerja dengan baik dengan sistem operasi 32-bit dan 64-bit.
Pada umumnya, EFI dianggap lebih canggih dan fleksibel daripada BIOS, dan banyak sistem modern mengadopsi EFI sebagai pengganti BIOS.


## Tugas 3
### Cara Install Debian
1. Download installer Debian [di sini](https://cdimage.debian.org/debian-cd/current/amd64/iso-dvd/debian-12.5.0-amd64-DVD-1.iso)
2. Buka Virtual Machine (VM)
3. Klik *New* di bagian atas
4. Beri nama (Misal: *Debian12 Desktop Lutfi*, maka type akan menyesuaikan)
5. Klik *Next* -> *Next* -> *Next* -> *Finish*
6. Klik *Start* di bagian atas
7. Tunggu hingga muncul pop up
8. Jika sudah muncul, klik tanda panah ke bawah -> *Other*
9. Cari dan pilih installer Debian yan sudah didownload
10. Klik *Mount and Retry Boot*
11. Klik *Install*
12. Pilih bahasa (Contoh: English)
13. Pilih lokasi (Jika Indonesia, maka klik *other* -> *Asia* -> *Indonesia*)
14. Pilih konfigurasi lokal (Direkomendasikan United States)
15. Pilih konfigurasi keyboard (Biasanya American English)
16. Masukkan hostname (Contoh: LUTFI)
17. Masukkan domain name (Contoh: lutfi.pens.ac.id)
18. Masukkan password root (Default: 1) dan masukkan verifikasi password root yang sudah dimasukkan tadi
19. Masukkan fullname untuk user baru (Contoh: lutfi)
20. Masukkan username untuk akun (Contoh: lutfi)
21. Masukkan password untuk user tadi (Contoh: 123lutfi-) dan masukkan verifikasi password untuk user yang sudah dimasukkan tadi
22. Pilih konfigurasi waktu (WIB: *Western*, WITA: *Central*, WIT: *Eastern*)
23. Pilih partition disks (Contoh: *Guide - use entire disks*)
24. Pilih *SCS13~~~*
25. Pilih *All files in one partition (Recommended for new users)*
26. Pilih *Finish partitioning and write changes to disks*
27. Pilih *Yes*
28. Jika muncul pop up konfigurasi package manager, pilih *No*
29. Jika muncul pop up konfigurasi package manager kedua (use a network mirror), pilih *Yes*
30. Jika muncul pilih Debian archive mirror country, pilih *Go Back*, lalu pilih *Yes*
31. Jika muncul pop up konfigurasi popularity-contest, pilih *Yes*
32. Pilih software, pastikan *Debian desktop environment* dan *...GNOME* terbintang (Cara memberi bintang: klik spasi)
33. Tunggu (Memerlukan waktu lebih lama)
34. Instal GRUB boot loader (Pilih *Yes*)
35. Pilih */dev/sda~~~*
36. Finish the installation (Pilih *Continue* untuk mereboot sistem)
37. Pilih *Debian GNU/Linux* (Opsional, jika tidak dienter akan otomatis memilih ini)
38. Selamat! Debian sudah terinstall hehe...
39. Klik user lalu masukkan password user, bukan root (Langkah 21)
40. Selamat!!! Anda sudah masuk ke desktop Debian eak
- NB: ~~~ = Keterangan pengganti kalimat lain

### Soal
1. Presentasi Langkah Demi Langkah Tentang Siklus CPU (Fetch, Decode, Execute)

![awal](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/c63c4ab1-69cd-4570-b721-fabc354def43)
- Inisialisasi awal

   1. Proses 1
      ![fetch1](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/cd2c4530-ac2b-43ab-9967-66f9d1f65d4b)
      ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/d272bd36-dec8-4203-8fa0-ec4629a783d1)
      - Fetch
         - Programme Counter mulai dari 0 (alamat instruksi di memori)
         - CPU mengambil instruksi (LOAD 6) dari memori, kemudian valuenya diletakkan di Instruction Register
   
   
      ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/67f20e6a-bc12-426b-9369-3edd3ea07551)
      - Decode
         - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami
   
   
      ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/faf96c11-8023-4123-9051-8fd260753c05)
      - Execute
         - LOAD 6 yang berarti CPU menampilkan value dari memori yang beralamat 6 ke accumulator

   2. Proses 2
      ![fetch](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/6ed3ad0f-b6aa-49b5-b7f5-86ee6ce6991f)
      ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/cae6bec7-2500-4468-840e-7e14cf9c8c4d)
      - Fetch
         - Programme Counter increment (bertambah 1) menjadi 1
         - CPU mengambil instruksi (ADD 7) dari memori, kemudian valuenya diletakkan di Instruction Register
   
      ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/6beb242c-93d7-4a3e-9a9f-25f672f67a5c)
      - Decode
         - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami
       
      ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/d06ff3a6-d4a3-478f-957f-7b7f0f706321)
      - Execute
         - CPU menambah value dari RAM address 7 ke accumulator

   3. Proses 3
      ![fetch](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8ab41546-7263-4801-87fc-2aafc2be0270)
      ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/92d12042-c086-4d9c-9f99-c0f22ad68cc2)
      - Fetch
         - Programme Counter increment (bertambah 1) menjadi 2
         - CPU mengambil instruksi (STORE 6) dari memori, kemudian valuenya diletakkan di Instruction Register

      ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/23961c56-284c-4591-877a-ea0c134b1220)
      - Decode
         - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami
    
      ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/a8dd6525-e944-4690-b6f7-985931bfba89)
      - Execute
         - CPU memasukkan value dari accumulator ke RAM address 6

   4. Proses 4
      ![fetch](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/892016a0-596b-4cba-b7d1-8e53c5ca8a78)
      ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8e1602b8-54bc-4535-ad36-e5bc8a8c253a)
      - Fetch
         - Programme Counter increment (bertambah 1) menjadi 3
         - CPU mengambil instruksi (JUMP 1) dari memori, kemudian valuenya diletakkan di Instruction Register

      ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/1a2977d5-aa20-4387-946f-7153fee3db55)
      - Decode
         - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami
    
      ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/aaae3365-0713-4a47-8b10-286ab45671b5)
      - Execute
         - CPU kembali mengakses ke RAM address 1

   
- Proses fetch->decode->execute terjadi berulang-ulang (looping) sampai perintah selesai dieksekusi semuanya.
- Setiap proses terjadi dalam satu kali jentikan jari.

- Peran bahasa pemrograman
   - Sebagai alat untuk menulis instruksi yang dimengerti oleh manusia
- Peran compiler
   - Sebagai alat untuk menerjemahkan source code dalam bahasa pemrograman tingkat tinggi menjadi kode mesin yang dapat dipahami oleh CPU
- Peran sistem operasi
   - Sebagai perantara antara program aplikasi dan perangkat keras komputer dan menyediakan lingkungan eksekusi yang diperlukan

2. Baca dan Pahami
   
3. Git Clone dan Melakukan Percobaan

![1](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/02f8cf47-9d5a-4082-814c-359918e5198e)
- Melakukan clone ke https://github.com/ferryastika/flops-iops

![2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/d9ae298b-f734-4215-bd66-8b14a73e9a24)
- Cek file/direktori yang tersedia

![3](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/c44101ec-06fc-4c3b-a951-78ffbf7d8d02)
- Masuk ke direktori flops-iops

![4](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8415d6ac-12cf-48ae-9af1-463f8df64456)
```fish
$ make
```

![5](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/a2eecbfa-2ebe-48ff-867d-d352ba5d35c5)
```fish
$ make clean
```

![6](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/5dedc913-d75b-4682-b4eb-ad6ebdf48130)
```fish
$ sudo make install
```

![7](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/dfc6193a-eb61-43dc-86c7-73cc87d64758)
```fish
$ sudo make uninstall
```

![8](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/17292880-b3a8-41d6-bcf4-6ffa3d92f7ab)
- Percobaan 1

![9](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/3b73469d-97ed-4167-8b3d-3fe61d6cbce9)
- Percobaan 2

![10](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/17499c54-ff26-4fb3-8bff-955a2fb63309)
- Percobaan 3

![11](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/e87fd1b5-eac1-449b-ba96-4993862d6fb1)
- Percobaan 4

![12](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/d837d67d-340f-4246-a6b1-82efadc0e980)
- Percobaan 5
```sh
$ iops64 1
$ flops64 1
```
Keterangan : 1 = Jumlah CPU VM Debian

- Hasil perbandingan IOPS dan FLOPS dengan teman
![iops-flops](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/89b9a4f5-f21f-4ecd-8a32-ef1b00aa2ef8)

- Analisa hasil percobaan dan kesimpulan IOPS dan FLOPS
   - Iops mengukur jumlah integer yang dapat dilakukan oleh sistem dalam satu detik
   - Flops mengukur jumlah floating-point yang dapat dilakukan oleh sistem dalam satu detik
   - 64 menunjukkan bahwa pengukuran ini berlaku untuk sistem 64 bit

4. Instalasi gcc, make, dan git

![1](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/5c8a8233-565e-42d7-987b-c8f842b12b8b)
- Masuk ke terminal Debian

![2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/6819bb32-0179-48fd-a05f-93f827d3d6fb)
- Login sebagai super user

![3](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/21f13ff2-a1dd-4526-aa14-d5904fec43d6)
- Install gcc

![4](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/e8a28ac1-b52a-4d9c-9e2c-baa315f8f1df)
- Install make

![5](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/89d18ce0-1663-4d27-8f40-66b65cf7276d)
- Install git

### Perbedaan Swapping dan Paging
- Swapping:
   - Menggeser seluruh proses antara RAM dan penyimpanan sekunder.
   - Mengalokasikan ruang untuk proses secara keseluruhan.
   - Lebih lambat karena melibatkan transfer data besar antara RAM dan disk.

- Paging:
   - Memecah memori menjadi unit-unit kecil yang disebut halaman.
   - Hanya memindahkan halaman yang sedang digunakan antara RAM dan disk.
   - Lebih efisien karena hanya memindahkan sebagian kecil data pada suatu waktu.


## Tugas 4
### Tugas Pendahuluan
1.	Apa yang dimaksud redirection?
- Redirection adalah pembelokan, yaitu untuk mengalihkan file descriptor dari 0, 1, dan 2
2.	Apa yang dimaksud pipeline?
- Pipeline adalah alat komunikasi antar proses, yang menghubungkan proses 1 dengan proses 2
3.	Apa yang dimaksud perintah di bawah ini:
- echo, cat, more, sort, grep, wc, cut, uniq
- echo untuk mengisi file
- cat untuk mengisi kemudian menampilkan isi file
- more untuk menampilkan isi lebih detail dari suatu folder
- sort untuk mengurutkan masukannya berdasarkan urutan ASCII
- grep untuk menyaring dan menampilkan baris-baris yang mengandung pola tertentu
- wc untuk menghitung jumlah baris, kata, dan karakter dari baris-baris yang masukan
- cut untuk mengambil kolom tertentu dari baris-baris masukannya
- uniq untuk menghilangkan baris-baris berurutan yang mengalami duplikasi

### Percobaan
1.	Percobaan 1 : File descriptor
      1)	Output ke layar (standar output), input dari system (kernel)
      ![1](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/974a67e5-cd13-4c46-b66e-40c607b54fab)
      ```
      $ ps untuk mendeskripsikan file
      ```
      2)	Output ke layar (standar output), input dari keyboard (standard input)
      ![2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/e0c22f3e-fad9-47a2-beb1-60626da6c4a3)
      ```
      $ cat untuk menulis pesan
      ```
      3)	Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
      ![3](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/cd0760f2-538e-40ba-a3b7-ef48881d7591)

      ```
      $ mkdir untuk membuat direktori/folder baru
      ```

2.	Percobaan 2 : Pembelokan (redirection)
      1)	Pembelokan standar output
      ![4](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/9d281eab-78ac-4342-bc04-87e6514bef10)
      ```
      $ cat 1> (nama file) untuk mengisi file
      ```
      2)	Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
      ![5](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/9aa2cb9d-29fd-43e0-9b4f-83fd079aeafe)
      ```
      $ cat 0< (nama file) atau cat (nama file) untuk melihat isi file
      ```
      3)	Pembelokkan standar error untuk disimpan di file
      ![6](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/42afa425-5d8d-42e0-b817-77bdb402a2e3)
      ```
      $ mkdir (nama direktori yang sudah ada) 2> (nama file) untuk menampilkan error
      ```
      4)	Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1
      ![7](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/07c1b2f8-b7f1-4f64-911c-244d7b1ddca8)
      ```
      Notasi 2>&1 = 2> untuk pembelokan standar error
      ```
      5)	Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
      ![8](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/ba589e4d-a5c3-43ca-9be5-f93f4ab35667)
      ```
      Notasi 1>&2 = &2 untuk pembelokan standar error
      ```
      6)	Notasi >> (append)
      ![9](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/cad39dd3-3ddd-4723-bccd-aa77f309238b)
      ```
      Notasi > untuk mengisi file, notasi >> untuk menambahkan isi file
      ```
      7)	Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup            harus diberikan pada awal baris
      ![10](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/6a69b8c9-bd6d-47ca-b51b-374b964dc5d1)
      ```
      $ cat <<++ diakhiri ++ = $ cat <<%%% diakhiri %%% untuk menulis beberapa baris tulisan
      ```
      8)	Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti        menyelipkan input dari keyboard
      ![11](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/e20ca610-a55f-4783-9627-35e13573ba31)
      ```
      Notasi – untuk menampilkan file
      ```

3.	Percobaan 3 : Pipa (pipeline)
      1)	Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
      ![12](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/33786e35-4388-45b5-a428-1e929772da7c)
      ![13](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8b2fa534-b468-4f0d-afc8-5507ebb0d033)
      ```
      Operator | untuk mengeksekusi proses dengan melewati data langsung ke data lainnya (Tidak semua hasil dicapture)
      ```
      2) Untuk membelokkan standart output ke file, digunakan operator ">"
      ![14](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/c4289ad9-6df2-4217-b403-80ce75c22d8a)
      3) Untuk menambahkan output ke file digunakan operator ">>"
      ![15](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/b65f8a8c-ce5d-405f-9206-fce075151423)
      4) Untuk membelokkan standart input digunakan operator "<"
      ![16](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/14949b1c-2d0d-42b8-bf4d-6c05780f15e6)
      5) Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
      ![17](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/87ac8238-2573-4e7e-a84e-ddb57bc6cea4)

4.	Percobaan 4 : Filter
      1)	Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
      ![18](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/b5e074a8-15ae-4c72-92cf-0c8c9dd83817)
      ![19](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/871db444-fa56-4104-b49b-49f908a3e653)
      ```
      Operator | bisa dikombinsikan untuk membuat fungsi lebih kompleks (Ini adalah percobaan kedua, karena yang pertama ada kesalahan penulisan  data)
      ```

### Latihan
1.	Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standar output ke file baru.
![20](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/327669ac-eb7d-40c9-ae8b-19a78de084d4)

2.	Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standar output ke file baru tanpa menghapus file baru sebelumnya.
![21](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/31db456f-3a3c-4c8e-a144-c9a810c8ec43)

3.	Urutkan file baru dengan cara membelokkan standar input.
![22](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/3b587231-2bea-4bf7-b38a-8001750f86e4)

4.	Urutkan file baru dengan cara membelokkan standar input dan standar output ke file baru.urut.
![23](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/4a9fe48d-86e6-440c-807c-809461bed2e3)
![24](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/5c00c1e7-175a-4212-b469-d113738eea82)
![25](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8bade487-616e-4199-bd8d-bd6c2f302172)
![26](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/e5758fd7-cc9b-4ce2-accc-7082f54934fd)
![27](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/aa8e5463-bc14-4a4d-9a59-c5bd1df54e79)

5.	Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standar error ke file rmdirerror.txt.
![28](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/6d72710a-033e-4db4-b70a-486210fe0098)
Notasi 2> untuk pembelokan standar error

7.	Urutkan kalimat berikut:
```
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung
```
Dengan menggunakan notasi here document (<@@@ ...@@@)
![29](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/af9a2dae-6693-4868-bbc1-779ee506191d)
Kombinasi here document **<<@@@ ...@@@** dan **| sort** menghasilkan output dengan abjad yang urut

7.	Hitung jumlah baris, kata, dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
![30](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/943f4359-fc64-404f-a28c-fbf5f5702bdf)
Kombinasi antara | wc dan notasi > untuk memasukkan data jumlah baris, kata, dan karakter ke file lain
8.	Gunakan perintah di bawah ini dan perhatikan hasilnya.
```
$ cat > hello.txt
dog cat
$ cat duck
dog chicken
chicken duck
chicken cat
dog duck
[Ctrl-d]
$ cat hello.txt | sort | uniq
$ cat hello.txt | grep “dog” | grep -v “cat”
```
![31](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/ac2ea3b1-0d70-40d7-ac18-2805f2f98f6c)
Command ini berisi pemasukan data ke file hello.txt yang kemudian diurutkan dan menampilkan data, yang mengandung kata “dog”, tetapi tidak mengandung kata “cat”


## Tugas 5
### Hubungan Arsitektur CPU dengan Arsitektur OS
1 Sederhananya
  - Arsitektur CPU: Menentukan bagaimana prosesor (CPU) bekerja, termasuk instruksi yang dapat dieksekusi, cara akses memori, dan mode operasi. Contoh arsitektur CPU termasuk x86, ARM, dan MIPS.
  - Arsitektur OS: Merupakan struktur dan fungsi dari sistem operasi, yang mengatur cara penggunaan sumber daya komputer seperti memori, CPU, dan perangkat keras lainnya. Sistem operasi seperti Windows, macOS, dan Linux adalah contoh arsitektur OS.

2. Kompleksnya
  - Kompatibilitas Instruksi: Sistem operasi harus dapat memahami dan menggunakan instruksi yang didukung oleh arsitektur CPU yang digunakan pada sistem tersebut.
  - Manajemen Sumber Daya: Sistem operasi bertanggung jawab untuk mengelola sumber daya komputer, termasuk alokasi memori, penjadwalan proses, dan manajemen perangkat keras. Ini bergantung pada cara arsitektur CPU menyediakan akses ke sumber daya tersebut.
  - Driver Perangkat: Sistem operasi menyediakan driver perangkat untuk berkomunikasi dengan perangkat keras. Driver ini harus cocok dengan arsitektur CPU tertentu dan memahami cara kerja perangkat keras tersebut.
  - Optimasi Kinerja: Sistem operasi dapat melakukan optimasi kinerja yang disesuaikan dengan karakteristik arsitektur CPU tertentu, seperti pengaturan jadwal proses, manajemen cache, atau penggunaan instruksi-instruksi spesifik.

### Fork
1. C Program Forking Separate Process
   ```
   #include <sys/types.h>
   #include <stdio.h>
   #include <unistd.h>
   
   int main() {
       pid_t pid;
       
       /* fork a child process */
       pid = fork();
       
       if(pid < 0) {
           /* error occurred */
           fprintf(stderr, "Fork Failed");
           return 1;
       } else if(pid == 0) {
           /* child process */
           execlp("/bin/ls", "ls", NULL);
       } else {
           /* parent process */
           /* parent will wait for the child to complete */
           wait(NULL);
           printf("Child Complete");
       }
       
       return 0;
   }
   ```
   Hasil : Error

2. Creating a Separate Process via Windows API
   ```
   #include <stdio.h>
   #include <windows.h>
   
   int main(VOID) {
   	STARTUPINFO si;
   	PROCESS_INFORMATION pi;
   	
   	/* allocate memory */
   	ZeroMemory(&si, sizeof(si));
   	si.cb = sizeof(si);
   	ZeroMemory(&pi, sizeof(pi));
   	
   	/* create child process */
   	if(!CreateProcess(NULL,
   	/* use command line */
   	"C:\\WINDOWS\\system32\\mspaint.exe", /* command */
   	NULL, /* don't inherit process handle */
   	NULL, /* don't inherit thread handle */
   	FALSE, /* disable handle inheritance */
   	0, /* no creation flags */
   	NULL, /* use parent's environment block */
   	NULL, /* use parent's existing directory */
   	&si,
   	&pi))
   	{
   		fprintf(stderr, "Create Process Failed");
   		return -1;
   	}
   	/* parent will wait the child to complete */
   	WaitForSingleObject(pi.hProcess, INFINITE);
   	printf("Child Complete");
   	
   	/* close handles */
   	CloseHandle(pi.hProcess);
   	CloseHandle(pi.hThread);
   }
   ```
   Hasil:
   ![image](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/fd0656f7-874d-42cb-8718-cb3f6e5197ce)

### Jalankan Orphan dan Zombie

### Producer dan Consumer Problem









