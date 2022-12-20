# Pengertian Exception Handling
Dalam sebuah pemograman terdapat kemungkinan terjadi sebuah error yang disebabkan oleh user saat run time terjadi. Error ini terjadi bukan karena kesalahan penulisan kode program dan terjadi saat program tersebut sedang berjalan. Ketika error ini terjadi, maka program akan otomatis berhenti sehingga tidak melanjutkan kode program di bawahnya. Untuk itu terdapat `try and exception` sebagai solusi dalam mengatasi permasalahan tersebut. 

Exception handling bekerja dengan menangkap bug atau error massage yang terjadi dan menjadikannya `toString`. Hal tersebut memungkinkan terjadi karena Exception di dalam java merupakan sebuah class dan bug atau error yang muncul merupakan sebuah object.

Berikut merupakan daftar error yang dapat terjadi di dalam Java : 

|Exception|Deskripsi|
|---------|---------|
|ArithmetiException|Hasil perhitungan matematika error, seperti pembagian dengan 0|
|ArrayIndexOutOfBoundsException|Index array yang dituju melebihi panjang array|
|ArrayStoreException|Data yang diinputkan ke dalam array berbeda tipe datanya dengan tipe data arraynya|
|ClassCastException|Error yang terjadi ketika kita ingin merubah class dari sebuah object ke class lain|
|IllegalArgumentException|Mengirimkan argumen yang tidak sejenis dengan parameter tipe datanya|

