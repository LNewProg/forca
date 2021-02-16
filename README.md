// forca
//jogo  da forca

#include <iostream>
#include <locale.h>
#define cabeca cout<<"#####################-JOGO-DA-FORCA-#####################\n\n\n"

using namespace std;

int main (){
	setlocale(LC_ALL, "Portuguese");
	
	char palavra[33],letra[1],secreta[33]="o";
	int tam=0,vidas=6,acertos=0,i=0;
	bool acertou=false;
	
	cabeca;
	//preciso da palavra a ser descoberta
	cout<<"Informe a palavra a ser descoberta: ";
	cin>>palavra;
	system("cls");
	//preciso descobrir o tamanho da palavra
	while(palavra[i]!='\0'){
		i++;
		tam++;
	}
	//preciso do tamanho da palavra sendo aplicado à secreta
	for(i=0;i<tam;i++){
		secreta[i]='-';
	}
	//aqui inicia o jogo, preciso dizer ao programa a condição dele continuar no loop
	while(vidas>0 && acertos<tam){
		system("cls");
		cabeca;
		//preciso informar ao usuário o número de tentativas que ele ainda possui antes de perder o jogo
		cout<<"Você ainda possui "<<vidas<<" vidas.\n\n";
		
		//preciso informar a ele a palavra a ser descoberta
		cout<<"A palavra a ser desvendada é: "<<secreta;
		
		//preciso pedir a ele que tente descobrir uma letra da palavra.
		cout<<"\n\nDigite uma letra que acha estar contida na palavra: ";
		cin>>letra[0];
		
		//preciso checar, letra por letra se a opção digitada pelo usuário existe na palavra.
		for(i=0;i<tam;i++){
			if (letra[0]==palavra[i]){
				acertos++;
				acertou=true;
				secreta[i]=palavra[i];
				
			}
		}
		if(!acertou){
			vidas--;
		}
		acertou=false;
	}
	if(acertos==tam){
		system("cls");
		cabeca;
		cout<<"Parabéns, você venceu, a palavra era: "<<palavra<<"!!!";
	}else if(vidas==0){
		system("cls");
		cabeca;
		cout<<"Que pena, você perdeu, a palavra era: "<<palavra<<".";
	}
	
	
	return 0;
}
