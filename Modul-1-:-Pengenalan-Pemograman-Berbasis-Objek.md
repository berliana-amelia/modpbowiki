# Apa itu Pemograman Berbasis Objek?
**Pemograman berbasis objek** atau **_Object Oriented Programming_** adalah metode pemograman yang berorientasi pada objek. Metode ini dibuat untuk menyediakan kebutuhan pengembangan program yang semakin hari semakin kompleks. Salah satu kekompleksan dari kebutuhan pengembangan program adalah kebutuhan untuk menyimpan beberapa jenis data dan fungsi secara bersamaan dalam satu variabel. Kekompleksan tersebut tidak dapat dipenuhi oleh **tipe data primitve** yang hanya mengizinkan satu variabel mempunyai satu tipe data saja, dan **struct** yang mampu menyimpan beberapa jenis tipe data, namun tidak mampu dalam menyimpan fungsi. 

![Ilustrasi Object Oriented Programming](https://holycoders.com/content/images/wordpress/2019/12/Object-Oriented-Programming.png)

Selain object, dalam _Object Oriented Programming_ juga dikenal **class**. Class merupakan cetakan/template dari object dan object merupakan hasil cetakan atau wujud dari class. Berikut merupakan penulisan kode program dari deklarasi object dan class : 
``````Java
class NamaClass{ // <-- Deklarasi Class (Class harus ada di atas class utama)
  // Statement
}
public class NamaFile{ // <-- Nama class pada class utama harus sama dengan nama fila (biasanya terisi otomatis ketika membuat file baru)
     public static void main(String[] args){
     NamaClass NamaObject = new NamaClass(); // <-- Deklarasi Object
     }
}
``````

Dengan menggunakan class, dapat dilakukan pengelompokan berbagai jenis yang data menggunakan **atribut** dan juga dapat mengolah data tersebut menggunakan **method**.
# Atribut
Atribut merupakan  nilai atau kumpulkan nilai yang dimiliki oleh dan dituliskan di dalam class. Mudahnya atribut dapat diilustrasikan sebagai ciri-ciri yang mempresentasikan karakteristik dari object. Berikut contoh penulisan atribut dalam bahasa Java :
``````Java
class NamaClass{ 
     // Deklarasi Atribut (seluruh atribut akan dimiliki oleh tiap object yang dideklarasikan)
     int nomor;
     Char huruf;
     String Kalimat;
     float pecahan;
}

public class NamaFile{ // <-- Nama class pada class utama harus sama dengan nama filenya (biasanya terisi otomatis ketika membuat file baru)
     public static void main(String[] args){
     NamaClass NamaObject = new NamaClass(); // <-- Deklarasi Object

     // Untuk memberikan nilai terhadap atribut dapat dilakukan dengan cara berikut : NamaObject.NamaAtribut = Nilai
     NamaObject.nomor = 1;
     NamaObject.huruf = 'a';
     NamaObject.Kalimat = "ini nilai";
     NamaObject.pecahan = 2.1f // Pada Java nilai float harus diikuti dengan f dibelakang nilai atau (float) di depan nilainya. Contoh : (float) 1/2
    }
}
``````

# Method
Method merupakan perilaku dari object. Perilaku ini berupa statement program yang dituliskan dalam bentuk fungsi atau prosedur untuk melakukan pengolahan nilai atau tidak. Mudahnya **method** merupakan _function atau procedur_ yang dituliskan/dimiliki oleh class. Berikut merupakan penulisan method di dalam class :
``````Java
class NamaClass{
   int nomor1,nomor2;
   void TampilkanNomor(){ // <--- Method dalam bentuk prosedur tanpa melakukan pengolahan data
      System.out.printf("Nomer 1 : %d dan Nomer 2 : %d\n",nomor1,nomor2);
   }
   int TambahkanNomor(){  // <--- Method dalam bentuk fungsi dan melakukan pengolahan data
      return nomor1 + nomor2; 
   }
}

public class NamaaFile {
    public static void main(String[] args) {
        manusia MantanTerindah = new manusia(); 
        MantanTerindah.nomor1 = 1;
        MantanTerindah.nomor2 = 2;

        // Melakukan pemanggilan/penggunaan method : 
        MantanTerindah.TampilkanNomor();
        int hasil = MantanTerindah.TambahkanNomor(); // variabel hasil akan menyimpan return value/nilai kembalian dari method
        // Atau dapat langsung ditampilkan seperti ini :
        System.out.printf("Hasil dari penjumlahan = %d\n",MantanTerindah.TambahkanNomor()); // Hasil dari pemanggilan method akan ditampung oleh %d
    }
}
``````

# Contoh Kode Program 
Berikut merupakan contoh dari penulisan OOP dalam bahasa Java : 
``````Java
class manusia{
    String WarnaRambut, WarnaKulit, Nama; // <--- Atribut (berupa variabel)
    int Umur;
    
    void TampilCiri(){ // <--- Method dalam bentuk prosedur (tanpa nilai kembalian)
        System.out.println("Nama : " + Nama);
        System.out.println("Warna Kulit : " + WarnaKulit);
        System.out.println("Warna Rambut : " + WarnaRambut);
        System.out.println("Umur : " + TampilUmur());
    }
    int TampilUmur(){   // <--- Method dalam bentuk fungsi (dengan nilai kembalian)
        return Umur;
    }
}

/* 
Untuk menggunakan seluruh isi dari class, maka diperlukan object yang akan memuat dan mempresentasikan keseluruhan nilai dari class. 
Berikut merupakan penulisan dari deklarasi object : 
*/

public class Pertama {
    public static void main(String[] args) {
        manusia MantanTerindah = new manusia(); // Struktur : NamaClass NamaObject = new NamaObject();
        manusia BismillahJodoh = new manusia();
        // Cara Memanggil Method : 
        MantanTerindah.TampilCiri();
        BismillahJodoh.TampilCiri();
    }
}
```````
Dalam kode program di atas, terdapat object dengan nama MantanTerindah dan BismillahJodoh, dengan menggunakan class maka kedua object tersebut dapat memiliki atribut dan method atau ciri dan karateristik yang sama. Sehingga tidak perlu didefinisikan ciri dan karakteristik tersebut pada masing-masing object.