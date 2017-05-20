#include<stdio.h>
int *key_schedule(int key[8]);
int prga(int S[256]);
main(){
	int a,i,k,key[8],S[256];
	printf("Enter key from {0,255}");
	scanf("%d",&k);
	for(i=7;i>=0;i--){
		key[i]=k%2;
		k=k/2;
	}
	*S=key_schedule(key);
	a=prga(S);
	printf("%d",a);
}
int *key_schedule(int key[8]){
	int S[256],i,j,c;
	for (i=0;i<256;i++){
    	S[i] = i;
		}
	j = 0;
	for (i=0;i<256;i++){
	    j = (j + S[i] + key[i%8])%256;
	    c=S[i];S[i]=S[j];S[j]=c;
	}
	return *S;
}
int prga(int S[256]){
int i=0,j=0,c,K;
    i=(i+1)%256;
    j=(j+S[i])%256;
    c=S[i];S[i]=S[j];S[j]=c;
    K=S[(S[i]+S[j])%256];
    return K;
}
