Sublime运行C 快捷键：Ctrl+Shift+B 
或者：ctrl+B编译


strcpy函数与memcpy函数实现


	#include
	
	char *strcpy(hcar * strDtest, const char * strSrc){
		
		if((strDtest== null)|| (strSrc == null) ){
		  return null;
		}
		char *strDestCopy=strDest;

		while((*strDtest++= *strSrc++)!="\0");
		
		return strDestCopy;
	
	}


	int getStrLen(const char *strSrc){
     int len=0;
	   while(*strSrc++ !="\0"){
	       len++;
		} 
	  return len;  
	}
	


	int main(){
		
		char strSrc[]="hello world";	
		char strDest[2];		
		int len=0;		
		len =getStrLen(stcpy(strDest,strSrc));
		printf("strDest:%s\n",strDest);		
		printf("Length of strDest:%d\n",len); 		
		return 0;
	
	}





	ListNode *result=null;
	
		while(head){
		    temp = head->next;
			head->next = result;
			result = head;
			head = temp;
		
		}
	
	return result;

-------------------------------------------------------------

2017/07/16 学习笔记

	#ifndef _HELLO_H_
	#define _HELLO_H_
	........
	
	#endif

指针：：

int number = 10；
int *pointer = &number; 
或者 pointer = &number;

result = *pointer +5   // 15


scanf("%d",pointer);

-------
int *pvalue =0;
因为 NULL等于0，如果要测试指针pvalue是否为null，可以这么判断：
if(!pvalue){

}

-------
输入一个字符：
char single;
scanf("%c",&single);

字符串：
char multiple[12];
scanf("%s",multiple);

char multiple = "hello hhhhhhhhhhhh";

char *p = &multiple[0]; 等价于 multipe；

*(P+i) 等价于 multiple[i]

long multiple[] = {23l,322l,85l,74l,80l};
long *p = multiple;

遍历：：：
for(int i=0; i< sizeof(multiple)/sizeof(multiple[0]); i++){

..........

}


-------------------
动态内存分配：：：

int *pNumber = (int *)malloc(100);

使用之前最好做判断：
if(pNumber == NULL){
   ...........
}

pNumber = (int *)malloc(75*sizeof(int));


用calloc()分配内存
int *pNumber = (int *) calloc(75, sizeof(int));

释放动态分配的内存
free(pNumber)

函数中使用指针：：：：

int  main（void）{

int number = 10;
int *pnumber = &number;
int result = 0;

result = change(pnumber);

printf("\nIn main,result = %d\tnumber = %d",result,number);

return 0;
}

int change(int *pnumber){

*pnumber *=2;
printf("\nIn function change.*pnumber = %d\n",*pnumber);
return *pnumber;

}

结果输出：
In function change.*pnumber = 20
In main,result = 20 number = 20



3、函数指针：：：：：

int sum(int a ,int b);
int (*pfun)(int,int) = sum;
int result = pfun(45 ,55);

int product(int a ,int b);

pfun = product;

result = pfun(5,12);

-----------------

	int sum(int,int);
	int product(int,int);
	int defferent(int,int);
	
	int main(void){
	
		int (*pfun)(int,int);
		
		pfun = sum;
		result = pfun(a,b);
		
		pfun =product;
		result = pfun(a,b);		
		
		pfun =defferent;
		result = pfun(a,b);
		
		return 0;	
	}
	
	int sum(int x,int y)
	{
		return x+y;
	}

冒泡排序：：：
# include <stdio.h>
void sort(int * a,int len ){
	for(int i=0;i<len-1;i++){

		int t;
		for(int j=0;j<len-i-1;j++){
			if(a[j]>a[j+1]){

				t=a[j+1];
				a[j+1]=a[j];
				a[j]=t;
			}
		}
	}

}
 
/*void sort(int * a, int len)
{
	int i, j, t;

	for (i=0; i<len-1; ++i)
	{
		for (j=0; j<len-1-i; ++j)
		{
			if (a[j] > a[j+1])   
			{
				t = a[j];
				a[j] = a[j+1];
				a[j+1] = t; 
			}
		}
	}
}*/

int main(void)
{
	int a[6] = {10, 2, 8, -8, 11, 0};
	int i = 0;

	sort(a, 6);

	for (i=0; i<6; ++i)
	{
		printf("%d ", a[i]);
	}
	printf("\n");

	return 0;
}




