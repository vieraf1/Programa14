# Programa 14

Linguagem Utilizada: C++.

Programa faz leitura dos valores dos três lados do triângulo, identifica que tipo de triângulo é e calcula a base, altura e a área total utilizando o teorema de Heron.

Programa Desenvolvido no DEV C++ IDE.

Código:

#include "iostream"
#include "math.h"
#include "string"
using namespace std;

float LA, LB, LC;
string STA;
float SP = 0, AR = 0, BA = 0, AL = 0, A = 0;

int main() {
	cout << "\nInformer o valor do primeiro lado da figura: " << endl;
	cin >> LA;
	cout << "\nInformer o valor do segundo lado da figura: " << endl;
	cin >> LB;
	cout << "\nInformer o valor do terceiro lado da figura: " << endl;
	cin >> LC;
	
	if ((LA > (LB + LC)) || (LB > (LA + LC)) || (LC > (LA + LB))) {
		STA = "Figura";
	}
	else if((LA == LB) && (LB == LC)) {
		STA = "Equilatero";
	}
	else if( ((LA == LB) && (LB != LC)) || ((LA == LC) && (LA != LB)) || ((LB == LC) && (LC != LA)) ) {
		STA = "Isoceles";
	}
	else if( (LA != LB) && (LB != LC) && (LA != LC)) {
		STA = "Escaleno";
	}
	
	if (STA != "Figura") {
		if (STA == "Equilatero") {
			BA = LA;
			SP = (LA + LB + LC)/2;
			A = SP * (SP - LA) * (SP - LB) * (SP - LC);
			AR = sqrt(A);
			AL = AR * 2 / BA;
		}
		if (STA == "Isoceles") {
			
			if (LA == LB){
			   	BA = LC;
			}
			else if (LB == LC) {
			   	BA = LA;
			}
			else if (LA == LC) {
			   	BA = LB;
			}		
			SP = (LA + LB + LC)/2;
			A = SP * (SP - LA) * (SP - LB) * (SP - LC);
			AR = sqrt(A);
			AL = AR * 2 / BA;
		}
		if (STA == "Escaleno") {
			
			if ((LC > LA) && (LC > LB)) {
			   	BA = LC;
			}
			else if ((LA > LB) && (LA > LC)) {
			   	BA = LA;
			}
			else if ((LB > LA) && (LB > LC)) {
			   	BA = LB;
			}		
			SP = (LA + LB + LC)/2;
			A = SP * (SP - LA) * (SP - LB) * (SP - LC);
			AR = sqrt(A);
			AL = AR * 2 / BA;
		}
	}
	
	cout << "\nSP: " << SP << " | AR: " << AR << " | BA: " << BA << " | AL: " << AL << " | STA: " << STA;

return 0;}
