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

hasil compile dapat dilihat pada a.jpg b.jpg & c.jpg


berikut hasil convert dari bahasa C ke bahasa assembly : 

.LC0:
  .string "Keyword please : "
.LC1:
  .string "%s"
.LC2:
  .string "did you mean %s ?"
main:
  push rbp
  mov rbp, rsp
  sub rsp, 176
  lea rax, [rbp-112]
  mov DWORD PTR [rax], 1634427213
  mov WORD PTR [rax+4], 110
  lea rax, [rbp-112]
  add rax, 10
  mov DWORD PTR [rax], 1769105744
  mov WORD PTR [rax+4], 26478
  mov BYTE PTR [rax+6], 0
  lea rax, [rbp-112]
  add rax, 20
  mov DWORD PTR [rax], 2054842704
  mov WORD PTR [rax+4], 97
  lea rax, [rbp-112]
  add rax, 30
  mov DWORD PTR [rax], 1634493767
  mov WORD PTR [rax+4], 115
  movabs rax, 7018699995023827271
  mov QWORD PTR [rbp-72], rax
  mov WORD PTR [rbp-64], 110
  lea rax, [rbp-112]
  add rax, 50
  mov DWORD PTR [rax], 1633968450
  mov WORD PTR [rax+4], 107
  lea rax, [rbp-112]
  add rax, 60
  mov DWORD PTR [rax], 1768058701
  mov WORD PTR [rax+4], 108
  lea rax, [rbp-112]
  add rax, 70
  mov DWORD PTR [rax], 1869901651
  mov WORD PTR [rax+4], 26478
  mov BYTE PTR [rax+6], 0
  lea rax, [rbp-112]
  add rax, 80
  movabs rdi, 7953766464424337746
  mov QWORD PTR [rax], rdi
  mov BYTE PTR [rax+8], 0
  lea rax, [rbp-112]
  add rax, 90
  movabs rcx, 7235436813466497857
  mov QWORD PTR [rax], rcx
  mov BYTE PTR [rax+8], 0
  mov DWORD PTR [rbp-4], 0
  mov edi, OFFSET FLAT:.LC0
  mov eax, 0
  call printf
  lea rax, [rbp-122]
  mov rsi, rax
  mov edi, OFFSET FLAT:.LC1
  mov eax, 0
  call scanf
  mov QWORD PTR [rbp-176], 0
  mov QWORD PTR [rbp-168], 0
  mov QWORD PTR [rbp-160], 0
  mov QWORD PTR [rbp-152], 0
  mov QWORD PTR [rbp-144], 0
  mov DWORD PTR [rbp-4], 0
.L6:
  cmp DWORD PTR [rbp-4], 9
  jg .L2
  mov DWORD PTR [rbp-8], 0
.L5:
  cmp DWORD PTR [rbp-8], 9
  jg .L3
  mov eax, DWORD PTR [rbp-8]
  cdqe
  movzx ecx, BYTE PTR [rbp-122+rax]
  mov eax, DWORD PTR [rbp-8]
  movsx rsi, eax
  mov eax, DWORD PTR [rbp-4]
  movsx rdx, eax
  mov rax, rdx
  sal rax, 2
  add rax, rdx
  add rax, rax
  add rax, rbp
  add rax, rsi
  sub rax, 112
  movzx eax, BYTE PTR [rax]
  cmp cl, al
  jne .L4
  mov eax, DWORD PTR [rbp-4]
  cdqe
  mov eax, DWORD PTR [rbp-176+rax*4]
  lea edx, [rax+1]
  mov eax, DWORD PTR [rbp-4]
  cdqe
  mov DWORD PTR [rbp-176+rax*4], edx
.L4:
  add DWORD PTR [rbp-8], 1
  jmp .L5
.L3:
  add DWORD PTR [rbp-4], 1
  jmp .L6
.L2:
  mov eax, DWORD PTR [rbp-176]
  mov DWORD PTR [rbp-12], eax
  mov DWORD PTR [rbp-4], 0
.L9:
  cmp DWORD PTR [rbp-4], 9
  jg .L7
  mov eax, DWORD PTR [rbp-4]
  cdqe
  mov eax, DWORD PTR [rbp-176+rax*4]
  cmp DWORD PTR [rbp-12], eax
  jge .L8
  mov eax, DWORD PTR [rbp-4]
  cdqe
  mov eax, DWORD PTR [rbp-176+rax*4]
  mov DWORD PTR [rbp-12], eax
.L8:
  add DWORD PTR [rbp-4], 1
  jmp .L9
.L7:
  mov DWORD PTR [rbp-4], 0
.L13:
  cmp DWORD PTR [rbp-4], 9
  jg .L10
  mov eax, DWORD PTR [rbp-4]
  cdqe
  mov eax, DWORD PTR [rbp-176+rax*4]
  cmp DWORD PTR [rbp-12], eax
  jne .L11
  lea rcx, [rbp-112]
  mov eax, DWORD PTR [rbp-4]
  movsx rdx, eax
  mov rax, rdx
  sal rax, 2
  add rax, rdx
  add rax, rax
  add rax, rcx
  mov rsi, rax
  mov edi, OFFSET FLAT:.LC2
  mov eax, 0
  call printf
  mov eax, 0
  jmp .L12
.L11:
  add DWORD PTR [rbp-4], 1
  jmp .L13
.L10:
  mov eax, 0
.L12:
  leave
  ret

di atas merupakan hasil convert dari bahasa C ke bahasa assembly...
(pada saat pengeditan bahasa assembly pada readme.md ini tersusun rapi, tetapi setelah dilihat kembali bukan dalam mode pengeditan hasilnya berantakan), saya tidak tau penyebabnya apa....


untuk gambar yang jelasnya, silahkan di lihat pada file :
1.jpg
2.jpg
3.jpg
4.jpg
5.jpg
