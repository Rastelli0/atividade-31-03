# atividade-31-03

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(){
    float matriz[3][3], soma = 0, maior, menor, soma_imp = 0;
    int i, j, imp_sec, par_sec , par_prin , opcao, veri;
    char resp = 's';

    srand(time(NULL));

do{
        printf("\nMenu de Opcoes:\n");
        
        printf("0 - Numeros aleatorios na matriz\n");
        
        printf("1 - Cadastrar elementos na matriz\n");
        
        printf("2 - Imprimir a matriz\n");
        
        printf("3 - Somatoria dos elementos da matriz\n");
        
        printf("4 - Imprimir o maior e menor elemento da matriz\n");
        
        printf("5 - Contar os numeros pares da diagonal principal\n");
        
        printf("6 - Contar os numeros impares da diagonal secundaria\n");
        
        printf("7 - Contar os numeros pares da diagonal secundária\n");
        
        printf("8 - Somatoria dos elementos das linhas impares\n");
        
        printf("9 - Sair\n");
        
        printf("Escolha uma opcao: ");
        
        scanf("%d", &opcao);
        

    switch (opcao)
    {
        case 0:
        for (i = 0; i < 3; i++) {
            for (j = 0; j < 3; j++) {
                matriz[i][j] = rand() % 100; 
            }
        }
        printf("Matriz preenchida com numeros aleatorios\n");


        break;

    case 1:
    for( i = 0; i < 3; i++){
        printf("\n");
          for( j = 0; j < 3; j++){
              printf("Digite os valores da matriz: ");
              scanf("%f", &matriz[i][j]);
      
      
          }
      }
        break;
        case 2:
        printf("matriz:");
        for(i = 0; i < 3; i++){
         printf("\n");
          for(j = 0; j < 3; j++){
           
              printf(" %2.0f \t", matriz[i][j]);
      
      
          }
      }
        break;
        case 3:
        for(i = 0; i < 3; i++){
            printf("\n");
         for(j = 0; j < 3; j++){
            soma += matriz[i][j];
         }
       }
       printf("soma da matriz: %2.0f \t ", soma);
        break;
        case 4:
        maior = matriz[1][1];
        menor = matriz[1][1];
      for(i = 0; i < 3; i++){
        printf("\n");
          for(j = 0; j < 3; j++){
             
              if(matriz[i][j] > maior){
                maior = matriz[i][j];
              }else if(matriz[i][j] < menor){
                menor = matriz[i][j];
              }
          }
      }
      printf("maior: %2.0f \t ", maior);
      printf("menor: %2.0f \t ", menor);
           
        break;
        case 5:
        for(i = 0; i < 3; i++){
            printf("\n");
                     veri = matriz[i][i];
                  if(veri % 2 ==  0){
                    par_prin +=1;
                  }
              
                }
            printf("par dig principal: %d \t ",  par_prin);
        
        break;
        case 6:
        for(i = 0; i < 3; i++){
            printf("\n");
            
                 veri = matriz[i][2-i];
              if(veri % 2 != 0){
                imp_sec++;
              }
          
            }
            printf("impar dig secundaria: %d \t ", imp_sec);
        break;
        case 7:
        for(i = 0; i < 3; i++){
            printf("\n");
                  
                     veri = matriz[i][2-i];
                  if(veri % 2 == 0){
                    par_sec++;
                  }
              
        }
        printf("par dig secundaria: %d \t ", par_sec);
        break;
        case 8:
        for(i = 0; i < 3; i++){
            printf("\n");
             for(j = 0; j < 3; j++){
              
                veri = matriz[i][j];
                if(veri % 2 != 0){
                    soma_imp += matriz[i][j]; 
                }
         
         
             }
         }

         printf("soma dos impares: %2.0f \t ",soma_imp);
        break;
        case 9:
                return 0;
        break;

        default:
                printf("Opção inválida!\n");

    }
   
    
    printf("deseja continuar? ");
    scanf(" %c", &resp);

 } while (resp == 's' || resp == 'S');






    return 0;
}
