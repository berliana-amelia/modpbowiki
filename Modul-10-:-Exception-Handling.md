# Pengertian Exception Handling
Dalam sebuah pemograman terdapat kemungkinan terjadi sebuah error yang disebabkan oleh user saat run time terjadi. Error ini terjadi bukan karena kesalahan penulisan kode program dan terjadi saat program tersebut sedang berjalan. Ketika error ini terjadi, maka program akan otomatis berhenti sehingga tidak melanjutkan kode program di bawahnya. Untuk itu terdapat `try and exception` sebagai solusi dalam mengatasi permasalahan tersebut. 

Exception handling bekerja dengan menangkap bug atau error massage yang terjadi dan menjadikannya `toString`. Hal tersebut memungkinkan terjadi karena Exception di dalam java merupakan sebuah class dan bug atau error yang muncul merupakan sebuah object.

Berikut merupakan beberapa daftar error yang dapat terjadi di dalam Java : 

|Exception|Deskripsi|
|---------|---------|
|ArithmetiException|Hasil perhitungan matematika error, seperti pembagian dengan 0|
|ArrayIndexOutOfBoundsException|Index array yang dituju melebihi panjang array|
|ArrayStoreException|Data yang diinputkan ke dalam array berbeda tipe datanya dengan tipe data arraynya|
|ClassCastException|Error yang terjadi ketika kita ingin merubah class dari sebuah object ke class lain|
|IllegalArgumentException|Mengirimkan argumen yang tidak sejenis dengan parameter tipe datanya|
|CassNotFoundException|Class yang dipanggil tidak ada|
|IllegalAccessException|Pengaksesan terhadap kelas gagal|

# Try - Catch
`Try` merupakan sebuah keyword yang menyediakan sebuah area untuk menjalankan blok program yang memiliki kemungkinan terjadi error run time. `Try` biasa dipasangkan dengan `catch` yang digunakan untuk menangkap error run time yang terjadi di dalam blok program `try`. Error run time yang ditangkap kemudian dikonversi menggunakan toString sehingga dapat ditampilkan tetapi tidak menghentikan berjalannya program.

Berikut merupakan contoh implementasi dari `try - catch` : 
``````Java
import java.util.Scanner;

