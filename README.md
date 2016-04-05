#include "stdafx.h"
#include <conio.h>
#include  <stdio.h>
#include <stdio.h>
#include <string.h>
#include <iostream>

using namespace System;






int coppy ()
{  
	setlocale(LC_ALL, "Russian");
	// Переменная, в которую будет помещен указатель на созданный
	// поток данных 
	FILE * dictionary;
	// Переменная, в которую поочередно будут помещаться считываемые строки
	char str[50];
	char kaka[1000000];

	//Указатель, в который будет помещен адрес массива, в который считана 
	// строка, или NULL если достигнут коней файла или произошла ошибка
	char *estr;

	// Открытие файла с режимом доступа «только чтение» и привязка к нему 
	// потока данных
	printf ("Открытие файла: ");
	dictionary = fopen ("dictionary.txt","r");

	// Проверка открытия файла
	if (dictionary == NULL) {printf ("ошибка\n"); return -1;}
	else printf ("выполнено\n");

	printf ("Считаны строки:\n");

	//Чтение (построчно) данных из файла в бесконечном цикле
	while (1)
	{
		// Чтение одной строки  из файла
		estr = fgets (str,sizeof(str),dictionary);
		strcat(kaka,str);

		//Проверка на конец файла или ошибку чтения
		if (estr == NULL)
		{
			// Проверяем, что именно произошло: кончился файл
			// или это ошибка чтения
			if ( feof (dictionary) != 0)
			{  
				//Если файл закончился, выводим сообщение о завершении 
				//чтения и выходим из бесконечного цикла
				printf ("\nЧтение файла закончено\n");
				break;
			}
			else
			{
				//Если при чтении произошла ошибка, выводим сообщение 
				//об ошибке и выходим из бесконечного цикла
				printf ("\nОшибка чтения из файла\n");
				break;
			}
		}
		//Если файл не закончился, и не было ошибки чтения 
		//выводим считанную строку  на экран
		printf ("     %s",str);
	}

	// Закрываем файл
	printf ("Закрытие файла: ");
	if ( fclose (dictionary) == EOF) 
		printf ("ошибка\n");
	else
		printf ("выполнено\n");
	printf("%s\n",& kaka);
	return 0;
} 
//  подсчет введеных символов  //
 

int count  characters()
{ int i=0;
char strol[50];
scanf("%s",&strol);
printf("%s\n",&strol);
i = strlen(strol);
printf("%d\n",i);
system("pause");
return 0;
}
// разделение строки на слова //
int divided str()
{ 
char str[]="sfaas  fsf sdf sd fsd";

char m[100][100];
int i=0;
char *p;
p = strtok(str," ");
while(p!=NULL){
	strcpy(m[i],p);
	i++;
	p=strtok(NULL," ");
}
int j=0;
for(int j=0;j<i;j++) {
	printf("%s \n",m[j]);
}
system("pause"); 
_getch;
return 0;
}

