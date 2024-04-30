# Tugas 4
## Presentasi Langkah Demi Langkah Tentang Siklus CPU (Fetch, Decode, Execute)
![](assets/inisialisasiawal.jpg)
- Inisialisasi awal

1. Proses 1
   - ![fetch1](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/cd2c4530-ac2b-43ab-9967-66f9d1f65d4b)
   - ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/d272bd36-dec8-4203-8fa0-ec4629a783d1)
     - Fetch
       - Programme Counter mulai dari 0 (alamat instruksi di memori)
       - CPU mengambil instruksi (LOAD 6) dari memori, kemudian valuenya diletakkan di Instruction Register

     - ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/67f20e6a-bc12-426b-9369-3edd3ea07551)
       - Decode
         - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami

      ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/faf96c11-8023-4123-9051-8fd260753c05)
      - Execute
        - LOAD 6 yang berarti CPU menampilkan value dari memori yang beralamat 6 ke accumulator

2. Proses 2
   - ![fetch](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/6ed3ad0f-b6aa-49b5-b7f5-86ee6ce6991f)
   - ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/cae6bec7-2500-4468-840e-7e14cf9c8c4d)
     - Fetch
       - Programme Counter increment (bertambah 1) menjadi 1
       - CPU mengambil instruksi (ADD 7) dari memori, kemudian valuenya diletakkan di Instruction Register

   - ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/6beb242c-93d7-4a3e-9a9f-25f672f67a5c)
     - Decode
       - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami

   - ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/d06ff3a6-d4a3-478f-957f-7b7f0f706321)
     - Execute
       - CPU menambah value dari RAM address 7 ke accumulator

3. Proses 3
   - ![fetch](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8ab41546-7263-4801-87fc-2aafc2be0270)
   - ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/92d12042-c086-4d9c-9f99-c0f22ad68cc2)
     - Fetch
       - Programme Counter increment (bertambah 1) menjadi 2
       - CPU mengambil instruksi (STORE 6) dari memori, kemudian valuenya diletakkan di Instruction Register

   - ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/23961c56-284c-4591-877a-ea0c134b1220)
     - Decode
       - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami

   - ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/a8dd6525-e944-4690-b6f7-985931bfba89)
     - Execute
       - CPU memasukkan value dari accumulator ke RAM address 6

4. Proses 4
   - ![fetch](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/892016a0-596b-4cba-b7d1-8e53c5ca8a78)
   - ![fetch2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8e1602b8-54bc-4535-ad36-e5bc8a8c253a)
     - Fetch
       - Programme Counter increment (bertambah 1) menjadi 3
       - CPU mengambil instruksi (JUMP 1) dari memori, kemudian valuenya diletakkan di Instruction Register

   - ![decode](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/1a2977d5-aa20-4387-946f-7153fee3db55)
     - Decode
       - CPU menerjemahkan instruksi menjadi operasi yang dapat dipahami

   - ![execute](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/aaae3365-0713-4a47-8b10-286ab45671b5)
     - Execute
       - CPU kembali mengakses ke RAM address 1

- Proses fetch->decode->execute terjadi berulang-ulang (looping) sampai perintah selesai dieksekusi semuanya.
- Setiap proses terjadi dalam satu kali jentikan jari.

# Tugas 5
## Peran Bahasa Pemrograman, Compiler, dan Sistem Operasi
1. Peran bahasa pemrograman
   - Sebagai alat untuk menulis instruksi yang dimengerti oleh manusia
2. Peran compiler
   - Sebagai alat untuk menerjemahkan source code dalam bahasa pemrograman tingkat tinggi menjadi kode mesin yang dapat dipahami oleh CPU
3. Peran sistem operasi
   - Sebagai perantara antara program aplikasi dan perangkat keras komputer dan menyediakan lingkungan eksekusi yang diperlukan

# Tugas 6
## Instalasi Debian dan Melakukan FLOPS IOPS
### Install Debian
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
- NB: ~~~ = Keterangan pengganti kalimat lanjutan

### FLOPS IOPS
1. Instalasi gcc, make, dan git

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

2. Melakukan clone dan flops iops
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
