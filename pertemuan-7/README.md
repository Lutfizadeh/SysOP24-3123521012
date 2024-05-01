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
      ![](assets/percobaan/2.png)
      ```
      $ cat untuk menulis pesan
      ```
      3)	Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
      ![](assets/percobaan/3.png)

      ```
      $ mkdir untuk membuat direktori/folder baru
      ```

2.	Percobaan 2 : Pembelokan (redirection)
      1)	Pembelokan standar output
      ![](assets/percobaan/4.png)
      ```
      $ cat 1> (nama file) untuk mengisi file
      ```
      2)	Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
      ![](assets/percobaan/5.png)
      ```
      $ cat 0< (nama file) atau cat (nama file) untuk melihat isi file
      ```
      3)	Pembelokkan standar error untuk disimpan di file
      ![](assets/percobaan/6.png)
      ```
      $ mkdir (nama direktori yang sudah ada) 2> (nama file) untuk menampilkan error
      ```
      4)	Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1
      ![](assets/percobaan/7.png)
      ```
      Notasi 2>&1 = 2> untuk pembelokan standar error
      ```
      5)	Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
      ![](assets/percobaan/8.png)
      ```
      Notasi 1>&2 = &2 untuk pembelokan standar error
      ```
      6)	Notasi >> (append)
      ![](assets/percobaan/9.png)
      ```
      Notasi > untuk mengisi file, notasi >> untuk menambahkan isi file
      ```
      7)	Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup            harus diberikan pada awal baris
      ![](assets/percobaan/10.png)
      ```
      $ cat <<++ diakhiri ++ = $ cat <<%%% diakhiri %%% untuk menulis beberapa baris tulisan
      ```
      8)	Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti        menyelipkan input dari keyboard
      ![](assets/percobaan/11.png)
      ```
      Notasi – untuk menampilkan file
      ```

3.	Percobaan 3 : Pipa (pipeline)
      1)	Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
      ![](assets/percobaan/12.png)
      ![](assets/percobaan/13.png)
      ```
      Operator | untuk mengeksekusi proses dengan melewati data langsung ke data lainnya (Tidak semua hasil dicapture)
      ```
      2) Untuk membelokkan standart output ke file, digunakan operator ">"
      ![](assets/percobaan/14.png)
      3) Untuk menambahkan output ke file digunakan operator ">>"
      ![](assets/percobaan/15.png)
      4) Untuk membelokkan standart input digunakan operator "<"
      ![](assets/percobaan/16.png)
      5) Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
      ![](assets/percobaan/17.png)

4.	Percobaan 4 : Filter
      1)	Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
      ![](assets/percobaan/18.png)
      ![](assets/percobaan/19.png)
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
