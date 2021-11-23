# hamming-working

#include<stdio.h>
void main(){
	int data[10];
	int dataatrec[10],c,c1,c2,c3,c4;
	scanf("%d",&data[0]);
	scanf("%d",&data[1]);
	scanf("%d",&data[2]);
	scanf("%d",&data[4]);
	
	data[6] = data[0]^data[2]^data[4];
	data[5] = data[0]^data[1]^data[4];
	data[3] = data[0]^data[1]^data[2];
	
	printf("hammi\n");
	for (int i = 0; i < 7; i++){
		printf("%d",data[i]);
	}
	printf("hammi222\n");
	for (int i = 0; i < 7; i++){
		scanf("%d",&dataatrec[i]);
	}
	c1=dataatrec[6]^dataatrec[4]^dataatrec[2]^dataatrec[0];
	c2=dataatrec[5]^dataatrec[4]^dataatrec[1]^dataatrec[0];
	c3=dataatrec[3]^dataatrec[2]^dataatrec[1]^dataatrec[0];
	c = 4*c3+2*c2+c1;
	
	if (c==0){
	
		printf("No error\n");
		
	}
	else{
			printf("\nerror found at %d",c);
		printf("\nData sent : ");
		for (int i = 0; i < 7; i++){
			printf("%d",data[i]);
		}
		printf("\nData recieved : ");
		for (int i = 0; i < 7; i++){
			printf("%d",dataatrec[i]);
		}
		printf("\nCorrect : ");
		if (dataatrec[7-c]==0){
			dataatrec[7-c]=1;
		}
		else{
			dataatrec[7-c]=0;
		}
		for (int i = 0; i < 7; i++){
			printf("%d",dataatrec[i]);
		}
	}
}
