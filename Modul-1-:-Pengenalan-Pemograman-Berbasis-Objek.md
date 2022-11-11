# Apa itu Pemograman Berbasis Objek?
**Pemograman berbasis objek** atau **_Object Oriented Programming_** adalah metode pemograman yang berorientasi pada objek. Metode ini dibuat untuk menyediakan kebutuhan pengembangan program yang semakin hari semakin kompleks. Salah satu kekompleksan dari kebutuhan pengembangan program adalah kebutuhan untuk menyimpan beberapa jenis data dan fungsi secara bersamaan dalam satu variabel. Kekompleksan tersebut tidak dapat dipenuhi oleh **tipe data primitve** yang hanya mengizinkan satu variabel mempunyai satu tipe data saja, dan **struct** yang mampu menyimpan beberapa jenis tipe data, namun tidak mampu dalam menyimpan fungsi. 

![Ilustrasi Object Oriented Programming](https://holycoders.com/content/images/wordpress/2019/12/Object-Oriented-Programming.png)

Selain object, dalam _Object Oriented Programming_ juga dikenal **class**. Class merupakan cetakan/template dari object dan object merupakan hasil cetakan atau wujud dari class. Dengan menggunakan class, dapat dilakukan pengelompokan berbagai jenis yang data menggunakan atribut**atribut** dan mengolah data tersebut menggunakan **method**. 
1. Atribut merupakan  nilai atau kumpulkan nilai yang dimiliki oleh class, mudahnya atribut dapat diilustrasikan sebagai ciri-ciri yang mempresentasikan karakteristik dari object. 
2. Method merupakan perilaku dari object. Perilaku ini berupa statement program yang dituliskan dalam bentuk fungsi atau prosedur untuk melakukan pengolahan nilai atau tidak. Mudahnya **method** merupakan _function atau procedur_ yang dituliskan/dimiliki oleh class. 

# Penulisan Program
Berikut merupakan contoh dari penulisan class dalam bahasa Java : 
``````Java
public class manusia{
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
Untuk menggunakan seluruh isi dari class, maka diperlukan object yang akan memuat dan 
mempresentasikan keseluruhan nilai dari class. 

Berikut merupakan penulisan dari deklarasi object : 
*/

public class Pertama {
    public static void main(String[] args) {
        manusia MantanTerindah = new manusia(); // Struktur : NamaClass NamaObject = new NamaObject();
        manusia BismillahJodoh = new manusia();
    }
}
```````
Dalam kode program di atas, terdapat object dengan nama MantanTerindah dan BismillahJodoh, dengan menggunakan class maka kedua object tersebut dapat memiliki atribut dan method atau ciri dan karateristik yang sama. Sehingga tidak perlu didefinisikan ciri dan karakteristik tersebut pada masing-masing object.