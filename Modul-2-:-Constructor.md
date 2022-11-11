# Definisi Constructor
Constructor merupakan salah satu method yang dimiliki oleh class pada Java. Method constructor digunakan untuk melakukan pemberian nilai awal kepada object yang dideklarasikan. Perhatikan contoh kode program di bawah :
``````Java
Class NamaClass{
   // Statement
}
public class Pertama {
    public static void main(String[] args) {
       NamaClass NamaObject = new NamaObject()       
    }
}
``````
Pada kode program di atas, ketika mendeklarasikan object maka akan dituliskan `NamaObject()`, penulisan tersebut merupakan pemanggilan method constructor yang bertujuan untuk melakukan pemberian nilai awal. Java secara default membuat method constructor di dalam class meskipun tidak dituliskan, dan secara otomatis memberikan nilai `NULL` jika belum diberikan nilai pada atributnya. 

Karena constructor merupakan sebuah method, maka dapat dilakukan perubahan/custom pada constructor. Berikut merupakan cara penulisan constructor :
``````Java
class NamaClass{
   int nilai;
// Deklarasi Constructor : Keywoard (opsional) NamaConstructor(Harus Sama dengan Nama Class) { Statement }
   NamaClass{
     nilai = 100; // <-- secara otomatis atribut nilai pada setiap object akan bernilai 100
   }
}
public class NamaFile {
    public static void main(String[] args) {
       NamaClass NamaObject = new NamaObject()       
    }
}
`````` 
Pada kode program di atas atribut nilai akan otomatis terisi dengan nilai 100, hal tersebut dikarenakan constructor merupakan method untuk melakukan pemberian nilai awal, dan di dalam constructor di atas dituliskan nilai dari atribut nilai = 100, sehingga nilai awal yang diberikan pada object akan otomatis terisi 100. 

Jika tidak ingin demikian, dapat dilakukan pengisian nilai atribut menggunakan constructor secara manual melalui deklarasi object pada class utama dengan menggunakan parameter.
``````Java
class NamaClass{
   int nilai;
   String nama
   NamaClass(int nilai, String nama){
     this.nilai = nilai;
     this.nama = nama;
   }
}
public class NamaFile {
    public static void main(String[] args) {
       NamaClass NamaObject = new NamaObject(100,"Juned") // <-- nilai awal diisikan di dalam tanda kurung yang akan menjadi argumen menuju constructor       
    }
}
``````
Penggunaan parameter dimungkinkan karena `constructor` merupakan method. Penggunaan constructor bermanfaat untuk melakukan pengurangan syntax dalam pemberian nilai atribut, karena hanya dapat dilakukan secara bersamaan saat pendeklarasian object.

`````Java
public class NamaFile {
    public static void main(String[] args) {
       NamaClass NamaObject = new NamaObject(100,"Juned") // <-- Menggunakan Constructor
       NamaObject.Nilai = 100;
       NamaObjet.Nama = "Juned" // <-- Tanpa Menggunakan Constructor       
    }
}

````` 