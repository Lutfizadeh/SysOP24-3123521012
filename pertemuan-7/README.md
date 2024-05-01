# Tugas 7
## Tugas Pendahuluan
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

## Percobaan
1.	Percobaan 1 : File descriptor
      1)	Output ke layar (standar output), input dari system (kernel)
      ![](assets/percobaan/1.png)
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

## Latihan
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
