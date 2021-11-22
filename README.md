#define _CRT_SECURE_NO_WARNINGS

#include<stdio.h>

写代码判断当前机器的字节序
int main()

{

	int a = 1;
	char* p = (char*)&a;
	if (1 == *p)
	{
		printf("小端\n");
	}
	else
	{
		printf("大端\n");
	}
	return 0;
  
}

1.
int main()

{

	char a = -1;
	signed char b = -1;
	unsigned char c = -1;
	//10000000000000000000000000000001
	//11111111111111111111111111111110
	//111111111111111111111111 11111111
    //整型提升 unsigned 
	//00000000000000000000000011111111 - 255
	printf("a=%d,b=%d,c=%d", a, b, c);// -1 -1 255
	return 0;
  
}

2.

int main()

{

	char a = -128;
	//10000000000000000000000010000000
	//11111111111111111111111101111111
	//111111111111111111111111 11111110
	//整型提升 有符号
	//11111111111111111111111111111110
	printf("%u\n", a);
	return 0;
  
}

3.

int main()

{

	char a = 128;
	//000000000000000000000000 10000000
	//整型提升 有符号
	//11111111111111111111111110000000
	printf("%u\n", a);
	return 0;
  
}

4.
int main()

{

	int i = -20;
	unsigned int j = 10;
	printf("%d\n", i + j);//-10
	return 0;
}

5.
int main()

{

	unsigned int i;
	for (i = 9; i >= 0; i--)
	{
		printf("%u\n", i);//死循环
	}
	return 0;
  
}

6.
#include<string.h>

int main()

{

	char a[1000];
	int i;
	for(i = 0; i < 1000; i++)
	{ 
		a[i] = -1 - i;
	}
	//-1 -2 -3...-127 -128 127 126...0 -1
	printf("%d\n", strlen(a));//0='\0'  结果为255
	for (i = 0; i <= 254; i++)
	{
		printf("%d ", a[i]);
	}
	return 0;
  
}

7.
unsigned char i = 0;//0 - 255

int main()

{

	for (i = 0; i <= 255; i++)
	{
		printf("hello world\n");//死循环
	}
	return 0;
  
}