class exception {
    public static void main(String[] args) {
        int[] angka = { 1, 2, 3, 4, 5 };
        Scanner inputan = new Scanner(System.in);
        try {
            System.out.println("Masukkan indeks : ");
            int indeks = inputan.nextInt();
            System.out.printf("Nilai indeks ke -%d adalah &d : ", indeks, angka[indeks]);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
``````
Output : 
`````
java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 5
`````

Selain itu kita dapat ganti `exception` di dalam kurung `catch` dengan nama error yang terjadi yaitu seperti contoh berikut : 
``````Java
try {
      System.out.println("Masukkan indeks : ");
      int indeks = inputan.nextInt();
      System.out.printf("Nilai indeks ke -%d adalah &d : ", indeks, angka[indeks]);
} catch (ArrayIndexOutOfBoundsException e) { // Exception diganti dengan ArrayIndexOutOfBoundsException ketika kita mengetahui error yang kemungkinan terjadi
      System.out.println(e);
}
``````
Pada `try-catch` tidak terbatas dengan satu `catch` saja, namun dalam satu `try` dapat dipasangkan dengan lebih dari satu `catch` sehingga `catch` yang dieksekusi dapat menyesuaikan dengan error yang terjadi, namun jika `catch` awal dijalankan maka seluruh `catch` setelahnya tidak akan dijalankan meskipun errornya juga terjadi dan catch yang akan dijalankan adalah catch yang menampung error yang pertama kali terjadi.

Berikut merupakan contoh dari `multi-catch` : 
``````Java
import java.util.Scanner;

class exception {
    public static void main(String[] args) {
        int[] angka = { 1, 2, 3, 4, 5 };
        Scanner inputan = new Scanner(System.in);
        try {
            System.out.println("Masukkan indeks : ");
            int indeks = inputan.nextInt();
            System.out.printf("Nilai indeks ke -%d adalah %d : ", indeks, angka[indeks]);
            int a = 1 / 0;
        } catch (ArrayIndexOutOfBoundsException e) { // Cath pertama
            System.out.println(e);
        } catch (ArithmeticException e) { // Catch Kedua
            System.out.println(e);
        }
    }
}
``````
Pada program di atas, terdapat 2 cath. Jika kita memasukkan indeks yang benar maka catch kedua akan dieksekusi karena error pada catch pertama tidak terjadi. Namun, jika error pada catch pertama juga terjadi, maka hanya catch pertama yang dijalankan dan catch kedua tidak meskipun error pada catch kedua juga terjadi.

# Finally 
`Finally` merupakan keyword yang menyediakan block program yang akan selalu dijalankan setelah `try` dan `catch` dijalankan terlepas dari terjadi atau tidaknya error di dalam `try - catch`. 

Berikut merupakan contoh implementasi dari `finally` : 
``````Java
import java.util.Scanner;

class exception {
    public static void main(String[] args) {
        int[] angka = { 1, 2, 3, 4, 5 };
        Scanner inputan = new Scanner(System.in);
        try {
            System.out.println("Masukkan indeks : ");
            int indeks = inputan.nextInt();
            System.out.printf("Nilai indeks ke -%d adalah %d : ", indeks, angka[indeks]);
            int a = 1 / 0;
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println(e);
        } catch (ArithmeticException e) {
            System.out.println(e);
        } finally {
            System.out.println("Terimakasih telah menggunakan program kami"); // Akan dioutputkan ketika try - catch selesai dijalankan
        }
    }
}
``````
Contoh lain dari Finally : 
``````Java
class exception {
    public static void main(String[] args) {
        try {
            int a = 1 / 0;
        } catch (Exception e) {
            System.out.println(e);
        } finally {
            System.out.println("Terimakasih telah menggunakan program kami");
        }
    }
}
``````

# Throw
Pada pembahasan sebelumnya telah dijelaskan bahwa terdapat banyak jenis dari error yang terjadi di Java. Selain itu, pada pemograman java kita dapat membuat exception atau error massage sendiri menyesuaikan dengan kondisi yang kita inginkan. Untuk melakukan hal tersebut maka digunakanlah keyword `Throw` dan exception yang dibuat sendiri disebut `user define exception`. 

Untuk melakukan custom exception maka terdapat beberapa tahapan : 

1. Buat class baru dengan nama exception yang diinginkan.
   ``````Java
    class AgeException extends Exception{
        AgeException(String Massage){ // --> Constructor untuk membuat user define exception
            super(Massage);
        }
    }
   ``````
   Disini akan dibuat user define exception dengan nama AgeException. 

2. Buat fungsi atau method yang melakukan pengecekan terhadap kondisi yang dijadikan sebagai kondisi yang akan menghasilkan error tersebut.
   ``````Java
   static void AgeCheck(int age) throws AgeException{ // --> Pada method diberikan throws kepada class exceptionnya
        if(age < 18){
            throw new AgeException("\nUmur tidak mencukupi"); // --> throw deklarasi object exception
        }else{
            System.out.println("Anda berhasil login");
        }
    }
   ``````
   Disini terdapat sebuah method dengan nama AgeCheck yang akan melakukan pengecekan terhadap nilai parameter age. Kondisi yang menghasilkan error disini 
   adalah jika `age < 18`.

3. Buat Main Program dengan Try - Checknya.
   ``````Java
   public static void main(String[] args) {
        Scanner inputan = new Scanner(System.in);
        System.out.println("Masukkan Umur : ");
        int Umur = inputan.nextInt();

        try{
            AgeCheck(Umur);
        }catch (Exception e){
            System.err.println(e);
        }finally {
            System.out.println("\nTerimakasih");
        }
   }
   ``````

Berikut merupakan full program dari program di atas : 
``````Java
package TryExcept;

import java.util.Scanner;

class AgeException extends Exception{
    AgeException(String Massage){
        super(Massage);
    }
}

public class Throws {
    static void AgeCheck(int age) throws AgeException{
        if(age < 18){
            throw new AgeException("\nUmur tidak mencukupi");
        }else{
            System.out.println("Anda berhasil login");
        }
    }
    public static void main(String[] args) {
        Scanner inputan = new Scanner(System.in);
        System.out.println("Masukkan Umur : ");
        int Umur = inputan.nextInt();

        try{
            AgeCheck(Umur);
        }catch (Exception e){
            System.err.println(e);
        }finally {
            System.out.println("\nTerimakasih");
        }
    }
}

``````

Berikut merupakan output dari program di atas : 

Input 1 : 
``````
Masukkan Umur : 
5
``````
Output 1 :
``````
TryExcept.AgeException: 
Umur tidak mencukupi

Terimakasih
``````
Input 2 :
``````
Masukkan Umur : 
20
``````
Output 2 : 
``````
Anda berhasil login

Terimakasih
``````