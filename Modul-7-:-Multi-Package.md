# Multi File
Multi file adalah penulisan class pada file yang berbeda. Hal ini dilakukan guna membedakan satu class dengan class yang lain berdasarkan filenya. Keuntungan menggunakan multi file adalah kemudahan untuk menganalisa suatu error, memudahkan user untuk melakukan pengembangan atau perubahan terhadap suatu class. Dengan menggunakan multi file, class satu dengan class lain tidak akan tercampur tetapi masih saling berhubungan. Berikut merupakan bentuk penggunaan dari `Multi File` : 

![image](https://user-images.githubusercontent.com/94579033/203195470-ca9b559b-9424-4563-aaf5-5ed29a79084d.png)

Dapat dilihat terdapat beberapa file dengan nama Bear, Cat, Fish, dll. Setiap file-file tersebut berisi class-class yang terpisah satu sama lain. 

![image](https://user-images.githubusercontent.com/94579033/203195746-882cf6df-1b27-4ce0-acb7-270ea0ed2ffb.png)

Tiap-tiap class tersebut meskipun terpisah secara file, namun masih dapat saling berhubungan. Bukti keterhubungan tersebut adalah pada `Main Class` kita dapat melakukan deklarasi objek menggunakan class yang sedang berada di class lain, selain itu juga dapat dilakukan pemanggilan `method` dan `atribute` yang dimiliki masing-masing class. 

![image](https://user-images.githubusercontent.com/94579033/203195949-e953cf09-cefc-4def-bfb6-0af776fdbffe.png)

Syarat untuk menghubungkan suatu class pada satu file dengan class pada file lain adalah dengan menggunakan : 
``````Java
package namapackage
``````
`Package` sendiri merupakan sebuah folder yang bertujuan untuk mengelompokkan file-file class yang saling berkaitan. Sehingga untuk menghubungkan sebuah file dengan file lain **dalam satu package** perlu dituliskan keyword `package` pada awal program.

Berikut contoh penggunaan package : 
``````Java
package Tugas;

public class Main {
    public static void main(String[] args) {
        Bear Beruang = new Bear();

        Beruang.eat();
        Beruang.move();
        Beruang.sleep();
    }
}
``````
Program di atas adalah kode program pada class main yang akan mengambil atribute dan method pada class Bear yang berada pada file lain. Berikut merupakan kode program class Bear : 
``````Java
package Tugas; // <--- Penghubung semua file dalam package Tugas

public class Bear {

    public void eat() {
        System.out.println("Makan Daging");
    }

    public void move() {
        System.out.println("Bergerak Berjalan");
    }

    public void sleep() {
        System.out.println("Sedang Tidur");
    }
}
``````
Pada kode program di atas package yang berisi **Class Main** dan **Class Bear** adalah `Tugas`. Oleh karena itu untuk menghubungkan antara **class main** dan **class bear** perlu dituliskan
`````Java
package Tugas
``````

# Multi Package
Selain multi file, pada java juga memungkinkan untuk menghubungkan class yang terdapat pada package yang berbeda. 
![image](https://user-images.githubusercontent.com/94579033/203199312-858fd85a-a7d6-46f4-bf00-9c86ee3f943c.png)
Dapat dilihat pada gambar di atas, terdapat 2 package dengan nama **PackageSatu** dan **PackageDua** yang pada tiap-tiap packagenya berisi class. Kemudian kita dapat menggunakan class pada **PackageDua** di dalam main class di **PackageSatu**.
``````Java
package PackageSatu;
import PackageDua.PackageDua;

public class PackageSatu {
    public static void main(String[] args) {
         PackageDua baru = new PackageDua();
         baru.Tampil();
    }
}
``````
Dapat dilihat pada kode program di atas, dilakukan deklarasi dengan class `PackageDua` yang mana class tersebut berada pada package yang berbeda dengan class `PackageSatu`. Berikut merupakan isi dari class PackageDua : 
![image](https://user-images.githubusercontent.com/94579033/203199860-6b9da2c7-a0fc-4afe-8be1-41ce7274da85.png)
Untuk menggunakan class pada PackageDua di PackageSatu, maka kita perlu menghubungkan kedua class yang berbeda package tersebut. Untuk menghubungkan keduanya, digunakan : 
``````
import PackageDua.PackageDua; // <-- import NamaPackage.NamaFile;
``````
Dengan menggunakan keyword `import` maka class di dalam class yang berbeda package dapat digunakan pada file class package lain. Berikut merupakan ouput dari kode program di atas : 
``````
ini package dua
``````