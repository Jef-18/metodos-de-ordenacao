#include <stdio.h>
#include <stdlib.h>
#include <time.h>

//Autor: Jeferson Almeida

int tamanhoVetor;
void quick(int vetor[tamanhoVetor], int inicio, int fim);

int main(){
    
    int i, opcao, tamanhoVetor, limiteMaximo; //VARIÁVEIS PARA O TAMANHO DO VETOR
    int it, pos, temp;                        //VARIÁVEIS DO BUBBLE SORT
    int posMenorInicial=0, posMenor=0;        //VARIÁVEIS DO SELECTION SORT 
    int carta, j, aux;                        //VARIÁVEIS DO INSERTION SORT 
    
    //VARIÁVEIS PARA CALCULAR O TEMPO
    clock_t Ticks[2];
    Ticks[0] = clock();
    double Tempo;   

    printf("\n Tamanho do Vetor: ");
    scanf("%d", &tamanhoVetor);
    
    printf("\n Gerar valores aleatórios até: ");
    scanf("%d", &limiteMaximo);
    
    int vetor[tamanhoVetor];
    srand(time(NULL));
    for(int i = 0; i < tamanhoVetor; i++){
        vetor[i] = rand() % limiteMaximo;
        printf(" %d ", vetor[i]);
    }
    
    do{
        printf("\n\n\n");
        printf(" ************* MÉTODOS DE ORDENAÇÃO *************\n\n");
        printf(" 1 - BUBBLE SORT\n");
        printf(" 2 - SELECTION SORT\n");
        printf(" 3 - INSERTION SORT\n");
        printf(" 4 - QUICK SORT\n");
        printf(" 5 - TENTAR NOVAMENTE\n");
        printf(" 6 - SAIR\n");
        printf("\n Escolha a opção desejada: ");
        scanf("%d",&opcao);
        system("cls || clear");
        
        switch(opcao){
            
            case 1:
            
                printf("\n 1 - BUBBLE SORT\n");
                for(it=0; it < tamanhoVetor - 1; it++){
                    printf("\n Iteração: %d\n", it);
                    printf(" -----------\n\n");
                    
                    for(pos=0; pos < tamanhoVetor-it-1; pos++){
                        
                        if(vetor[pos] < vetor[pos+1]){
                            temp = vetor[pos];
                            vetor[pos] = vetor[pos+1];
                            vetor[pos+1] = temp;
                        }
                        
                    }
                    for(int i=0; i < tamanhoVetor; i++){
                        printf(" %d ", vetor[i]);
                    }
                    printf("\n");
                    
                }    
                Ticks[1] = clock();
                Tempo = (Ticks[1] - Ticks[0]) * 1000.0 / CLOCKS_PER_SEC;
                printf("\n Tempo gasto: %g ms.", Tempo);
                getchar();
                
                break;
                
            case 2:
                
                printf("\n 2 - SELECTION SORT\n");
                    for(it = 0; it < tamanhoVetor - 1; it++){
                    posMenorInicial = it;
                    
                    for(int i = posMenorInicial+1; i< tamanhoVetor; i++){
                        if(vetor[i] > vetor[posMenor]){
                            posMenor = i;
                        }
                    }
                    if(vetor[posMenor] > vetor[posMenorInicial]){
                        temp = vetor[posMenorInicial];
                        vetor[posMenorInicial] = vetor[posMenor];
                        vetor[posMenor] = temp;
                    }
                    
                    printf("\n Iteração: %d\n", it);
                    printf(" -----------\n\n");
                    
                    for(int i = 0; i < tamanhoVetor; i++){
                        printf(" %d ", vetor[i]);
                    }
                    printf("\n");
                }
                Ticks[1] = clock();
                Tempo = (Ticks[1] - Ticks[0]) * 1000.0 / CLOCKS_PER_SEC;
                printf("\n Tempo gasto: %g ms.", Tempo);
                getchar();
                
                break;
                
            case 3:
            
                printf("\n 3 - INSERTION SORT\n");
                for(it = 1; it < tamanhoVetor; it++){
                    carta = vetor[it];
                    for(j = it - 1; (j >= 0) && vetor[j] < carta; j--){
                        vetor[j+1] = vetor[j];
                    }
                    
                    vetor[j+1] = carta;
                    printf("\n Iteração: %d\n", it);
                    printf(" -----------\n\n");
                    
                    for(int i = 0; i < tamanhoVetor; i++){
                        printf(" %d ", vetor[i]);
                    }
                    printf("\n");
                }
                Ticks[1] = clock();
                Tempo = (Ticks[1] - Ticks[0]) * 1000.0 / CLOCKS_PER_SEC;
                printf("\n Tempo gasto: %g ms.", Tempo);
                getchar();
                
                break;
                
            case 4: 
                
                printf("\n 4 - QUICK SORT\n");             
                printf("\n Vetor inicial: \n\n");
                for(int i = 0; i < tamanhoVetor; i++){
                    printf(" %d ", vetor[i]);
                }
                
                quick(vetor, 0, tamanhoVetor-1);
                
                printf("\n Vetor final: \n\n");
                for(int i = 0; i < tamanhoVetor; i++){
                    printf(" %d ", vetor[i]);
                }
                printf("\n");
                
                Ticks[1] = clock();
                Tempo = (Ticks[1] - Ticks[0]) * 1000.0 / CLOCKS_PER_SEC;
                printf("\n Tempo gasto: %g ms.", Tempo);
                getchar();

                break;
                
            case 5:
                main();
                
                break;
                
            case 6:
                printf("\n The end!");
                return 0;
                
                break;
                
            default:
            printf("\n\t Opção não encontrada, por favor tente novamente.");
        }

    }while(opcao != 6); 
}
 
void quick(int vetor[tamanhoVetor], int inicio, int fim){
    
    int i, j, pivo, meio, temp;
    int k;
    
    i = inicio;
    j = fim;
    
    meio = (int)((i + j)/2);
    pivo = vetor[meio];
    
    do{
        
       while(vetor[i] > pivo) {
           i++; 
       }
       
       while(vetor[j] < pivo) {
           j--;
       }
       
       if(i <= j){
           temp = vetor[i];
           vetor[i] = vetor[j];
           vetor[j] = temp;
           i = i+1;
           j = j-1;         
       }
       
    }while(j > i);   //Enquanto os ponteiros não se cruzarem
    
    if(inicio < j){
       quick(vetor, inicio, j); 
    } 
    if(i < fim){
        quick(vetor, i, fim);    
    }    
}
    

