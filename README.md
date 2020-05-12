# TA Algo semester2
//Penggabungan void(fungsi),array,pointer&operasi file
#include <fstream>
#include <conio.h>
#include <iostream>
using namespace std;

void file(){
	string baris, beras, gula, susu;
	int jumlah;
	int bahan[3]={35000, 20000, 15000},*x , *y , *z;
	x=&bahan[0];
	y=&bahan[1];
	z=&bahan[2];
	
    ofstream outfile;
    outfile.open("cnthfile.txt");
    outfile << "============================================="<<endl;
	outfile << "\nBerikut adalah Barang yang Anda Pesan "<<endl;
    while(true){
        cout << "- ";
        getline(cin, baris);
		if(baris == "ok") break;
        if(baris=="beras"){
        	outfile <<"Beras : "<<*x<<endl;
		};
		if(baris=="gula"){
        	outfile <<"Gula : "<<*y<<endl;
		};
		if(baris=="susu"){
        	outfile <<"Susu : "<<*z<<endl;
		};
    }
    outfile<<"Total Harga Barang Yang Anda Pesan : ";
	jumlah=0;
    for (int i=0; i<3; i++){
		jumlah = jumlah + bahan[i];
		}
	outfile<<jumlah;
	outfile<<"\n\nTerima Kasih Telah Berbelanja di Toko Kami"<<endl;
	outfile<<"Semoga Datang Kembali"<<endl;
	outfile<<"=============================================";
    outfile.close();
		
    ifstream infile;
    infile.open("cnthfile.txt");
 
    if (infile.is_open())
    {	
        while ( getline (infile,baris) )
        {
            cout << baris << '\n';
        }
        infile.close();
    }
    else cout << "Unable to open file";
}

void bahan(){
	int bahan[3]={35000, 20000, 15000}, *x , *y , *z;
	x=&bahan[0];
	y=&bahan[1];
	z=&bahan[2];

    cout << "Selamat Datang di Toko Kami" << endl;
    cout << "Silahkan Tulis Barang yang Anda Inginkan"<<endl;
    cout << "Berikut adalah barang yang tersedia : "<<endl;
    cout << "1. Beras	"<<*x<<endl;
    cout << "2. Gula		"<<*y<<endl;
    cout << "3. Susu		"<<*z<<endl;
    cout << "Jika Sudah Selesai Ketik 'ok'"<<endl;
}

main () {
	bahan();
	file();
	cout << "\nSilahkah Menunggu Struk Anda"<<endl;
    cout <<" . . . . . . . . . . . . . . . . . ."<<endl;
    return 0;
}
