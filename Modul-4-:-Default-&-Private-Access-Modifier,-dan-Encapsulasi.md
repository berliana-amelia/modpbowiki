# Definisi Access Modifier
`Access Modifier` merupakan metode menentukkan kewenangan dalam mengakses class dan isi di dalamnya (method,atribut,dll). Jadi kita dapat mengatur dimana saja dan siapa saja yang dapat melakukan pengaksesan langsung terhadap class atau isinya. 
`Access Modifier` sendiri terdiri dari beberapa jenis antara lain : 
1. Default
2. Public
3. Private
4. Protected

![](https://usemynotes.com/wp-content/uploads/2021/02/what-are-access-specifiers-in-java.jpg)

Namun, dalam modul kali ini hanya akan dibahas mengenai default dan private access modifier. Hal tersebut dikarenakan sifat dari access modifier lainnya tidak akan terlihat jika penulisan program masih dalam satu file yang sama. B
Berikut merupakan contoh penulisan `access modifier` : 
``````Java
class NamaClass{
      private int a; // <access modifier> <tipe data> <nama atribut>
      int b;
}
``````
# Default Access Modifier
Default access modifier adalah access modifier yang diberikan secara otomatis oleh Java, sehingga untuk menggunakan access modifier ini tidak perlu dilakukan penulisan access modifiernya di depan atribut atau methodnya. Contoh default access modifier : 
``````Java
class NamaClass{
      int a;
}
``````
Secara otomatis atribut a akan memiliki access modifier berupa `default`. Dengan itu atribut a dapat diakses diseluruh program dengan syarat masih dalam satu `package` yang sama.
# Private Access Modifier
`Private` access modifier adalah access modifier yang hanya mengizinkan pengaksesan secara langsung di dalam classnya saja, sehingga pengaksesan di luar classnya sendiri (satu package atau berbeda) akan dilarang atau tidak dapat dilakukan. 
Berikut merupakan contoh implementasi `private access modifier` :  
``````Java
class OverloadingClass{
    private int a; // <-- atribut a memiliki access modifier private
    int b;         // <-- atribut b memiliki access modifier default (tidak perlu ditulis)
    OverloadingClass(int b){
        a = 5;
        this.b = b;
    }
}

public class Overloading {
    public static void main(String[] args) {
        OverloadingClass ketiga = new OverloadingClass(2);
        System.out.println("Nilai B adalah : " + ketiga.b);
 /*     System.out.println("Nilai B adalah : " + ketiga.a); <-- Jika dijalankan akan error, karena atribut a memiliki access modifier berupa private, 
                                                                sehingga tidak dapat dilakukan pengaksesan di luar classnya sendiri */ 
    }
}
`````` 
Hal yang terjadi jika kita memaksa untuk melakukan pengaksesan secara langsung terhadap atribut dengan access modifier private adalah sebagai berikut : 
``````
'a' has private access in 'Modul.OverloadingClass'
``````
# Encapsulasi/Encapsulation