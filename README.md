# AELX

AELX adalah sebuah perangkat lunak baris perintah yang memungkinkan Anda untuk membaca dan memproses file konfigurasi `.aelx`. Perangkat lunak ini mendukung ekstraksi pasangan kunci-nilai dari file konfigurasi dan menyediakan opsi untuk mengeluarkan data dalam format JSON atau sebagai variabel lingkungan (environment variables).

## Instalasi

Untuk menginstal AELX, ikuti langkah-langkah berikut:

1. Clone repositori AELX:

   ```shell
   git clone https://github.com/refaldyrk/aelx.git
   ```

2. Beralih ke direktori proyek:

   ```shell
   cd aelx
   ```
3. Jalankan Aelx:

   ```shell
   aelx --f config.aelx -k hello
   ```

## Penggunaan

Jalankan perintah `aelx` dengan flag-flag berikut:

- `-k`: Kunci yang ingin Anda ambil nilainya dari file konfigurasi.
- `--f`: Nama file `.aelx` yang ingin Anda baca.
- `-j`: Opsi opsional untuk mengeluarkan data dalam format JSON. Default: `false`.
- `--o`: Opsi opsional untuk menentukan nama file keluaran dalam format JSON. Default: `aelx.json`.
- `-e`: Opsi opsional untuk mengeluarkan data sebagai variabel lingkungan. Default: `false`.

### Contoh Penggunaan

1. Mengambil nilai kunci tertentu dari file konfigurasi:

   ```shell
   aelx -k <nama-kunci> --f <nama-file.aelx>
   ```

   Contoh:
   ```shell
   aelx -k hello --f config.aelx
   ```

2. Mengeluarkan data dalam format JSON:

   ```shell
   aelx -k <nama-kunci> --f <nama-file.aelx> -j true
   ```

   Contoh:
   ```shell
   aelx -k hello --f config.aelx -j true
   ```

3. Mengeluarkan data dalam format JSON dengan nama file kustom:

   ```shell
   aelx -k <nama-kunci> --f <nama-file.aelx> -j true --o <keluaran.json>
   ```

   Contoh:
   ```shell
   aelx -k hello --f config.aelx -j true --o output.json
   ```

4. Mengeluarkan data sebagai variabel lingkungan:

   ```shell
   aelx -k <nama-kunci> --f <nama-file.aelx> -e true
   ```

   Contoh:
   ```shell
   aelx -k hello --f config.aelx -e true
   ```

## Format File `.aelx`

File `.aelx` menggunakan format yang khusus. Berikut adalah contoh format file `.aelx` yang didukung:

```
project: start|
[kunci-1] nilai-1|
[kunci-2] nilai-2|
[kunci-3] nilai-3|
project: end|
```

Pastikan file `.aelx` mengikuti format tersebut untuk memastikan ekstraksi data yang benar.

## Contoh File Konfigurasi `.aelx`

Berikut adalah contoh isi dari file konfigurasi `.aelx`:

```
project: start|
hello[world]|
lorem[ipsum]|
project: end|
```

Dalam contoh ini, terdapat dua pasangan kunci-nilai:

- Kunci: `hello`, Nilai: `world`
- Kunci: `lorem`, Nilai: `ipsum`

Anda dapat menggunakan perintah `aelx` untuk mengambil nilai dari kunci-kunci ini atau melakukan ekstraksi data yang sesuai dengan kebutuhan Anda.