# Tugas 9
## Perbedaan CISC dan RISC
- CISC (Complex Instruction Set Computing) adalah arsitektur komputer yang memiliki komponen sedikit dan cara memprogram yang lebih kompleks
- RISC (Reduced Instruction Set Computing) adalah arsitektur komputer yang memiliki komponen banyak dan cara memprogram yang lebih sederhana

## Hubungan Arsitektur CPU dengan Arsitektur OS
1. Sederhananya
  - Arsitektur CPU: Menentukan bagaimana prosesor (CPU) bekerja, termasuk instruksi yang dapat dieksekusi, cara akses memori, dan mode operasi. Contoh arsitektur CPU termasuk x86, ARM, dan MIPS.
  - Arsitektur OS: Merupakan struktur dan fungsi dari sistem operasi, yang mengatur cara penggunaan sumber daya komputer seperti memori, CPU, dan perangkat keras lainnya. Sistem operasi seperti Windows, macOS, dan Linux adalah contoh arsitektur OS.

2. Kompleksnya
  - Kompatibilitas Instruksi: Sistem operasi harus dapat memahami dan menggunakan instruksi yang didukung oleh arsitektur CPU yang digunakan pada sistem tersebut.
  - Manajemen Sumber Daya: Sistem operasi bertanggung jawab untuk mengelola sumber daya komputer, termasuk alokasi memori, penjadwalan proses, dan manajemen perangkat keras. Ini bergantung pada cara arsitektur CPU menyediakan akses ke sumber daya tersebut.
  - Driver Perangkat: Sistem operasi menyediakan driver perangkat untuk berkomunikasi dengan perangkat keras. Driver ini harus cocok dengan arsitektur CPU tertentu dan memahami cara kerja perangkat keras tersebut.
  - Optimasi Kinerja: Sistem operasi dapat melakukan optimasi kinerja yang disesuaikan dengan karakteristik arsitektur CPU tertentu, seperti pengaturan jadwal proses, manajemen cache, atau penggunaan instruksi-instruksi spesifik.

## Fork
Sebelum melakukan fork serta menjalankan orphan dan zombie, kita harus menginstall g++ dahulu.
![1](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/f50d3e7e-6720-4346-8b13-a95f7adf89d6)
```
$ su root
$ sudo apt update
$ sudo apt upgrade
$ sudo apt instal g++
```

Kemudian login kembali sebagai user
![2](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/8ca8bc3e-a53d-4063-b161-f8d4f639f39f)
```
$ login [username]
```

1. Fork 1
   - Masuk ke compiler
   ```
   $ nano [namafile].cpp
   ```
   
   - Lalu masukkan kode di bawah
   ```
   using namespace std;
   
   #include <iostream>
   #include <sys/types.h>
   #include <unistd.h>
   
   
   /* getpid() adalah system call yg dideklarasikan pada unistd.h.
   Menghasilkan suatu nilai dengan type pid_t.
   pid_t adalah type khusus untuk process id yg ekuivalen dg int
   */
   int main(void) {
   	pid_t mypid;
   	uid_t myuid;
   	for (int i = 0; i < 3; i++) {
   		mypid = getpid();
   		cout << "I am process " << mypid << endl;
   		cout << "My parent process ID is " << getppid() << endl;
   		cout << "The owner of this process has uid " << getuid()
   	<< endl;
   /* sleep adalah system call atau fungsi library
   yang menghentikan proses ini dalam detik
   */
   	sleep(3);
   	}
   return 0;
   }
   ```
   
   - Lalu simpan file dengan menekan ```Ctrl + X```
 
   - Ubah file .cpp menjadi .exe
   ```
   $ g++ [namafile].cpp -o [namafile].exe
   ```

   - Jalankan kodenya
   ```
   $ ./[namafile].exe
   ```
   
   - Hasil :
   ![3](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/48c28108-9f83-4660-b37c-81c4356971a6)

