# PBO_Tugas_3

`````
public class MesinTiket {
    // Atribut yang menyimpan harga tiket, saldo pengguna, dan total yang dibayar
    private double harga;
    private double saldo;
    private double total;

    // Konstruktor yang menerima harga tiket dan saldo awal pengguna
    public MesinTiket(double harga, double saldo) {
        this.harga = harga;
        this.saldo = saldo;
        this.total = 0.0; // Inisialisasi total yang dibayar dimulai dari 0
    }

    // Metode untuk mengambil nilai harga tiket
    public double getHarga() {
        return harga;
    }

    // Metode untuk mengambil saldo yang tersedia
    public double getSaldo() {
        return saldo;
    }

    // Metode untuk mengambil total pembayaran yang telah dilakukan
    public double getTotal() {
        return total;
    }

    // Metode untuk membayar tiket
    public void bayarTiket() {
        if (saldo >= harga) { // Memeriksa apakah saldo mencukupi untuk membayar tiket
            saldo -= harga; // Mengurangi saldo sebesar harga tiket
            total += harga; // Menambahkan harga tiket ke total yang dibayar
            System.out.println("Pembayaran berhasil. Saldo tersisa: " + saldo);
        } else { // Jika saldo tidak cukup
            System.out.println("Saldo tidak mencukupi, perlu saldo sebanyak: " + (harga - saldo));
        }
    }

    // Metode untuk menambahkan saldo
    public void tambahSaldo(double jumlah) {
        saldo += jumlah; // Menambahkan saldo pengguna
        System.out.println("Saldo berhasil ditambahkan. Saldo saat ini: " + saldo);
    }

    // Metode utama untuk menjalankan program
    public static void main(String[] args) {
        // Membuat objek MesinTiket dengan harga tiket 50 dan saldo awal 100
        MesinTiket mesin = new MesinTiket(50, 100);

        // Menampilkan harga tiket, saldo awal, dan total pembayaran sebelum transaksi
        System.out.println("Harga tiket: " + mesin.getHarga());
        System.out.println("Saldo awal: " + mesin.getSaldo());
        System.out.println("Total yang dibayar: " + mesin.getTotal());

        // Membayar tiket pertama kali
        mesin.bayarTiket();

        // Menampilkan saldo dan total pembayaran setelah pembelian tiket pertama
        System.out.println("Saldo setelah pembayaran: " + mesin.getSaldo());
        System.out.println("Total yang dibayar setelah pembayaran: " + mesin.getTotal());

        // Menambahkan saldo sebesar 30
        mesin.tambahSaldo(30);

        // Membayar tiket kedua kali setelah saldo ditambahkan
        mesin.bayarTiket();

        // Menampilkan saldo dan total pembayaran akhir
        System.out.println("Saldo akhir: " + mesin.getSaldo());
        System.out.println("Total yang dibayar akhir: " + mesin.getTotal());
    }
}
`````

1. Deklarasi Kelas dan Atribut:
`````
public class MesinTiket {
    private double harga;
    private double saldo;
    private double total;
}
`````
MesinTiket: Kelas yang digunakan untuk merepresentasikan sebuah mesin tiket.
Atribut harga menyimpan harga tiket, saldo menyimpan saldo yang dimiliki pengguna, dan total menyimpan jumlah total pembayaran tiket yang telah dilakukan.

2. Konstruktor:
`````
public MesinTiket(double harga, double saldo) {
    this.harga = harga;
    this.saldo = saldo;
    this.total = 0.0;
}
`````
Konstruktor ini digunakan untuk menginisialisasi harga tiket dan saldo pengguna ketika objek MesinTiket dibuat. Atribut total diinisialisasi dengan nilai 0 karena belum ada pembayaran yang dilakukan.

3. Getter getHarga(), getSaldo(), getTotal():
Metode ini hanya mengembalikan nilai dari atribut yang sesuai:
`````
public double getHarga() { return harga; }
public double getSaldo() { return saldo; }
public double getTotal() { return total; }
`````
getHarga(): Mengembalikan harga tiket.
getSaldo(): Mengembalikan saldo pengguna.
getTotal(): Mengembalikan total pembayaran yang telah dilakukan.

4. Metode bayarTiket():
`````
public void bayarTiket() {
    if (saldo >= harga) {
        saldo -= harga;
        total += harga;
        System.out.println("Pembayaran berhasil. Saldo tersisa: " + saldo);
    } else {
        System.out.println("Saldo tidak mencukupi, perlu saldo sebanyak: " + (harga - saldo));
    }
}
`````
Metode ini digunakan untuk melakukan pembayaran tiket.
Jika saldo cukup untuk membayar tiket (saldo >= harga), maka saldo akan dikurangi dengan harga tiket, dan total pembayaran ditambah dengan harga tiket. Informasi tentang sisa saldo ditampilkan.
Jika saldo tidak cukup, akan ditampilkan pesan berapa saldo yang kurang.

5. Metode tambahSaldo(double jumlah):
`````
public void tambahSaldo(double jumlah) {
    saldo += jumlah;
    System.out.println("Saldo berhasil ditambahkan. Saldo saat ini: " + saldo);
}
`````
Metode ini digunakan untuk menambah saldo pengguna. Setelah saldo ditambahkan, akan dicetak pesan yang menunjukkan saldo terbaru.

6. Metode main(String[] args):
`````
public static void main(String[] args) {
    MesinTiket mesin = new MesinTiket(50, 100);
    ...
}
`````
Metode main() adalah titik masuk dari program. Dalam metode ini, sebuah objek MesinTiket dibuat dengan harga tiket 50 dan saldo awal 100.
Kode ini juga melakukan serangkaian operasi:
Menampilkan informasi harga tiket, saldo awal, dan total pembayaran.
Melakukan pembayaran pertama kali.
Menambahkan saldo dan mencoba membayar tiket lagi.
Pada akhirnya, menampilkan saldo akhir dan total yang telah dibayar.
