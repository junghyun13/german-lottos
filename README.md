# german-lottos
# c
독일 로또는 {1, 2, ..., 49}에서 수 6개를 고른다. 로또 번호를 선택하는데 사용되는 가장 유명한 전략은 49가지 수 중 a(a>6)개의 수를 골라 집합 aa를 만든 다음 그 수만 가지고 번호를 선택하는 것이다.  첫 번째 수는 a (6 &lt; a &lt; 13)이고, 다음 k개 수는 집합 aa에 포함되는 수이다. aa의 원소는 오름차순으로 주어진다. 집합 aa와 a가 주어졌을 때, 수를 고르는 모든 방법을 출력하는 프로그램을 작성해보자!

#include <stdio.h>
#include <stdlib.h>

int aa[100];
int ab[100];
int a;

void dfs(int start,int depth){
	int i;
	if(depth==6){
		for(i=0;i<6;i++){
			printf("%d ",ab[i]);}
		printf("\n");}
	else{
	    for(i=start;i<a;i++){
	    	ab[depth]=aa[i];
			printf("흠..\n");
	    	dfs(i+1,depth+1);
			printf("여기");}}
}


int main(){
	int i;
	while(1){
	scanf("%d",&a);
	if(a==0){
		break;}
	for(i=0;i<a;i++){
		scanf(" %d",&aa[i]);}
	dfs(0,0);
	printf("더이상 구하기 싫다면 0을 입력해주세요!");
	printf("\n");}
    return 0;
}
