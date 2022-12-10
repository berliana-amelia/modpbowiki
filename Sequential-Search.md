# Searching Algorithm
Searching algorithm atau algoritma pencarian merupakan algoritma yang digunakan untuk mencari sebuah item dalam sebuah kumpulan data. Terdapat banyak jenis algoritma pencarian seperti sequential searching, binary searching, jump searching, interpolation searching, dan banyak lagi. 
# Sequential Searching
Sequential searching atau biasa disebut linear searching merupakan algoritma pencarian dasar yang melakuan pencarian item di dalam data dengan bentuj baris atau list. Pencarian menggunakan sequential searching sangat mudah yaitu dilakukan dengan memeriksa satu per satu data secara berurutan untuk memastikan kecocokan antara tiap-tiap data dengan data yang dicari. Data-data yang dicari dapat beraneka ragam, menyesuaikan dari kebutuhan program.

Berikut merupakan ilustrasi dari sequential searching :

![](https://www.tutorialspoint.com/data_structures_algorithms/images/linear_search.gif)

Kelebihan dari algoritma ini adalah sangat mudah diimplementasikan, namun algoritma ini juga memiliki kelemahan yaitu membutuhkan waktu pemrosesan yang besar ketika data yang dicari terdapat di dalam kumpulan data yang sangat besar.

Berikut merupakan contoh kode program `Sequential Search` :

``````C
#include <stdio.h>

int main()
{

    int BarisAngka[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int cari;
    printf("Masukkan angka yang dicari : ");
    scanf("%d", &cari);
    for (int a = 0; a < sizeof(BarisAngka); a++)
    {
        if (BarisAngka[a] == cari)
        {
            printf("Angka %d ditemukan pada urutan ke %d\n", cari, a + 1);
            break;
        }
        else if (a == sizeof(BarisAngka) - 1 && BarisAngka[a] != cari)
        {
            printf("Angka tidak ditemukan\n");
        }
    }
}
``````

# Soal Latihan
1. Buatlah array 2 dimensi dengan ukuran 3x3 dan lakukan pencarian terhadap suatu angka di dalam array 2 dimensi tersebut. Jika angka ditemukan, outputkan baris dan kolom dari angka tersebut dan jika tidak, maka outputkan angka tidak ditemukan.
   
   Input :
   ``````
   5
   ``````
   Output :
   ``````
   Angka 5 berada pada baris ke 5 kolom ke 2.
   ``````
2. Buatlah program untuk menghitung jumlah setiap huruf dari sebuah kalimat

   Input : 
   ``````
   "apa kabar semuanya, apakah semuanya baik baik saja";
   ``````
   Output :
   ``````
   huruf a ada 15
   huruf b ada 3
   huruf e ada 2
   huruf h ada 1
   huruf i ada 2
   huruf j ada 1
   huruf k ada 4
   huruf m ada 2
   huruf n ada 2
   huruf p ada 2
   huruf r ada 1
   huruf s ada 3
   huruf u ada 2
   huruf y ada 2
   ``````

3. Buatlah Sequential Algoritm dengan menggunakan while looping.
