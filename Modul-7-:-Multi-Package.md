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
Pada kode program di atas package yang berisi **Class Main** dan **Class Bear** adalah `Tugas`. Oleh karena itu untuk menghubungkan antara **class main** dan **class bear** diperlukan penulisan 
`````Java
package Tugas
``````