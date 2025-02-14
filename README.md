```
import java.util.Scanner;
```
Baris ini mengimpor kelas Scanner dari paket java.util, yang digunakan untuk membaca input dari pengguna.

```
public class UAS2_1 {
```
Mendeklarasikan nama kelas publik bernama UAS2_1

```
public static void main(String[] args) {
```   
Metode utama yang akan di eksekusi saat program di jalankan

```
Scanner input = new Scanner(System.in);
```
Membuat objek Scanner untuk membaca input dari pengguna melalui konsol

```
String[] daftarMenu = {"Nasi Goreng", "Mie Goreng", "Roti Bakar", "Kentang Goreng", "Teh Tarik", "Cappucino", "Chocolate Ice"};
```
Mendeklarasikan dan menginisialisasi array daftarMenu dengan nama-nama menu.

```
int[] hargaMenu = {20000, 15000, 12000, 10000, 8000, 20000, 25000};
```
Mendeklarasikan dan menginisialisasi array hargaMenu dengan harga-harga menu.

```
int total = 0;
```
Variabel untuk menyimpan jumlah total pesanan yang sudah didaftarkan.

```
int pilihan;
```
Variabel untuk menyimpan pilihan menu dari pengguna.

```
String[] namaPesanan = new String[100];
int[] harga = new int[100];
int[] kuantitasBeli = new int[100];
```
Mendeklarasikan tiga array untuk menyimpan nama pesanan, harga pesanan, dan jumlah kuantitas pesanan.

```
System.out.println("=== Selamat Datang di Kafe ===");
```
Menampilkan pesan selamat datang.

```
System.out.println();
System.out.println("=== Menu ===");
for (int i = 0; i < daftarMenu.length; i++) {
    System.out.println((i + 1) + ". " + daftarMenu[i] + " - Rp" + hargaMenu[i]);
}
System.out.println();
```
Menampilkan daftar menu dan harga ke konsol.

```
do {
```
Memulai blok do-while yang akan berjalan sampai pilihan menu adalah 4

```
System.out.println("=== Menu Utama ===");
System.out.println("1. Tambah Pesanan");
System.out.println("2. Tampilkan Data Pesanan");
System.out.println("3. Hitung Total Biaya");
System.out.println("4. Selesai");
System.out.print("Pilihan menu: ");
pilihan = input.nextInt();
input.nextLine();
```
Menampilkan menu utama dan membaca pilihan dari pengguna.

```
switch (pilihan) {
    case 1:
        System.out.print("Pilih nomor menu pesanan: ");
        int pilihanMenu = input.nextInt();
        input.nextLine();

        if (pilihanMenu < 1 || pilihanMenu > daftarMenu.length) {
            System.out.println("Nomor tidak valid");
            break;
        }

        System.out.print("masukkan jumlah pesanan: ");
        int kuantitas = input.nextInt();

        namaPesanan[total] = daftarMenu[pilihanMenu - 1];
        harga[total] = hargaMenu[pilihanMenu - 1];
        kuantitasBeli[total] = kuantitas;
        total++;
        System.out.println(kuantitas + " " + daftarMenu[pilihanMenu - 1] + " berhasil ditambahkan");
        System.out.println();
        break;
        ```
Case 1 untuk menambah pesanan. Membaca nomor menu dan kuantitas pesanan dari pengguna, lalu menyimpannya dalam array yang sesuai.

```
case 2:
        int totalSementara = 0;
        System.out.println();
        System.out.println("=== Daftar pesanan ===");
        for (int i = 0; i < total; i++) {
            System.out.println((i + 1) + ". " + " " + namaPesanan[i] + " x" + kuantitasBeli[i] + " - Rp." + (harga[i] * kuantitasBeli[i]));
            totalSementara += harga[i] * kuantitasBeli[i];

            System.out.println("Total Biaya Sementara: Rp." + totalSementara);
        }
        System.out.println();
        break;
        ```
case 2 untuk menampilkan data pesanan. Menampilkan nama pesanan, kuantitas, dan total sementara.

```
case 3:
        int totalBayar = 0;
        for (int i = 0; i < total; i++) {
            totalBayar += harga[i] * kuantitasBeli[i];
        }
        System.out.println("total bayar: Rp." + totalBayar);
        System.out.println();
        break;
        ```
case 3 untuk menghitung total biaya pesanan.

```
case 4:
        System.out.println("Terima kasih telah memesan di kafe kami");
        break;
    default:
        System.out.println("pilih tidak valid. silahkan coba lagi");
}
```
case 4 untuk menyelesaikan program. Menampilkan pesan terima kasih. Default case untuk menangani input yang tidak valid.

```
} while (pilihan != 4);
```
loop do-while berlanjut hingga pengguna memilih 4.

```
}
```
sebagai penutup dari main metode

```
}
```
sebagai penutup kelas UAS2_1