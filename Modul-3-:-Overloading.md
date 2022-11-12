# Overloading
`Overloading` adalah konsep ketika dituliskan 2 atau lebih constructor dan method dengan nama yang sama namun memiliki parameter yang berbeda. Konsep `overloading` sendiri juga merupakan penerapan konsep dari `polymorphsm` yang akan dibahas pada modul berikutnya.
# Constructor Overloading
`Constructor overloading` memungkinkan kita untuk melakukan pendeklarasian suatu object dengan beberapa opsional. Hal tersebut memungkinkan karena dengan menggunakan `overloading` maka akan terdapat beberapa `overloading` di dalam class. Berikut merupakan bentuk implementasi overloading : 
``````Java
class OverloadingClass{
    int a,b;
    OverloadingClass(int a){ // <-- constructor pertama dengan satu parameter
        this.a = a;
    }
    OverloadingClass(){      // <-- constructor kedua dengan 2 parameter
    }
    OverloadingClass(int a,int b){ // <-- constructor ketiga dengan 3 parameter
        this.a = a;
        this.b = b;   
    }
// Pada penulisan di atas terdapat 3 opsional constructor yang dapat dipilih dalam melakukan pendeklarasian object.
}

public class Overloading {
    public static void main(String[] args) {
        OverloadingClass pertama = new OverloadingClass(1);
        OverloadingClass kedua = new OverloadingClass();
        OverloadingClass ketiga = new OverloadingClass(1,2);
/* Dapat dilihat pada pendeklarasian object, argument yang dimiliki tiap-tiap pendeklarasian berbeda satu sama lain tetapi tidak terjadi error.
   Dengan demikian tiap tiap object akan memiliki nilai awal atribut yang berbeda sesuai dengan opsi constructor yang dipilih.
*/
// Untuk membuktikan dapat dilakukan pengecekan dengan mengoutputkan nilai masing masing object : 
        System.out.printf("nilai a : %d dan nilai b : %d\n",pertama.a,pertama.b);
        System.out.printf("nilai a : %d dan nilai b : %d\n",kedua.a,kedua.b);
        System.out.printf("nilai a : %d dan nilai b : %d\n",ketiga.a,ketiga.b);
    }
}
``````
# Method Overloading
`Method Overloading` merupakan implementasi overloading pada method. Dengan menggunakan overloading pada method maka dimungkinkan untuk terdapat beberapa method dengan nama yang sama namun dengan parameter dan statement yang berbeda ketika dilakukan pemanggilan. Dengan begitu, terdapat opsional method yang dapat dipilih untuk dipanggil menyesuaikan dengan kebutuhan program. Berikut merupakan contoh implementasi `method overloading` : 
``````Java
class OverloadingClass{
    int a,b;
    OverloadingClass(int a,int b){
        this.a = a;
        this.b = b;
    }
    void Tampilkan(int a){ // <-- method pertama dengan satu parameter
        this.Tampilkan();  /* <-- dapat dilakukan pemanggilan method Tampilkan lain. 
                                  Membuktikan bahwa keduanya merupakan 2 method yang berbeda dengan 1 nama */
        System.out.printf("nilai dari variabel a adalah  %d\n",a);
    }
    void Tampilkan(){     // <-- method kedua dengan dua parameter
        System.out.println("anda sedang menampilkan method\n");
    }
// Tiap-tiap statement yang terdapat di dalam method adalah berbeda, sehingga selain memiliki parameter yang berbeda tiap method juga memiliki statement yang berbeda ketika dijalankan. 
}

public class Overloading {
    public static void main(String[] args) {
        OverloadingClass ketiga = new OverloadingClass(1,2);
        ketiga.Tampilkan(5); // <-- Pemanggilan method tampilkan dengan satu parameter 
        ketiga.Tampilkan();  // <-- Pemanggillan method tampilkan tanpa parameter
    }
}
``````
OUTPUT :
``````
anda sedang menampilkan method 
nilai dari variabel a adalah  5

anda sedang menampilkan method
``````
Baris pertama dan kedua merupakan output dari pemanggilan method `ketiga.Tampilkan(5)` karena di dalam methodnya terdapat pemanggilkan `this.Tampilkan()` maka juga akan di tampilkan hasil dari method `ketiga.Tampilkan()` pada baris pertama. Kemudian pada baris keempat merupakan output dari pemanggilan method `ketiga.Tampilkan()` sendiri.