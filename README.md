rograma {
  funcao inicio() {
    
    cadeia mapa[5][5]
    inteiro linha=0, coluna=0
    inteiro ultimaLinha=0, ultimaColuna=0
    caracter direcao

  //Preenchendo a mapa de jogo com "_"
    para (inteiro i=0;i<5;i++){
      para (inteiro j=0;j<5;j++){
        mapa[i][j] = "_"
      }
    }
    //Criando posicoes para os obstaculos
    mapa[0][4] = "*"
    mapa[2][2] = "*"
    mapa[4][4] = "*"
    mapa[4][1] = "*"
    mapa[4][3] = "*"
    mapa[3][4] = "*"
    mapa[0][4] = "■"
    mapa[3][3] = "■"
    mapa[1][2] = "■"
    
    //Definindo a posicao inicial da personagem
    mapa[0][0]= ":O"

    //Mostrando a versão inicial do mapa
    para (inteiro i=0;i<5;i++){
      para (inteiro j=0;j<5;j++){
        escreva(mapa[i][j], " ")
      }
    escreva("\n")
    }    

    //Lendo um comando para movimentar a personagem
    enquanto(verdadeiro){
      escreva("Digite o comando: ")
      leia(direcao)
      limpa()
      //Verificando qual tecla foi pressionada
      escolha(direcao){
        caso "s": 
          linha++
          pare
        caso "a": 
          coluna--
          pare
        caso "w": 
          linha--
          pare
        caso "d": 
          coluna++
          pare
        caso contrario: 
          pare
      }
      //Resetando qual foi a última posição que a personagem esteve
      mapa[ultimaLinha][ultimaColuna]="_"
      
      //Definindo a nova posição da personagem no mapa
      mapa[linha][coluna]=":O"
      
      //Exibindo o mapa de jogo atualizado
      para (inteiro i=0;i<5;i++){
       para (inteiro j=0;j<5;j++){
          escreva(mapa[i][j], " ")
       }
       escreva("\n")
      }
      //Memorizando a última posição da personagem
      ultimaLinha=linha
      ultimaColuna=coluna
      
      
     
      se (mapa[0][4]!=""e mapa[2][2]!="" e mapa[4][4]!="" e mapa[4][1]!="" e mapa[4][3]!="" e mapa[3][4]!="" ){
        escreva ("voce comeu todas as frutas!!!")pare
        
       
      }
      se(mapa[0][4]!="■" ou mapa [3][3]!="■" ou mapa[1][2]!="■"){escreva ("game over")pare
    }
   

    }
    
  }
}
