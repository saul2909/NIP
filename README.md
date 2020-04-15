#include <iostream>
#include <conio.h>

using namespace std;
void login(int tarjeta, int nip);
void menu();
double Dinero, saldo=10000;
void retiro();
void Saldo();

int main(){//inicio int main

int nip, tarjeta, i, saldo;
i=3;

while(i!=0){//inicio while
	cout<<"Ingresa tarjeta: \n";
	cin>>tarjeta;
	cout<<endl;
	cout<<"ingresa nip: \n";
	cin>>nip;
	login(tarjeta, nip);//funcion para validar datos

i--;//incrementador
}//fin while



getch();
return 0;
}//fin int main


void login(int tarjeta, int nip){//inicio login
	if(tarjeta==123 && nip==123){//uso de la && para que se cumplan dos sentencias
	
		menu();
		
	}else{//este es un SiNo
		cout<<"Contrasenia Incorrecta: ";
	}//fin del SiNo
	
	
}//fin login


void menu(){//inicio void menu
	int opc;
	cout<<"********Operacion Bancaria Seleccione Una Opcion********\n";
	cout<<"1.-Consultar Saldo: \n";
	cout<<"2.-Retirar: \n";
	cout<<"3.-Salir \n";
	cin>>opc;
	
	switch(opc){//inicio switch
		case 1:
			Saldo();
			break;
			
		case 2:
			retiro();
			break;
		
		case 3:
			cout<<"Gracias por su visita \n";
			exit(1);
			
			break;
			
		
	}//fin switch
}//fin void menu


void retiro(){//inicio void retiro
	char respuesta;
	
	cout<<"¿Cunto es el monto que deseas retirar? ";
			cin>>Dinero;
	
			if(Dinero>saldo){//inicio if
				cout<<"La cantidad que deseas retirar exede tu saldo disponible\n";
				
				}else{
					saldo = saldo-Dinero;
					
				cout<<"Saldo restante: "<<saldo;	
				
			}//fin if
			cout<<"Deseas continuar: ";
			cin>>respuesta;
			if(respuesta=='S'||respuesta=='s'){
				menu();
			}else{
				exit(1);
			}
}//fin void retiro


void Saldo(){
	char op;
	
	cout<<"Quieres conocer tu saldo: \n";
	cin>>saldo;
	
	cout<<"Tu saldo es de $10000 pesos\n";
	
	cout<<"Deseas continuar: ";
			cin>>op;
			if(op=='S'||op=='s'){
				menu();
			}else{
				exit(1);
			}
		
}