***************************************

	# include <stdio.h>
	# include <string.h>
	
	struct Student
	{
		int age;
		char sex;
		char name[100];
	}; //分号不能省
	
	void InputStudent(struct Student *);
	void OutputStudent(struct Student *);
	int main(void)
	{
		struct Student st ;  //15行
		//printf("%d\n", sizeof(st));
	
		InputStudent(&st); //对结构体变量输入  必须发送st的地址
		OutputStudent(&st); //对结构体变量输出  可以发送st的地址也可以直接发送st的内容 但为了减少内存的耗费，也为了提高执行速度，推荐发送地址
	
		return 0;
	}
	
	void OutputStudent(struct Student *pst)
	{
		printf("%d %c %s\n", pst->age, pst->sex, pst->name);
	}
	
	void InputStudent(struct Student * pstu) //pstu只占4个字节
	{
		(*pstu).age = 10;
		strcpy(pstu->name, "张三");
		pstu->sex = 'F';	
	}
	
	/*
	//本函数无法修改主函数15行st的值 所以本函数是错误的
	void InputStudent(struct Student stu)
	{
		stu.age = 10;
		strcpy(stu.name, "张三");  //不能写成 stu.name = "张三";
		stu.sex = 'F';
	}
	*/

************************************
enum：
# include <stdio.h>

//只定义了一个数据类型，并没有定义变量， 该数据类型的名字是 enum WeekDay 
enum WeekDay
{
	MonDay, TuesDay, WednesDay, ThursDay, FriDay, SaturDay, SunDay
};

int main(void)
{
	//int day; //day定义成int类型不合适
	enum WeekDay day = SunDay;
	printf("%d\n", day);   
	return 0;
}

*************************************88
指针：：：：：

	#define _CRT_SECURE_NO_WARNINGS
	# include <stdio.h>  
	# include <string.h>  
	# include <stdlib.h>  
	# include <stdio.h>
	# include <malloc.h> 
	
	#define LEN 20  
	typedef struct person
	{
		char name[LEN];
		int  age;
	}person;
	
	// 返回0表示失败，返回1表示成功  
	int mallocAndInit(person **ppPs)
	{
		*ppPs = (person*)malloc(sizeof(person));
		if (NULL == *ppPs)
		{
			// 内存分配失败  
			fprintf(stderr, "Malloc failed.\n");
			return 0;
		}
		// 初始化  
		(*ppPs)->age = 0;
		strcpy((*ppPs)->name, "");
		return 1;
	}
	
	void main()
	{
		person *pTest = NULL;
		person **pptest = &pTest;   // 二级指针要指向准备使用的一级指针！！！  
		// 这里通过二级指针获取到了函数内部为一级指针分配的内存，即改变了一级指针的地址  
		if (!mallocAndInit(pptest))
		{
			fprintf(stderr, "Error.\n");
			exit(1);
		}
		// 这里不会再出错  
		printf("The person's name is %s, age is %d.\n", pTest->name, pTest->age);
		// 释放内存并还原  
		if (pTest != NULL)
		{
			free(pTest);
			pTest = NULL;
			pptest = NULL;
		}
	}


6、申请堆空间：
new和delete代替malloc和free，是书写更加流畅，尤其申请堆内数组更直观。
例如：
a)申请1个普通变量 int *p = new int;  delete p;
b)申请数组 int *p = new int[10];  delete []p;
c)申请结构体对象：SData * p = new SData; delete p;
d)申请结构体数组：SData * p = new SData[20]; delete []p;
e)申请指针数组：SData* *p[100] = SData* [20]; delete[]p;
Demo::
///:::::申请一个数组
#define _CRT_SECURE_NO_WARNINGS
#include <iostream>   
using namespace std;

struct sData
{
 int nNumb;
char sName[20];
float fMatch;
}

int main()
{
	/*sData * p=new sData;
	p->nNumb = 1009;
	strcpy(p->sName,"aaaaa");
	p->fMah =89.4f;
	delete p;*/

	sData * p=new sData[20];
	p[0].nNumb = 1032;
	strcpy(p[0]->sName,"aaaaa");
	p[0]->fMah =89.4f;
	delete []p;

	return;
}

