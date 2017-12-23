# parser-code-with-C-and-convert-it-to-assembly-languange
tugas

parser adalah suatu code yang dapat digunakan untuk mencari keyword yang tersedia dari inputan yang belum lengkap.
parser code ini banyak diaplikasikan, seperti untuk mendapatkan keyword yang diinginkan ketika mengetik sesuatu pada kolom search engine seperti google.
parser juga dapat digunakan sebagai translator, misalnya ketika seorang programmer menulis code dengan bahasa C dan ingin menerjemahkannya ke python, metode ini dapat digunakan.
dari berbagai situs internet yang saya lihat, program parser ini kebanyak menggunakan teks file sebagai keyword nya. dan programnya pun mengolah data yang terdapat pada teks file tersebut.

tetapi disini saya hanya menggunakan 10 keyword yang tersedia, yaitu :
1.makan
2.piring
3.pizza
4.gelas
5.gantungan
6.badak
7.mobil
8.sotong
9.rambutan
10.asteroid

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

hasil compile dapat dilihat pada a.jpg b.jpg & c.jpg
![a](https://user-images.githubusercontent.com/32272275/34321177-8c739634-e83b-11e7-9db3-145953f60c1d.jpg)

![b](https://user-images.githubusercontent.com/32272275/34321179-920fa948-e83b-11e7-9514-acf4e9cff406.jpg)

![c](https://user-images.githubusercontent.com/32272275/34321182-98ba1a1c-e83b-11e7-8460-e9a7653e08dc.jpg)


berikut hasil convert dari bahasa C ke bahasa assembly : 

![1](https://user-images.githubusercontent.com/32272275/34321207-104b2710-e83c-11e7-857a-a3d06e21ebfd.jpg)

![2](https://user-images.githubusercontent.com/32272275/34321208-13e9a554-e83c-11e7-9dd1-8dad74886918.jpg)

![3](https://user-images.githubusercontent.com/32272275/34321209-18041c46-e83c-11e7-9184-464d8cd83768.jpg)

![4](https://user-images.githubusercontent.com/32272275/34321211-1be5be50-e83c-11e7-97b2-b5a454b4ef86.jpg)

![5](https://user-images.githubusercontent.com/32272275/34321212-20149d48-e83c-11e7-95f6-624d82ed6cac.jpg)
