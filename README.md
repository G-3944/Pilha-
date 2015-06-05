# Pilha-
Estrutura de dados, pilha implementada em linguagem C
//PILHA alocação sequencial
#include <stdio.h>
#include <stdlib.h>
#define MAX 10

typedef struct{
	int v[MAX];
	int topo;
}Pilha;

int empty(Pilha *p);
int pop(Pilha *p);
void push(Pilha *p, int valor);
int size(Pilha *p);
int stackpop(Pilha *p);

int main(void){
	Pilha pilha;
	
	pilha.topo= -1;
	
	push(&pilha,1);
	push(&pilha,2);
	push(&pilha,3);
	printf("Elemento do topo da pilha %d\n",stackpop(&pilha));
	printf("Tamanho da pilha %d",size(&pilha));
	
	printf("\n%d",pop(&pilha));
	printf("\n%d",pop(&pilha));
	printf("\n%d",pop(&pilha));
	printf("\n%d",pop(&pilha));
	
	return 0;
}

//testar se a pilha está vazia
int empty(Pilha *p){
	if(p->topo==-1)
	{
		return 1;
	}
	else
	{
		return 0;
	}
}

//retorna Topo e diminui a posição da pilha
int pop(Pilha *p){
	if(empty(p)){
		printf("\nPilha vazia.");
		exit(1);
	}
	return (p->v[p->topo--]);
}

//empilhar
void push(Pilha *p, int valor){
	
	if(p->topo == (MAX-1))
	{
		printf("Estouro de pilha") ;
		exit(1);
	}
	//p->topo++;
	p->v[++(p->topo)] = valor;
	return;
}

//tamanho da pilha
int size(Pilha *p){
	return (p->topo+1);
}

//retorna o topo da pilha
int stackpop(Pilha *p){
	return p->v[p->topo];
}