/*
int main(){
	int a[10] = {1,2,3,4,5,6,7,8,9,0};
	int i=0;
	int *p = (int*)malloc(sizeof(int)*10);
	int i=0;
	int *p = (int*)malloc(sizeof(int)*10);
	int *p =new int[10];
	
	while(i<_countof(a)){
	  p[i] = a[i++];
	}
	
	while(i<_countof(a)){
	  p[i] = a[i++];
	 cout<< p[i++]<<endl;	
	}

	//a是栈内的空间不用delete删除
	delete []p;
	return 0;
}*/


///Demo2::
#include <iostream>   
using namespace std;
//#define max(a,b) a>b?a:b;
/*
int max(int a,int b)
{
 return  a>b?a:b;
}

inline int max(int a,int b){
 return  a>b?a:b;
}

int main(){
 int k=max(32,33);
 return 0;
}

////Demo3:::
#include <iostream>   
using namespace std;

Struct STime
{
	int nHour;
	int nMin;
	int nSec;
	void SetTime(int h,int m ,int s){
		nHour = h;
		nMin = m;
		nSec = s;
	}
}

int main()
{
 STime Morn,noon;
Morn.setTime(9,60,51);
noon.setTime(19,52,92);
}


////Demo4:::
缺省函数

#include<studio.h>

int add (int a , int b=10,int c= 12){
  return a+b+c;
}

int main()
{
 int k = add(12,15);
add(4);
add(7,24);
add(21,213,25);
}



////Demo5::
C++:

void swap(int& i,int& j)
{
	int tmp=i;
	i =j;
	j=tmp;
}

void main()
{
	int i=10;
	int j=20;
	swap(i,j);
}

C:::
void swap(int* i,int* j)
{
int tmp=*i;
*i = *j;
*j =tmp;
}
void main()
{
	int i=10;
	int j=20;
	swap(&i,&j);
}
 


Demo5：：
#pragma once
#include <iostream>
using namespace std;
typedef int DATA;
struct SNode
{
	DATA data;
	SNode* pNext;
};

class CList
{
	SNode* m_pHead;
public:
	 void AddHead(DATA data) {
		 SNode* p = new SNode;
		 p->data = data;
		 p->pNext = m_pHead;
		 m_pHead = p;
	}
	void AddTail(DATA data) {
		SNode* pNew = new SNode;
		pNew->data = data;
		pNew->pNext = NULL;
		if (!m_pHead) {
			m_pHead = pNew;
			return;
		 }
		SNode* p = m_pHead;
			while (p->pNext != NULL) {
				p = p->pNext;
			}
			p->pNext = pNew;
	} 
	int  GetCount() {
		SNode* p = m_pHead;
		int i = 0;
		while (p) {
			++i;
			p = p->pNext;
		}
		return i;
	}


};

int main() {
	CList list; 
	list.AddHead(2);
	list.AddHead(32);
	list.AddHead(24);
	list.AddTail(53);
}


////////////////////////////////////////////////////

#define  _CRT_SECURE_NO_WARNINGS

#include <iostream>

using namespace std;
//1、申请1个普通变量 int *p = new int;  delete p;
//2、申请数组 int *p = new int[10];  delete []p;
//3、申请结构体对象：SData * p = new SData; delete p;
//4、申请结构体数组：SData * p = new SData[20]; delete []p;
//5、申请指针数组：SData* p[100] = { NULL }; delete[]p;
struct SData
{
	int nNumb;
	char sName[20];
	float fMath;
};
int main()
{
	//int *p = new int(5);//初始化堆空间语句
	int *p = new int[5];
	p[0] = 32;
	p[1] = 22;
	p[2] = 54;	
	p[4] = 22;
	p[3] = 54;

	int i = 0;
	while (i < 5)
		cout << p[i++] << endl;
	delete []p;
	
	return 0;
}
/*
SData * p = new SData;//0...19
p->nNumb = 1032;
strcpy(p->sName, "bbb");
p->fMath = 85.5f;

delete p;
*/
/*
SData * p = new SData[20];//0...19
p[0].nNumb = 1032;
strcpy(p[0].sName, "bbb");
p[0].fMath = 85.5f;

delete []p;

*/
/*
int a[10] = { 2,35,6,7,8,9,9 };
int i = 0;
//int *p = (int*)malloc(sizeof(int) * 10);
int *p = new int[10];

while (i < _countof(a))
p[i] = a[i++];
i = 0;
while (i < _countof(a))
cout << p[i++] << endl;

delete []p;

*/