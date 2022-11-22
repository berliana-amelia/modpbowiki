# Static Atribute
`Static Atribute` merupakan atribute yang menempel pada classnya atau menjadi milik class. Hal tersebut membuat `Static Atribute` dapat diakses melalui class tanpa melalui objek. Bukti bahwa static atribute adalah atribute milik class dapat dilihat pada gambar di bawah ini : 

![image](https://user-images.githubusercontent.com/94579033/203083575-55a84318-f5e5-4962-92b7-ee54d97577e9.png)

Kita tidak dapat menggunakan `this` pada `static atribute` yang mana `this` merupakan keyword untuk merujuk object yang tengah aktif. Untuk menggunakan static atribute maka dapat dituliskan seperti kode program di bawah ini : 

``````Java
class StaticCourse{
    static String StaticAtribute = "Ini Static Atribute"; // <-- Untuk menggunakan static keyword, cukup dituliskan static di depan tipe atributnya
    String Atribute;
    StaticCourse (String Atribute){
        this.Atribute = Atribute;
        StaticAtribute 
    }
}
``````
Dengan menggunakan `Static Atribute` , maka seluruh object dengan class yang memiliki static atribute tersebut akan memiliki static atribut beserta nilainya. Namun, yang membedakan antara static atribut dengan atribut biasa adalah kita dapat melakukan pemanggilan `Static Atribute` tersebut melalui classnya. 

![image](https://user-images.githubusercontent.com/94579033/203088526-62cf0852-a245-4dc9-b8b4-1585b1f15263.png)

Dapat dilihat pada gambar di atas, ketika dilakukan pemanggilan class, muncul _suggestion_ pemanggilan static atribute. Hal tersebut menandakan bahwa `Static Atribte` merupakan kepemilikan class, bukan object. Dengan begitu, pemanggilan `Static Atribute` melalui class memungkinkan untuk dilakukan.
``````Java
class StaticCourse{
    static String StaticAtribute = "Ini Static Atribute";
    String Atribute;
    StaticCourse (String Atribute){
        this.Atribute = Atribute;
    }
}

public class StaticMethodAndAtribute {
    public static void main(String[] args) {
        StaticCourse ObjectSatu = new StaticCourse("ini Bukan Static Atribute");
        StaticCourse Object_Dua = new StaticCourse("ini Bukan Static Atribute");
        System.out.println(ObjectSatu.StaticAtribute);
        System.out.println(Object_Dua.StaticAtribute);
        System.out.println(StaticCourse.StaticAtribute); // <--- Pemanggilan Static Atribute melalui class
    }
}

``````
Output : 
``````
Ini Static Atribute
Ini Static Atribute
Ini Static Atribute
``````
Karena kepemilikan dari static atribute adalah milik class, maka perubahan nilai pada static atribute entah itu melalui object atau class, akan mempengaruhi nilai y dari static atribute pada seluruh object yang membawanya. 
``````Java
class StaticCourse{
    static String StaticAtribute = "Ini Static Atribute";
    String Atribute;
    StaticCourse (String Atribute){
        this.Atribute = Atribute;
    }
}

public class StaticMethodAndAtribute {
    public static void main(String[] args) {
        StaticCourse ObjectSatu = new StaticCourse("ini Bukan Static Atribute");
        StaticCourse Object_Dua = new StaticCourse("ini Bukan Static Atribute");

        System.out.println(ObjectSatu.StaticAtribute);
        System.out.println(Object_Dua.StaticAtribute);
        System.out.println(StaticCourse.StaticAtribute);

        ObjectSatu.StaticAtribute = "BERUBAHHH!!!!"; // <-- Merubah nilai static atribute

        System.out.println(ObjectSatu.StaticAtribute);
        System.out.println(Object_Dua.StaticAtribute);
        System.out.println(StaticCourse.StaticAtribute);
    }
}
``````
Output : 
``````
Ini Static Atribute
Ini Static Atribute
Ini Static Atribute
BERUBAHHH!!!!
BERUBAHHH!!!!
BERUBAHHH!!!!
``````

Salah satu dari implementasi `Static Method` adalah kita dapat menghitung jumlah objek yang  telah dideklarasikan dengan menggunakan kode program seperti di bawah ini : 
``````Java
class StaticCourse{
    static int hitungAtribut;
    StaticCourse (){
        StaticCourse.hitungAtribut++; // <-- Akan bertambah setiap constructor method dipanggil.
    }
}

public class StaticMethodAndAtribute {
    public static void main(String[] args) {
        StaticCourse ObjectSatu = new StaticCourse();
        StaticCourse Object_Dua = new StaticCourse();
        System.out.printf("Jumlah objek yang telah dideklarasikan sejumlah : %d",StaticCourse.hitungAtribut);

    }
}

``````
Output : 
``````
Jumlah objek yang telah dideklarasikan sejumlah : 2
``````
Pada ouput di atas ketika melakukan pemanggilan `StaticCourse.hitungAtrubut` akan dihasilkan nilai 2. Hal tersebut dikarenakan pada setiap pemanggilan method constructor di deklarasi objek, hitungAtribut akan melakukan increment. Kemudian karena setiap perubahan pada `Static Atribute` nilainya melekat pada classnya, maka dihasilkan nilai 2.
# Static Method
Sama seperti static atribte, keyword `static` juga dapat diimplementasikan pada method. Untuk memberikan static pada method, dapat dilakukan melalui cara di bawah ini : 
``````Java
class StaticCourse{
    static void tampil(){
        System.out.println("Ini Static Method\n");
    }
}

public class StaticMethodAndAtribute {
    public static void main(String[] args) {
        StaticCourse.tampil();
    }
}
``````
Output : 
``````
Ini Static Method
``````
Dapat dilihat pada kode program dan output di atas. Pada kode program tidak dilakukan deklarasi objek sama sekali. Namun pemanggilan method masih dapat dilakukan melalui classnya.