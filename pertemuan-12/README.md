# Tugas 10
## Threads
Terjemahan soal dan jawaban
1. Berikan tiga contoh pemrograman di mana multithreading memberikan kinerja yang lebih baik daripada solusi berulir tunggal.
   - Jawaban:
     - Server Web yang melayani setiap permintaan dalam utas terpisah.
     - Aplikasi yang diparalelkan seperti perkalian matriks di mana bagian matriks yang berbeda dapat dikerjakan secara paralel.
     - Program GUI interaktif seperti debugger di mana sebuah thread digunakan untuk memonitor input pengguna, thread  lain mewakili aplikasi yang sedang berjalan, dan thread ketiga memonitor kinerja.

2. Apa saja dua perbedaan antara thread tingkat pengguna dan thread tingkat kernel? Dalam kondisi apa salah satu jenis lebih baik daripada yang lain?
   - Jawaban:
     - Thread tingkat pengguna tidak diketahui oleh kernel, sedangkan kernel mengetahui thread kernel.
     - Pada sistem yang menggunakan pemetaan M:1 atau M:N, thread pengguna dijadwalkan oleh pustaka thread dan kernel menjadwalkan thread kernel.
     - Thread kernel tidak perlu diasosiasikan dengan sebuah proses, sedangkan setiap thread pengguna merupakan bagian dari sebuah proses. Kernel thread umumnya lebih mahal untuk dipelihara daripada user thread karena harus direpresentasikan dengan struktur data kernel.

3. Jelaskan tindakan yang diambil oleh kernel untuk melakukan context- switch di antara thread tingkat kernel.
   - Jawaban:
     - Peralihan konteks antara thread kernel biasanya membutuhkan penyimpanan nilai register CPU dari thread yang dialihkan dan mengembalikan register CPU dari thread baru yang dijadwalkan.

4. Sumber daya apa yang digunakan saat thread dibuat? Apa perbedaannya dengan sumber daya yang digunakan saat proses dibuat?
   - Jawaban:
     - Karena thread lebih kecil daripada proses, pembuatan thread biasanya menggunakan sumber daya yang lebih sedikit daripada pembuatan proses. Membuat proses membutuhkan alokasi blok kontrol proses (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori, daftar file yang terbuka, dan variabel lingkungan. Mengalokasikan dan mengelola peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat thread pengguna atau kernel melibatkan pengalokasian struktur data yang kecil untuk menampung set register, stack, dan prioritas.

5. Asumsikan bahwa sistem operasi memetakan thread tingkat pengguna ke kernel menggunakan model banyak-ke-banyak dan pemetaan dilakukan melalui LWP. Lebih jauh lagi, sistem ini memungkinkan pengembang untuk membuat thread waktu nyata untuk digunakan dalam sistem waktu nyata. Apakah perlu untuk mengikat thread waktu nyata ke LWP? Jelaskan.
   - Jawaban:
     - Ya, pengaturan waktu sangat penting untuk aplikasi real-time. Jika sebuah thread ditandai sebagai real-time tetapi tidak terikat pada LWP, thread tersebut mungkin harus menunggu untuk dilampirkan ke LWP sebelum berjalan. Pertimbangkan jika sebuah thread real-time sedang berjalan (terikat pada LWP) dan kemudian mulai memblokir (misalnya harus melakukan I/O, telah didahului oleh thread real-time dengan prioritas yang lebih tinggi, sedang menunggu kunci pengecualian bersama, dll.) Saat thread real-time diblokir, LWP yang terikat padanya telah ditugaskan ke thread lain. Ketika thread real-time telah dijadwalkan untuk berjalan kembali, thread tersebut harus menunggu terlebih dahulu untuk diikat ke LWP. Dengan mengikat LWP ke thread real-time, Anda memastikan bahwa thread tersebut dapat berjalan dengan penundaan minimal setelah dijadwalkan.
