# parser-code-with-C-and-convert-it-to-assembly-languange
tugas

parser adalah suatu code yang dapat digunakan untuk mencari keyword yang tersedia dari inputan yang belum lengkap.
parser code ini banyak diaplikasikan, seperti untuk mendapatkan keyword yang diinginkan ketika mengetik sesuatu pada kolom search engine seperti google.
parser juga dapat digunakan sebagai translator, misalnya ketika seorang programmer menulis code dengan bahasa C dan ingin menerjemahkannya ke python, metode ini dapat digunakan.

berikut programnya dalam bahasa C :

// Fa Destri Reynaldo
// 2015630018


#include <stdio.h>
#include <string.h>

// parser program


struct Keywords // tipe data structur yang di dalamnya terdapat komponen tipe data char nama
{
	char kunci[10];
} ;

int main () // main execute
{
	Keywords kata[10];
	
	strcpy(kata[0].kunci ,"Makan");

	strcpy(kata[1].kunci ,"Piring");

	strcpy(kata[2].kunci ,"Pizza");

	strcpy(kata[3].kunci ,"Gelas");

	strcpy(kata[4].kunci ,"Gantungan");

	strcpy(kata[5].kunci ,"Badak");
	
	strcpy(kata[6].kunci ,"Mobil");
	
	strcpy(kata[7].kunci ,"Sotong");
	
	strcpy(kata[8].kunci ,"Rambutan");
	
	strcpy(kata[9].kunci ,"Asteroid");

	int a=0;

	char input[10];
	printf("Keyword please : ");
	scanf("%s", &input); // input dengan tipe data string at least 3 character
	
	//parser code
	int b, count[10]={0,0,0,0,0,0,0,0,0,0};
	for (a=0; a<10; a++)
	{
		for(b=0; b<10; b++)
		{
			if(input[b] == kata[a].kunci[b])
			{
				count[a]++;
			}
		}
	}

	
	int z=count[0];
	for(a=0; a<10; a++)
	{
		if(z < count[a]){
			z = count[a];
		}
		
	}

	for(a=0; a<10; a++)
	{
		if( z == count[a])
		{
			printf("did you mean  %s ?", kata[a].kunci ); //output
			return 0; 
		}

	}


}

dari code di atas ketika di compile menghasilkan : 

file:///C:/Users/johannes/Desktop/a.jpg

