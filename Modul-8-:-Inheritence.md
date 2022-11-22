# Inheritence
`Intheritence` atau pewarisan merupakan konsep menurunkan sifat dari induk ke anaknya. Dalam OOP, penurunan/pewarisan sifat tersebut dilakukan dalam hal menurunkan isi dari suatu class seperti atribute dan method. Tujuan dari konsep inheritence ini adalah untuk mengurangi redudansi dalam penulisan atribut dan method jika suatu class memiliki atribut dan method yang sama dengan class lain. Dalam `inheritence` class yang menurunkan sifatnya disebut `Parent Class/SuperClass` sedangkan yang menerima pewarisan disebut `Child Class/SubClass`.
 
Tujuan lain dari pewarisan adalah bentuk perluasan atau pensesifikasian dari class, perluasan tersebut dapat berupa overidding dari perent class atau menambahkan atribut dan menthod baru pada child classnya. 

![](https://cdn-images-1.medium.com/max/1080/1*gRily1Y6mlrOETJeKRgvgw.png)

Pada gambar di atas terdapat class dengan nama Animal, isi dari class tersebut kemudian diwariskan kepada class lain yaitu `Dog` dan `Lion` yang mana Dog dan Lion merupakan bentuk perluasan dari animal dalam hal spesiesnya. Kemudian dapat dilihat pada class Dog dan Lion juga terdapat atributdan method yang tidak dimiliki oleh class Animal, hal tersebut merupakan bentuk perluasan dari class animal yang mana perluasan tersebut menyesuaikan dengan kebutuhan sub classnya.

Berikut merupakan penerapan inheritence : 
``````Java
package PackageSatu;

class Animal {
    String Species;
    Animal(String Species){
        this.Species = Species;
    }
}

class Goat extends Animal{
    Goat(String Species){
        super(Species);
    }
    void EatVegetable(){
        System.out.println(Species + "Eat Vegetable");
    }
}

class Lion extends Animal{
    Lion(String Species){
        super(Species);
    }
    void EatMeat(){
        System.out.println(Species + "Eat Meat");
    }
}
``````
Untuk menerapkan inheritence perlu dituliskan : 
``````Java
class subClass extends superClass{
      Statement;
}
``````
Dengan menggunakan kode program di atas, maka seluruh isi dari superClass juga akan menjadi milik subClass. Kemudian juga terdapat perluasan pad method, yang mana pada class goat terdapat perluasan method dengan nama **EatVagatable** dan pada class lion berupa **EatMeat**. Kedua method tersebut tidak dimiliki oleh superclassnya.

Selain itu pada kode program di atas, juga terdapat keyword `super`. Keyword `super` digunakan ketika melakukan overidding terhadap suatu method, tetapi masih ingin menggunakan bentuk dari method milik parentnya sehingga pada prosess overidding tidak diperlukan penulisan ulang di dalam method subclassnya. 
``````Java
class Lion extends Animal{
    Lion(String Species){
        super(Species);
    }
    void EatMeat(){
        System.out.println(Species + "Eat Meat");
    }
}
``````
Pada kode program di atas terdapat `super(Species)` maksud hal tersebut adalah subclass ingin menjalankan kode program yang sama dengan superclassnya. Pada kode program di atas, `super(Species)` merujuk pada 
``````Java
class Animal {
    String Species;
    Animal(String Species){
        this.Species = Species;
    }
}
``````