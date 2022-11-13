# Encapsulasi
`Encapsulasi` atau `Encapsulation` merupakan sebuah metode pengaksesan `atribut` dengan cara memanggil `method`. Dengan menggunakan `encapsulasi` maka pengaksesan beberapa atribut dapat dilakukan secara bersamaan dengan hanya memanggil sebuah method. `Encapsulasi` jika diilustrasikan sama seperti capsul.

![](https://xperti.io/blogs/wp-content/uploads/2021/12/xblog-Encapsulation.png)

Jika pada sebelumnya telah dibahas bahwa `private access modifier` tidak dapat diakses di luar classnya, maka melalui `encapsulasi` pengaksesan terhadap private atribut memungkinkan untuk dilakukan namun secara **TIDAK LANGSUNG**. Pengaksesan tersebut haruslah melalui penghubung berupa `method` berupa `setter method` dan `getter method`.

# Setter
`Setter` merupakan method untuk melakukan pengaksesan terhadap atribut di dalam class dengan access modifier private. Hal ini bertujuan agar tidak dapat memungkinkannya/tidak dapat dilakukannya atribut tersebut secara bebas atau terpisah. 

Berikut contoh penulisan `setter method` : 
``````Java
class Mahasiswa{
    private int Nilai; 
    private String Matkul; 
    
    Mahasiswa(String Matkul, int Nilai){ /* <-- Constructor merupakan setter, karena untuk melakukan 
                                                akses pemberian nilai terhadap atribut haruslah melalui construcor. */
        this.Nilai = Nilai;
        this.Matkul = Matkul;
    }

    Mahasiswa(){}; // <-- Constructor kedua (Overloading Constructor)

 // Selain melalui constructor, setter juga dapat melalui method biasa :
    void SetterNilai(String Matkul,int Nilai) { // <-- Berikut merupakan method setter.

 /* Atribut privat akan tetap diakses di dalam class melalui method setter dan method 
    setter dapat diakses di luar class karena method setter tidak bersifat privat. */
        this.Nilai = Nilai;
        this.Matkul = Matkul;
    }
}

public class RekapNilai {
    public static void main(String[] args) {
        Mahasiswa Windah = new Mahasiswa("Pemograman Berbasis Objek",100); // <-- Pemanggilan setter method berupa constructor.

    //  Dengan sifatnya yang private maka pemberian nilai tidak dapat dilakukan secara terpisah seperti di bawah ini : 
    //  Windah.Nilai = 5 // <-- Hal tersebut tidak memungkinkan, karena atribut nilai bersifat private dan pengaksesan tidak melalui setter.
        
        Mahasiswa Basudara = new Mahasiswa();
    //  Setter menggunakan method SetterNilai : 
        Basudara.SetterNilai("Perancangan Basis Data",100); /* <-- Dengan menggunakan setter, maka pengaksesan atribut haruslah dilakukan secara 
                                                                   bersamaan menyesuaikan dengan parameter setter yang dimiliki. */
    }
}
``````
Di dalam kode program di atas, `setter` disetting untuk melakukan pemberian data terhadap atribut nilai dan matkul secara bersamaan atau melarang pemberian nilai secara terpisah atau tanpa melalui `setter`. 
# Getter
Jika `setter` digunakan untuk memberikan nilai kepada atribut, maka getter digunakan untuk mengambil nilai atribut yang bersifat private tersebut. Sehingga jumlah atribut yang diambil nilainya, menyesuaikan dengan aturan dari method `getter` tersebut.

Berikut merupakan contoh penulisan method `getter` :
``````Java
class Mahasiswa{
    private int Nilai; 
    private String Matkul;     
    Mahasiswa(String Matkul, int Nilai){
        this.Nilai = Nilai;
        this.Matkul = Matkul;
    }
    Mahasiswa(){};
    void SetterNilai(String Matkul,int Nilai) {
        this.Nilai = Nilai;
        this.Matkul = Matkul;
    }

    void TampilkanData(){ // <-- Berikut merupakan getter method dengan aturan menampilkan kedua data sekaligus
        System.out.printf("Mata Kuliah : %s\nNilai : %d\n",this.Matkul,this.Nilai);
    }

  // Getter tidak terbatas dengan prosedur, fungsi juga dapat digunakan sebagai getter : 
     int AmbilNilai(){ // <-- Getter untuk mengambil nilai dari atribut nilai saja
        return this.Nilai;
    }
}

public class RekapNilai {
    public static void main(String[] args) {
        Mahasiswa Windah = new Mahasiswa("Pemograman Berbasis Objek",100);
        Mahasiswa Basudara = new Mahasiswa();
        Basudara.SetterNilai("Perancangan Basis Data",100);
        System.out.println("Windah : ");

//      Memanggil getter method : 
        Windah.TampilkanData();
        System.out.println("\nBasudara : ");
        Basudara.TampilkanData();
        int NilainyaWindah = Windah.AmbilNilai(); // <-- Karena terdapat return value maka diperlukan container untuk menampungnya.
        System.out.println("Nilainya Windah : " + NilainyaWindah);

//       Memanggil tanpa melalui getter : 
//       System.out.println("Nilainya Windah : " + Windah.Nilai); <--- Akan Error karena tidak diizinkan.
    }
}
`````` 
Pada kode program di atas terdapat 2 `getter` yaitu `TampilkanData` dan `AmbilNilai`, masing-masing `getter` mempunyai aturannya masing-masing, yaitu mengambil kedua nilai atribut dan mengambil nilai atribut nilai saja. Sehingga pemanggilan nilai di luar kedua aturan tersebut akan menghasilkan error atau tidak dapat dilakukan.