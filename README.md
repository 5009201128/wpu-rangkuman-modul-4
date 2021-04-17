# wpu-rangkuman-modul-4
Laporan Rangkuman Pembelajaran
=>	Pointers
-	Merupakan penunjuk suatu variabel
-	Karena memori komputer berbentuk seperti rangkaian sel memori, maka dibutuhkan pendeklarasian untuk menyimpan suatu nilai dengan memberikan alamat pada lokasi tertentu dalam memori
Deklarasi :
int *ptr;
=>	Alamat operator 
-	Dimulai dengan tanda ampersand (&) yang berarti menunjukkan operator alamat

Contoh :

#include <iostream>
using namespace std;
int main (){
int a=5;
cout<<"masukkan nilai a= "<<a<<endl;
cout<<"masukkan alamat a= "<<&a<<endl;
cin, getch ();
return 0;
}

=>	Assignment variabel pointer
Pada assignment tidak perlu menggunakan tanda *

Contoh :

Int a, *ptr;
a = 5;
ptr = &a;


=>	Operator defference
-	Penggunaan tanda * pada operator berfungsi untuk mengakses nilai yang ditunjuk dari variabel pointer

Contoh :

#include <iostream>
using namespace std;
int main() {
int a = 5;
int *ptr;
ptr = &a;
cout << "Nilai variabel a adalah " << a << endl;
cout << "Alamat variabel a adalah " << &a << endl;
cout << "Isi dari variabel ptr adalah " << ptr << endl;
cout << "Nilai yang ada pada variabel ptr adalah " << *ptr << endl;
return 0;
}


=>	Double pointer
-	Sederhananya, pada suatu program dapat memuat lebih dari satu pointer sehingga terdapat dua simbol *

Contoh :

#include <stdio.h>
int main (void) {
int a = 5;
int *ptr = &a;
int **dbptr = &ptr;
printf ("%d\n", **dbptr);
return 0;
}

=>	Pointer dan Array
Array merupakan penyusunan data yang berupa sekuensial, sehingga alamat data yang disimpan secara berurutan.

Contoh :

#include <iostream>
using namespace std;
int main () {
int Array[5] = {1,3,5,7,8};
int *ptrArray;
ptrArray = Array;
cout << "Nilai pada elemen 0 Array adalah " << Array[0] << endl;
cout << "Nilai pada elemen 0 Array (ptr) adalah " << ptrArray << endl;
ptrArray++;
*ptrArray = 10;
cout << "Nilai pada elemen 1 Array adalah " << Array[1] << endl;
cout << "Nilai pada elemen 1 Array (ptr) adalah " << ptrArray << endl;
ptrArray = Array;
cout << endl;
cout << "Akses nilai semua array dengan pointer dan looping for" << endl;
for (int i=0; i<5; i++) {
cout << "Nilai indeks ["<<i<<"] adalah = " << *ptrArray+i << endl;
}
return 0;
}

=>	Pointer dan fungsi
Pada penggunaan pointer pada fungsi, pointer berfungsi untuk menunjukkan perubahan yang terjadi dengan cara meninjau input pada parameter. Biasanya, pada fungsi digunakan cara pass by value, namun bias juga menggunakan cara pass by argument.
-	Pass by value
Memiliki makna pengubahan argument yang disalin ke dalam parameter fungsi, namun perubahannya tidak mengubah variabel pada fungsi awal.

Contoh :

#include <stdio.h>

void change(int a, int b)
{
    a = a + 5;
    b = b + 5;
}

int main()
{
    int x = 10, y = 6;
    change(x, y);
    printf("%d %d\n", x, y);

    return 0;
}

-	Pass by reference
Sama halnya dengan pass by value, argument akan disalin ke parameter fungsi. Namun, bedanya pada pass by reference setiap perubahan yang terjadi akan berpengaruh terhadap variabel awal atau variabel aslinya

Contoh :

#include <stdio.h>

void change(int *a, int *b)
{
    *a = *a + 5;
    *b = *b + 5;
}

int main()
{
    int x = 10, y = 6;
    change(&x, &y);
    printf("%d %d\n", x, y);

    return 0;
}



Contoh Soal 1
Buatlah program untuk menampilkan alamat dari suatu fungsi.

Pembahasan:

#include <iostream>
using namespace std;
int main() {
int val = 100;
int *pointer;
pointer = &val;
cout << "Nilai variabel val adalah " << val << endl;
cout << "Alamat variabel val adalah " << &val << endl;
cout << "Isi dari variabel pointer adalah " << pointer << endl;
cout << "Nilai yang ada pada variabel pointer adalah " << *pointer << endl;
return 0;
}
