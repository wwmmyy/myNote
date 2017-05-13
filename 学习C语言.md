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