# Tugas


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
1. Presentasi Langkah Demi Langkah Tentang Siklus CPU (Fetch, Decode, Execute)

![awal](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/c63c4ab1-69cd-4570-b721-fabc354def43)
- Inisialisasi awal


![fetch1](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/cd2c4530-ac2b-43ab-9967-66f9d1f65d4b)
![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/d272bd36-dec8-4203-8fa0-ec4629a783d1)
- Fetch
   - Programme Counter mulai dari 0 (alamat instruksi di memori)
   - CPU mengambil instruksi dari memori, kemudian valuenya diletakkan di Instruction Register


![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/67f20e6a-bc12-426b-9369-3edd3ea07551)
- Decode
   - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami


![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/faf96c11-8023-4123-9051-8fd260753c05)
- Execute
   - CPU menjalankan instruksi sesuai dengan operasinya. Dalam kasus ini instruksinya adalah LOAD 6 yang berarti CPU menampilkan value dari memori yang beralamat 6 ke accumulator

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
   - Iops mengukur jumlah operasi input/output yang dapat dilakukan oleh sistem dalam satu detik
   - Flops mengukur jumlah operasi jumlah aritmatika floating-point yang dapat dilakukan oleh sistem dalam satu detik
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
 
$ ps untuk mendeskripsikan file

2)	Output ke layar (standar output), input dari keyboard (standard input)
 
$ cat untuk menulis pesan

3)	Input dari keyboard dan output ke alamat internet
 
$ mail untuk mengirim email

4)	Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
 
$ mkdir untuk membuat direktori/folder baru

2.	Percobaan 2 : Pembelokan (redirection)
1)	Pembelokan standar output
 
$ cat 1> (nama file) untuk mengisi file

2)	Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
 
$ cat 0< (nama file) atau cat (nama file) untuk melihat isi file

3)	Pembelokkan standar error untuk disimpan di file
 
$ mkdir (nama direktori yang sudah ada) 2> (nama file) untuk menampilkan error

4)	Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1
 
Notasi 2>&1 = 2> untuk pembelokan standar error

5)	Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
 
Notasi 1>&2 = &2 untuk pembelokan standar error

6)	Notasi >> (append)
 
Notasi > untuk mengisi file, notasi >> untuk menambahkan isi file

7)	Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
 
$ cat <<++ diakhiri ++ = $ cat <<%%% diakhiri %%% untuk menulis beberapa baris tulisan

8)	Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
 
Notasi – untuk menampilkan file

9)	Untuk membelokkan standar output ke file, digunakan operator >
 
Notasi > untuk pembelokan standar output ke file

10)	Untuk menambahkan output ke file digunakan operator >>
 
Notasi >> untuk menambahkan isi file

11)	Untuk membelokkan standar input digunakan operator <
 
Notasi < untuk pembelokan standar input

12)	Pembelokkan standar input dan standar output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standar input dan output.
 
Kombinasi < dan > tidak boleh menggunakan nama file yang sama

3.	Percobaan 3 : Pipa (pipeline)
1)	Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
 
 
 
Operator | untuk mengeksekusi proses dengan melewati data langsung ke data lainnya
4.	Percobaan 4 : Filter
2)	Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
 
Operator | bisa dikombinsikan untuk membuat fungsi lebih kompleks (Ini adalah percobaan kedua, karena yang pertama ada kesalahan penulisan  data)
