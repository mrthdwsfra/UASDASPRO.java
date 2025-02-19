import java.util.Scanner; :untuk membaca inputan

public class uas1{ :untuk menginisialisasi

    public static void main(String[] args) { :sebagai titik awal memulai sebuah program
        Scanner input = new Scanner(System.in); : untuk menciptakan objek scanner input yang membaca dari input standar.
        String[] namaMahasiswa = new String[100]; :menggunakan string untuk mempresentasikan teks,kalimat,kata atau karakter.
        String[] nimMahasiswa = new String[100];
        String[] jenisPrestasi = new String[100];
        String[] tingkatPrestasi = new String[100];
        int[] tahunPrestasi = new int[100];
        int prestasiCount = 0;
        int pilihan; :menggunakan int karna untuk menyimpan angka bilangan bulat
        do { : menggunkan perulangan do-while untuk eksekusi minimal sekali dan untuk validasi input
            System.out.println("=== PENCATATAN PRESTASI MAHASISWA ==="); :menggunakan System.out.println agar dapat menampilkan output dan untuk menambahkan garis baru
            System.out.println("1. Tambah Prestasi Mahasiswa");:menggunakan System.out.println untuk menampilkan informasi yang kita minta.
            System.out.println("2. Tampilkan Daftar Prestasi");
            System.out.println("3. Analisis Prestasi Berdasarkan Jenis");
            System.out.println("4. Keluar");
            System.out.print("Pilih menu: "); untuk menampilkan teks tanpa baris baru tanpa menambah baris pilihan = input.nextInt();untuk membaca bilangan bulat
            input.nextLine(); : digunakan untuk membaca seluruh baris input.
            switch (pilihan) { :untuk mengecek nilai yang dimasukkan.
                case 1:
                if (prestasiCount >= 100) { :kondisi ini biasanya mengevaluasi menjadi nilai yang benar.
                    System.out.println("Jumlah prestasi telah mencapai batas maksimal."); :untuk menampilkan informasi yang kita minta.
                    break; :untuk menghentikan eksekusi blok switch setelah blok case yang
                    } 

                    System.out.print("Nama Mahasiswa: "); 
                    namaMahasiswa[prestasiCount] = input.nextLine(); 
                    System.out.print("NIM: "); 
                    nimMahasiswa[prestasiCount] = input.nextLine(); 
                    System.out.print("Jenis Prestasi: "); 
                    jenisPrestasi[prestasiCount] = input.nextLine(); 
                    while (true) { 
                        System.out.print("Tingkat Prestasi (Lokal, Nasional, Internasional): "); 
                        tingkatPrestasi[prestasiCount] = input.nextLine(); 
                        if (tingkatPrestasi[prestasiCount].equalsIgnoreCase("Lokal") || 
                        tingkatPrestasi[prestasiCount].equalsIgnoreCase("Nasional") || 
                        tingkatPrestasi[prestasiCount].equalsIgnoreCase("Internasional")) {
                            break; 
                        } else { 
                            System.out.println("Input tidak valid. Harap masukkan salah satu dari: Lokal, Nasional, Internasional."); 
                        } 
                    }
                    while (true) { 
                        System.out.print("Tahun Prestasi (2010 hingga tahun saat ini): "); 
                        int tahun = input.nextInt(); 
                        input.nextLine(); 
                        if (tahun >= 2010 && tahun <= 2024) { 
                            tahunPrestasi[prestasiCount] = tahun; 
                            break; 
                        } else { 
                            System.out.println("Input tidak valid. Harap masukkan tahun antara 2010 hingga tahun saat ini."); 
                        } 
                    }

                    prestasiCount++; 
                    System.out.println("Prestasi berhasil ditambahkan!");
                    break;
                case 2:
                if (prestasiCount > 0) {
                    System.out.println("=== DAFTAR SEMUA PRESTASI ==="); 
                    for (int i = 0; i < prestasiCount; i++) { 
                        System.out.println("Nama: " + namaMahasiswa[i] + "| NIM: " + nimMahasiswa[i] + "| Jenis: " + jenisPrestasi[i] + "| Tingkat: " + tingkatPrestasi[i] + "| Tahun: " + tahunPrestasi[i]); 
                    }
                } else {
                    System.out.println("belum ada data prestasi");
                }                  
                    break; :untuk menghentikan eksekusi loop.
                case 3: :Jika nilai yang dievaluasi sama dengan 3, maka kode yang terkait dengan case 3:
                System.out.print("Masukkan jenis prestasi yang ingin dianalisis: "); :digunakan untuk mencetak teks "Masukkan jenis prestasi yang ingin dianalisis: " ke terminal tanpa menambahkan baris baru setelahnya. 
                String jenis = input.nextLine(); :digunakan untuk membaca seluruh baris teks yang dimasukkan dari terminal dan menyimpannya dalam variabel jenis yang bertipe String.
                System.out.println("=== ANALSIS PRESTASI ==="); :digunakan untuk mencetak teks "=== ANALISIS PRESTASI ===" ke terminal.
                for (int i = 0; i < prestasiCount; i++) {  :untuk mengulang blok kode sejumlah prestasiCount kali. Berikut penjelasan singkatnya:

int i = 0; inisialisasi variabel i dengan nilai 0.

i < prestasiCount; adalah kondisi loop yang memastikan loop berjalan selama i kurang dari prestasiCount.

i++ adalah ekspresi peningkatan yang menambah nilai i sebesar 1 setiap iterasi.
                    if (jenisPrestasi[i].equalsIgnoreCase(jenis)) {  :digunakan untuk membandingkan dua string tanpa memperhatikan huruf besar/kecil.
                        System.out.println("Nama: " + namaMahasiswa[i] + "| NIM: " + nimMahasiswa[i] + "| Tingkat: " + tingkatPrestasi[i] + "| Tahun: " + tahunPrestasi[i]); 
                    } 
                }
                    break; :untuk menghentikan eksekusi loop.
                case 4: :Jika nilai yang dievaluasi sama dengan 4, maka kode yang terkait dengan case 4:
                    System.out.println("Terima kasih!"); :digunakan untuk mencetak teks "Terima kasih!" ke hasil run. 
                    break; :untuk menghentikan eksekusi loop.
                default: :digunakan sebagai pilihan terakhir jika nilai yang diuji sesuai.
                    System.out.println("Pilihan tidak valid. Silakan coba lagi.");digunakan untuk mencetak teks "Pilihan tidak valid. Silakan coba lagi." ke hasil run.
            }
        } while (pilihan != 4);:kondisi while adalah untuk mengulang kode selama nilai yang ditentukan benar,(pilihan != 4) artinya selama variabel tidak bernilai 4 maka akan terus melakukan looping.

    }
}
