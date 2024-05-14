# Tugas 10
## Perbedaan Concurrent dan Parallel
Secara sederhana:
- Concurrent: Beberapa tugas berjalan pada waktu yang bersamaan, tetapi mungkin tidak secara benar-benar serentak. Mereka bisa bergantian dijalankan, dan sistem mengalihkan perhatian dari satu tugas ke yang lain.
  - Contoh: Mengerjakan beberapa tugas dalam satu waktu, seperti menulis email sambil mendengarkan musik. Anda tidak melakukan keduanya secara persis pada saat yang sama, tetapi bergantian di antara mereka.
- Parallel: Beberapa tugas benar-benar berjalan secara serentak, pada waktu yang bersamaan, mungkin di prosesor yang berbeda.
  - Contoh: Mengerjakan proyek bersama dengan rekan tim, di mana masing-masing dari Anda bekerja pada bagian yang berbeda secara bersamaan. Setiap orang mengambil bagian tertentu dan bekerja pada bagian tersebut pada saat yang bersamaan.
- Gambar Ilustrasi:
- ![](assets/concurrent-parallel.jpg)
- Sumber: https://devopedia.org/concurrency-vs-parallelism

## Perbedaan Concurrent dan Serial
Secara sederhana:
- Concurrent: Beberapa tugas berjalan pada waktu yang bersamaan, tetapi mungkin tidak benar-benar serentak. Mereka bisa bergantian dijalankan, dan sistem mengalihkan perhatian dari satu tugas ke yang lain.
  - Contoh: Melakukan beberapa tugas dalam satu waktu, tetapi mungkin secara bergantian. Misalnya, membaca email sambil mendengarkan musik. Anda mungkin beralih di antara membaca email dan mendengarkan musik, tetapi keduanya berjalan pada saat yang bersamaan.
- Serial: Tugas-tugas dieksekusi satu per satu, berurutan, tanpa adanya tumpang tindih. Satu tugas harus menunggu penyelesaian tugas sebelumnya sebelum dapat dijalankan.
  - Contoh: Mengerjakan satu tugas pada satu waktu. Misalnya, mencuci piring, kemudian membersihkan meja, dan seterusnya.
- Gambar Ilustrasi:
- ![](assets/concurrent-serial.jpg)
- Sumber: Internet