2. Fork 2
   - Masuk ke compiler
   ```
   $ nano [namafile].cpp
   ```
   
   - Lalu masukkan kode di bawah
   ```
   #include <iostream>
   #include <sys/types.h>
   #include <unistd.h>
   using namespace std;
   
   
   /* getpid() dan fork() adalah system call yg dideklarasikan
   pada unistd.h.
   Menghasilkan suatu nilai dengan type pid_t.
   pid_t adalah type khusus untuk process id yg ekuivalen dg int
   */
   int main(void) {
   	pid_t childpid;
   	int x = 5;
   	childpid = fork();
   
   	while (1) {
   		cout << "This is process ID" << getpid() << endl;
   		cout << "In this process the value of x becomes " << x << endl;	
   		sleep(2);
   		x++;
   	}
   	return 0;
   }
   ```
   
   - Lalu simpan file dengan menekan ```Ctrl + X```
 
   - Ubah file .cpp menjadi .exe
   ```
   $ g++ [namafile].cpp -o [namafile].exe
   ```

   - Jalankan kodenya
   ```
   $ ./[namafile].exe
   ```

   - Tekan ```Ctrl + C``` untuk menghentikan prosesnya
   
   - Hasil
   ![4](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/be62a078-0a63-4bd7-81b5-1db58ddc0177)


## Orphan dan Zombie
1. Orphan
   - Masuk ke compiler
   ```
   $ nano [namafile].c
   ```
   
   - Lalu masukkan kode di bawah
   ```
   #include <stdio.h>
   #include <sys/types.h>
   #include <unistd.h>
   
   int main()
   {
   	// fork() Create a child process
   
   	int pid = fork();
   	if (pid > 0)
   	{
   		//getpid() returns process id
   		// while getppid() will return parent process id
   		printf("Parent process\n");
   		printf("ID : %d\n\n",getpid());
   	}
   	else if (pid == 0)
   	{
   		printf("Child process\n");
   		// getpid() will return process id of child process
   		printf("ID: %d\n",getpid());
   		// getppid() will return parent process id of child process
   		printf("Parent -ID: %d\n\n",getppid());
   
   		sleep(10);
   
   		// At this time parent process has finished.
   		// So if u will check parent process id 
   		// it will show different process id
   		printf("\nChild process \n");
   		printf("ID: %d\n",getpid());
   		printf("Parent -ID: %d\n",getppid());
   	}
   	else
   	{
   		printf("Failed to create child process");
   	}
   	
   	return 0;
   }
   
   /* https://www.includehelp.com/c-programs/orphan-process.aspx */
   ```
   
   - Lalu simpan file dengan menekan ```Ctrl + X```
 
   - Ubah file .c menjadi .exe
   ```
   $ g++ [namafile].c -o [namafile].exe
   ```

   - Jalankan kodenya
   ```
   $ ./[namafile].exe
   ```

   - Tekan ```Ctrl + C``` untuk menghentikan prosesnya
   
   - Hasil
   ![5](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/b8dba801-5cfb-437f-afcd-ed9024edb78f)

2. Zombie
   - Masuk ke compiler
   ```
   $ nano [namafile].c
   ```
   
   - Lalu masukkan kode di bawah
   ```
   #include <stdlib.h>
   #include <sys/types.h>
   #include <unistd.h>
   int main ()
   {
     pid_t child_pid;
   
      /* Create child*/
     child_pid = fork ();
     if (child_pid > 0) {
   
       /* Parent process */
       sleep (60);
     }
     else {
   
       /*Child process. Exit immediately. */
       exit (0);
     }
     return 0;
   }
   
   /*ps -e -o pid,ppid,stat,cmd */
   ```

   - Lalu simpan file dengan menekan ```Ctrl + X```
 
   - Ubah file .c menjadi .exe
   ```
   $ g++ [namafile].c -o [namafile].exe
   ```

   - Jalankan kodenya
   ```
   $ ./[namafile].exe
   ```

   - Tekan ```Ctrl + C``` untuk menghentikan prosesnya
   
   - Hasil
   ![6](https://github.com/Lutfizadeh/SysOP24-3123521012/assets/67014058/14b0dc30-88aa-4ef6-b189-8f7d3390258a)
   

## Producer Consumer Problem
Producer Consumer Problem adalah permasalahan produsen-konsumen. Ini mencerminkan keadaan di dunia nyata, seperti saat terjadi interaksi antara produsen dan konsumen di pasar. Dengan memahami masalahnya, kita bisa menerapkan prinsip prinsip sinkronisasi di dalam program untuk mengatasi masalahnya.
