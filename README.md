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
