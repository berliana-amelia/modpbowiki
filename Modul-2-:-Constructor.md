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

# Penulisan Constructor
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
    // Tanpa Menggunakan Constructor  
       NamaObject.Nilai = 100;
       NamaObjet.Nama = "Juned"   
    }
}

````` 
Dapat dilihat pada program di atas, bahwa penggunaan constructor dalam pemberian nilai lebih efisien dalam penulisannya.
# This Keywoard
`This` adalah keywoard yang merujuk kepada object yang sedang aktif saat itu atau object yang sedang dipanggil pada saat pemanggilan method. Penggunaan `this` seringkali digunakan untuk memberikan nilai object di dalam constructor, penggunaan this digunakan karena seringkali parameter constructor dituliskan mirip dengan nama atributnya, sehingga perlu diberi pembeda diantara keduanya. Berikut merupakan penggunaan `this` keywoard : 
``````Java
class NamaClass{
   int nilai;
   String nama
   NamaClass(int nilai, String nama){
/* Pada bagian ini atribut nilai dengan parameter nilai memiliki kesamaan nama, sehingga compiler perlu diberitau bahwa keduanya berbeda dengan 
   menggunakan keywoard this, keyword this memberitau compiler bahwa nilai tersebut merujuk kepada atribut nilai milik object yang tengah dipanggil
   bukan merujuk kepada parameter milik constructor */
     this.nilai = nilai; 
     this.nama = nama;
   }
// Contoh lain dari penggunaan this adalah sebagai berikut : 
   NamaClass(){ // <-- hal ini disebut dengan overloading (penulisan 2 method yang sama dengan parameter yang berbeda)
     this(100,"Sylphy"); /* <-- this akan merujuk pada object yang sedang aktif, 
                                penulisan ini mirip dengan new NamaObject(); pada 
                                class utama saat mendeklarasikan object baru */ 
   }
}
public class NamaFile {
    public static void main(String[] args) {
       NamaClass NamaObject = new NamaObject(100,"Juned")     
    }
}
``````