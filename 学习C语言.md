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




}






























 


