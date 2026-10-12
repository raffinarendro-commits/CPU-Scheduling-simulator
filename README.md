# CPU Scheduling Simulator

Simulator penjadwalan CPU berbasis web untuk memvisualisasikan cara kerja algoritma **FCFS**, **SJF**, **Priority**, dan **Round Robin**.

Final Project Mata Kuliah **Sistem Operasi** – **Kelompok 1**.

> Proyek ini adalah simulator konsep Sistem Operasi, bukan implementasi kernel atau sistem operasi sungguhan.

## Deskripsi

Penjadwalan CPU menentukan proses mana yang berhak memakai CPU berikutnya. Karena terjadi di dalam kernel, prosesnya tidak terlihat. Simulator ini memperlihatkannya langkah demi langkah dalam bentuk Gantt Chart, status proses, dan perhitungan metrik, sehingga perbedaan antaralgoritma bisa diamati dan dibandingkan pada data yang sama.

Alur kerjanya: **Input → Process/Algorithm → Simulation → Visualization → Result → Analysis**.

## Fitur

- **Input proses:** PID, Arrival Time, Burst Time, dan Priority. Proses bisa ditambah, diubah, dan dihapus (maksimal 10).
- **Empat algoritma:**
  - FCFS
  - SJF (non-preemptive)
  - Priority (non-preemptive, angka lebih kecil = prioritas lebih tinggi)
  - Round Robin (quantum dapat diatur)
- **Visualisasi:** Gantt Chart yang tumbuh per satuan waktu, sumbu waktu, ready queue, serta status proses (NEW, READY, RUNNING, TERMINATED) dan sisa burst.
- **Metrik:** Waiting Time, Turnaround Time, dan Response Time per proses beserta rata-ratanya.
- **Mode simulasi:** Step, Auto play (dapat dijeda), Selesaikan, dan Reset.
- **3 skenario pengujian bawaan:**
  1. Semua proses tiba bersamaan
  2. Arrival berbeda
  3. Ada CPU idle
- **Perbandingan algoritma:** tabel rata-rata metrik keempat algoritma untuk data yang sedang dipakai.
- **Analisis teori:** penjelasan singkat algoritma yang dipilih.
- Tampilan responsif, mendukung tema terang dan gelap.

## Rumus Perhitungan

| Metrik | Rumus |
|---|---|
| Turnaround Time | Waktu selesai − Arrival |
| Waiting Time | Turnaround − Burst |
| Response Time | Waktu pertama dapat CPU − Arrival |
| Rata-rata | Jumlah nilai semua proses ÷ jumlah proses |

Perhitungan dilakukan di fungsi `simulate()` pada `index.html`.

## Cara Menjalankan

Tidak perlu instalasi, framework, maupun koneksi internet.

1. Unduh atau clone repository ini:
   ```bash
   git clone https://github.com/raffinarendro-commits/CPU-Scheduling-simulator.git
   ```
2. Buka berkas HTML (`index.html` atau `cpu_scheduling_simulator_rapi.html`) dengan browser modern (Chrome, Edge, atau Firefox), misalnya dengan klik dua kali.
3. Pilih skenario atau ubah data proses, pilih algoritma, lalu gunakan **Step** atau **Auto play**.

Demo online (jika GitHub Pages diaktifkan): https://raffinarendro-commits.github.io/CPU-Scheduling-simulator/

## Cara Penggunaan Singkat

1. Pilih **Skenario** atau isi tabel proses sendiri.
2. Pilih **Algoritma**. Untuk Round Robin, isi **Quantum**.
3. Klik **Step** untuk maju satu satuan waktu, atau **Auto play** untuk berjalan otomatis.
4. Lihat hasil dan perbandingan di bagian **Hasil dan analisis**.
5. Klik **Reset** untuk mengulang dari waktu 0.

## Struktur Kode

Seluruh aplikasi ada dalam satu berkas HTML (HTML + CSS + JavaScript murni).

| Bagian / fungsi | Peran |
|---|---|
| `SCENARIOS`, `THEORY` | Data skenario uji dan penjelasan teori |
| `simulate()` | Menjalankan algoritma, menghasilkan segmen Gantt dan metrik |
| `runNonPreemptive()`, `pickNext()` | Logika FCFS, SJF, dan Priority |
| `runRoundRobin()` | Logika Round Robin |
| `getState()` | Status proses pada waktu tertentu |
| `render*()` | Menggambar Gantt Chart, status, hasil, dan perbandingan |
| `stepForward()`, `toggleAutoPlay()`, `resetSimulation()` | Kontrol simulasi |

## Batasan

- SJF dan Priority berupa versi non-preemptive.
- Waktu dalam satuan diskrit, context switch dianggap nol.
- Setiap proses hanya punya satu CPU burst, tanpa operasi I/O.

## Anggota Kelompok 1

| No | Nama | NIM | Peran |
|---|---|---|---|
| 1 | Deanova Rasya Al-Hasyim | 2504030007 | System Analyst |
| 2 | Raffi Narendro | 2504030029 | Programmer / Algorithm |
| 3 | Irvan Ardiansah | 2504030043 | UI / Visualization |
| 4 | Khaidir Asri | 2504030083 | Testing & Documentation |

Mata Kuliah Sistem Operasi – Teknik Informatika, Universitas Islam Syekh-Yusuf – 2026
