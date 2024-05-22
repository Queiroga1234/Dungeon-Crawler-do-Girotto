scanf("%d", &menu);
system("cls");
if(menu==1){
	printf("iniciando jogo\n");
	fase = 1;
	vidas = 3;
	Sleep(2000);
	
while (fase==1) {
    system("cls");
	printf("Vidas:%d\n", vidas);
    for (i = 0; i < 10; i++) {
        for (j = 0; j < 10; j++) {
            if (i == posY && j == posX) {
                printf("&");
            } else {
                printf("%c", mapa[i][j]);
            }
        }
        printf("\n");
    }
    if(posY==8&&posX==8){
		chave1++;
	}
	if(vidas <= 0){
            	printf("Game over, tente novamente");
            }
            printf("%d\n", fase);
            printf("%d\n", chave1);
    teclaPressionada = lerTecla();
    switch (teclaPressionada) {
        case 'w':
        	if (mapa[posY - 1][posX] == '#') {
                vidas--;
        	}
            else if (mapa[posY - 1][posX] != '*') {
                posY--;
            }
            break;
        case 'a':
        	if (mapa[posY][posX - 1] == '#') {
                vidas--;
        	}
            else if (mapa[posY][posX - 1] != '*') {
                posX--;
            }
            break;
        case 's':
        	if (mapa[posY + 1][posX] == '#') {
                vidas--;
            }
            else if (mapa[posY + 1][posX] != '*') {
                posY++;
            }
            break;
        case 'd':
        	if (mapa[posY][posX + 1] == '#') {
                vidas--;
            }
            else if (mapa[posY][posX + 1] != '*') {
                posX++;
            }
            break;
        case 'i':
        	if((posY==2&&posX==1&&chave1!=0)||(posY==1&&posX==2&&chave1!=0)){
        		mapa[1][1]='=';
        	}
        	break;
        case 'q':
            printf("Saindo do jogo...\n");
            return 0;
        default:
            printf("Tecla invalida!\n");
            Sleep(1000);
            break;
    }
    if (mapa[posY][posX] == '='){
        fase++;
    }
    
    }
    int posY2 = 1;
	int posX2 = 1;
	int chave2 = 0;
	int moveA2;
	int inimigoAY2 = 12;
	int inimigoAX2 = 8;
	char mapa2[20][21] = {
	"********************",
	"*D                 *",
	"*        #        #*",
	"*                # *",
	"*     ###       #  *",
	"*                  *",
	"*            #     *",
	"*                  *",
	"*        #         *",
	"*         ###      *",
	"*   O              *",
	"*          #       *",
	"*                  *",
	"*      #   # # #   *",
	"*                # *",
	"*        #      #@ *",
	"*                # *",
	"*        #         *",
	"*                  *",
	"********************",
	};
	
    while(fase==2){
    	
    	system("cls");
    	printf("Vidas:%d\n", vidas);
    for (i = 0; i < 20; i++) {
        for (j = 0; j < 21; j++) {
            if (i == posY2 && j == posX2) {
                printf("&");
            }
			else if(i == inimigoAY2 && j == inimigoAX2){
            	printf("X");
            } else {
                printf("%c", mapa2[i][j]);
            }
        }
        printf("\n");
    }
    
    if(posY2==15&&posX2==17){
		chave2++;
	}
	if(vidas <= 0){
		system("cls");
        printf("Game over, tente novamente");
        menu = 0;
        fase = 0;
            }
            printf("%d\n", fase);
            printf("%d\n", chave2);
    teclaPressionada = lerTecla();
    switch (teclaPressionada) {
        case 'w':
        	if (mapa2[posY2 - 1][posX2] == '#') {
                vidas--;
        	}
        	else if (mapa2[posY2 - 1][posX2] == '='){
            	fase++;
            }
            else if (mapa2[posY2 - 1][posX2] != '*') {
                posY2--;
            }
            break;
        case 'a':
        	if (mapa2[posY2][posX2 - 1] == '#') {
                vidas--;
        	}
        	else if(mapa2[posY2][posX2 - 1] == '='){
            	fase++;
            }
            else if (mapa2[posY2][posX2 - 1] != '*') {
                posX2--;
            }
            break;
        case 's':
        	if (mapa2[posY2 + 1][posX2] == '#') {
                vidas--;
            }
            else if (mapa2[posY2 + 1][posX2] != '*') {
                posY2++;
            }
            break;
        case 'd':
        	if (mapa2[posY2][posX2 + 1] == '#') {
                vidas--;
            }
            else if (mapa2[posY2][posX2 + 1] != '*') {
                posX2++;
            }
            break;
        case 'i':
        	if((posY2==11&&posX2==4)||(posY2==10&&posX2==5)||(posY2==5&&posX2==12)||(posY2==11&&posX2==6)){
        		printf("Casseb Supremacy");
        		Sleep(1000);
        	}
        	else if((posY2==2&&posX2==1&&chave2!=0)||(posY2==1&&posX2==2&chave2!=0)){
        		mapa2[1][1]='=';
        	}
        	break;
        case 'q':
            printf("Saindo do jogo...\n");
            return 0;
        default:
            printf("Tecla invalida!\n");
            Sleep(1000);
            break;
    }
    if(posY2 == inimigoAY2 && posX2 == inimigoAX2){
    	system("cls");
        printf("Game over, tente novamente");
        menu = 0;
        fase = 0;
    }
    
    moveA2= rand()%4;
    if (moveA2==1){
    	if(mapa2[inimigoAY2 + 1][inimigoAX2] != '*'&& mapa2[inimigoAY2 + 1][inimigoAX2] != '#'){
    		inimigoAY2++;
    	}
    }
    else if (moveA2==2){
    	if(mapa2[inimigoAY2 - 1][inimigoAX2] != '*'&& mapa2[inimigoAY2 - 1][inimigoAX2] != '#'){
    		inimigoAY2--;
    	}
    }
    else if (moveA2==3){
    	if(mapa2[inimigoAY2][inimigoAX2 + 1] != '*'&& mapa2[inimigoAY2][inimigoAX2 + 1] != '#'){
    		inimigoAX2++;
    	}
    }
    else{
    	if (moveA2==1){
    	if(mapa2[inimigoAY2][inimigoAX2 - 1] != '*'&& mapa2[inimigoAY2][inimigoAX2 - 1] != '#'){
    		inimigoAX2--;
    	}
    }
    }
    
}
    srand(time(NULL));
	int posY3 = 1;
	int posX3 = 1;
	int inimigoSX= 14;
	int inimigoSY= 1;
	int inimigoAX=29;
	int inimigoAY=38;
	int moveS;
	int moveA;
	int chave3 = 0;
	char mapa3[40][41] = {
	"****************************************",
	"*D                                 #  >*",
	"*                                  #   *",
	"*                                  #   *",
	"*                                  #   *",
	"*                                  #   *",
	"*                                  #   *",
	"*                               ####   *",
	"*                                      *",
	"*  ###############                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*                ************          *",
	"*                *>                    *",
	"*                *                     *",
	"*                *                     *",
	"*                *                     *",
	"*       **********                     *",
	"*                         #            *",
	"*                         #            *",
	"*                         #            *",
	"*            O            #            *",
	"*                         #            *",
	"*                         #            *",
	"*                         #            *",
	"*     #####################            *",
	"*           #                          *",
	"*           #                          *",
	"*           #                        ##*",
	"*           #                        #@*",
	"*                                      *",
	"****************************************",
	};
	
    while(fase==3){
    	
        system("cls");
    	printf("Vidas:%d\n", vidas);
    	printf("Coordenada Y:%d\n", posY3);
    	printf("Coordenada X:%d\n", posX3);
    for (i = 0; i < 40; i++) {
        for (j = 0; j < 41; j++) {
            if (i == posY3 && j == posX3) {
                printf("&");
            }
            else if(i == inimigoAY && j == inimigoAX){
            	printf("X");
            }
            else if(i == inimigoSY && j == inimigoSX){
            	printf("V");
            }
			 else {
                printf("%c", mapa3[i][j]);
            }
        }
        printf("\n");
    }
    
    
    if(posY3==37&&posX3==38){
		chave3++;
	}
	if(vidas <= 0){
		system("cls");
        printf("Game over, tente novamente");
        menu = 0;
        fase = 0;
            }
            printf("%d\n", fase);
            printf("%d\n", chave3);
    teclaPressionada = lerTecla();
    switch (teclaPressionada) {
        case 'w':
        	if (mapa3[posY3 - 1][posX3] == '#') {
                vidas--;
        	}
        	else if (mapa3[posY3 - 1][posX3] == '='){
            	fase++;
            }
            else if (mapa3[posY3 - 1][posX3] != '*') {
                posY3--;
            }
            break;
        case 'a':
        	if (mapa3[posY3][posX3 - 1] == '#') {
                vidas--;
        	}
        	else if(mapa3[posY3][posX3 - 1] == '='){
            	fase++;
            }
            else if (mapa3[posY3][posX3 - 1] != '*') {
                posX3--;
            }
            break;
        case 's':
        	if (mapa3[posY3 + 1][posX3] == '#') {
                vidas--;
            }
            else if (mapa3[posY3 + 1][posX3] != '*') {
                posY3++;
            }
            break;
        case 'd':
        	if (mapa3[posY3][posX3 + 1] == '#') {
                vidas--;
            }
            else if (mapa3[posY3][posX3 + 1] != '*') {
                posX3++;
            }
            break;
        case 'i':
        	if((posY3==29&&posX3==12)||(posY3==30&&posX3==13)||(posY3==29&&posX3==14)||(posY3==28&&posX3==13)){
        		printf("Casseb Supremacy");
        		Sleep(1000);
        	}
        	else if((posY3==2&&posX3==1&&chave3!=0)||(posY3==1&&posX3==2&chave3!=0)){
        		mapa3[1][1]='=';
        	}
        	else if((posY3==2&&posX3==38)||(posY3==1&&posX3==37)){
        		posY3 = 21;
        		posX3 = 18;
        	}
        	else if((posY3==21&&posX3==19)||(posY3==22&&posX3==18)){
        		posY3 = 1;
        		posX3 = 38;
        	}
        	break;
        case 'q':
            printf("Saindo do jogo...\n");
            return 0;
        default:
            printf("Tecla invalida!\n");
            Sleep(1000);
            break;
    }
    if(posY3 == inimigoSY && posX3 == inimigoSX){
    	system("cls");
        printf("Game over, tente novamente");
        menu = 0;
        fase = 0;
    }
    if(posY3 == inimigoAY && posX3 == inimigoAX){
    	system("cls");
        printf("Game over, tente novamente");
        menu = 0;
        fase = 0;
    }
    
    moveA= rand()%4;
    if (moveA==1){
    	if(mapa3[inimigoAY + 1][inimigoAX] != '*'&& mapa3[inimigoAY + 1][inimigoAX] != '#'){
    		inimigoAY++;
    	}
    }
    else if (moveA==2){
    	if(mapa3[inimigoAY - 1][inimigoAX] != '*'&& mapa3[inimigoAY - 1][inimigoAX] != '#'){
    		inimigoAY--;
    	}
    }
    else if (moveA==3){
    	if(mapa3[inimigoAY][inimigoAX + 1] != '*'&& mapa3[inimigoAY][inimigoAX + 1] != '#'){
    		inimigoAX++;
    	}
    }
    else{
    	if (moveA==1){
    	if(mapa3[inimigoAY][inimigoAX - 1] != '*'&& mapa3[inimigoAY][inimigoAX - 1] != '#'){
    		inimigoAX--;
    	}
    }
    }
    
    moveS = rand()%2;
	if(moveS==0){
		if(posX3<inimigoSX){
			if(mapa3[inimigoSY][inimigoSX - 1] != '*'&& mapa3[inimigoSY][inimigoSX - 1] != '#'){
    			inimigoSX--;
    	}
    	}
		else{
			if(mapa3[inimigoSY][inimigoSX + 1] != '*'&& mapa3[inimigoSY][inimigoSX + 1] != '#'){
    			inimigoSX++;
		}
		}
	}else{
		if(posY3<inimigoSY){
			if(mapa3[inimigoSY - 1][inimigoSX] != '*'&& mapa3[inimigoSY - 1][inimigoSX] != '#'){
    			inimigoSY--;
		}
		}else{
				if(mapa3[inimigoSY + 1][inimigoSX] != '*'&& mapa3[inimigoSY + 1][inimigoSX] != '#'){
    			inimigoSY++;
		}
		}
	}

}
if(fase==4){
	system("cls");
	printf("Parabens, voce terminou o jogo\n Credito do jogo para: Iasmin Forte de Carvalho e Pedro Henrique Queiroga\n Jogue novamente\n");
}

}else if(menu==2){
	printf("preparando tutorial\n");
	Sleep(2000);
	printf("Nesse dungeon crawler, o seu personagem(&) vai atras de chaves(@) para fugir dessa masmorra\nOs controles sao:\n W: mover para cima\n A: mover para esquerda\n S: mover para baixo\n D: mover para direita\n I: interacao com os elementos das fases\n Q: sair do jogo\n");
}else if(menu==3){
	printf("PREPARANDO MENSAGEM DE DESPEDIDA\n");
	Sleep(2000);
	printf("Obrigado por jogar! Eh hora de fechar as cortinas dessa aventura digital. Ate a proxima jornada!");
}else{
	printf("DIGITE UMA OPCAO VALIDA");
}

}
return 0;
