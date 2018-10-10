/*realizar un programa que simule las actividades de un cajero automatico
1.- leer un codigo de seguridad
2.-mostrar un menu de 4 opciones
5.-utilizando una variable de acarreo 
podra retirar o comprar  tiempo aire a su cuenta

*/	
	
	char opcion;
	char operacion();
	int saldo_inicial =1000,numero,monto;
	float extra,saldo = 0,retiro,tiempo_a;
	char codigo;
	
#include<iostream>
#include<string>
#define USER "java"
#define PASS "c++"
using namespace std;
int main()
{
	string usuario, password;
	
	cout<<"\n\t\t\tLOGIN DE USUARIO"<<endl;
	cout<<"\n\t\t\t----------------"<<endl;
	cout<<"\n\t\t\tusuario:";
	getline(cin, usuario);
	cout<<"\n\t\t\tpassword:";
	getline(cin, password);
	
	if(usuario == USER && password == PASS)
	{
		cout<<"\n\t\t\tbienvenido al sistema!!"<<endl;
	}
	else
	{
		cout<<"\n\t\t\tel usuario y/o pasword es incorrecto"<<endl;
	}
	
	cout<<"\n\t\t\tselecciona la opcion 1 para realizar las siguientes operaciones:\n"; //selecciona para entrar al menu
	cin>>opcion;
	
	switch(opcion)
	{
		case'1':operacion();  //primera opcion
		break;
		default:cout<<"\n\t\t\topcion invalida:"; //si el usuario digita malla opcion aparece como defautl
		
	}
	system("pause");
	return 0;
	
}
char operacion()  //aqui se realiza las operaciones
{
	int opcion;
	cout<<"\n\t\t\tselecciona la operacion :\n";
	cout<<"\n\t\t\t1. ingresar dinero en su cuenta :\n";
	cout<<"\n\t\t\t2. retirar dinero de su cuenta :\n";
	cout<<"\n\t\t\t3. realizar una recarga :\n";
	cin>>opcion;

	switch(opcion)
	{
		
			
			
		case 1:  //ingresa dinero el usuario va a meter dinero al cajero
			cout<<"\n\t\t\tdigite la canidad de dinero a ingresar:"<<endl;
			cin>>extra;
			saldo =saldo_inicial + extra;
			cout<<"\n\t\t\tdinero en cuenta es :"<<saldo<<endl;
			break;
			
			
		case 2://retire dinero el usuario retira sudinero de la cantidad que el quiera
			cout<<"\n\t\t\tdigite la cantidad de  dinero a retirar :"<<endl;
			cin>>retiro;
			if(retiro > saldo_inicial)
			{
				cout<<"\n\t\t\tsaldo insuficiente:"<<endl;
			}
			else
			{
				saldo = saldo_inicial - retiro;
				cout<<"\n\t\t\tdinero en cuenta :\n"<<saldo<<endl;
			}
			break;
			
			
		case 3://realiza una recarga
			cout<<"\n\t\t\tingrese el numero de tu celular de 10 digitos:";
			cin>>numero;
			cout<<"\n\t\t\tselecciona el monto :";
			cin>>monto;
			
			if((numero>10)&&(numero<1))// se realiza la cuenta del monto
			
			{
				cout<<"\n\t\t\topcion invalida:";
			}
			else
			{
				numero = monto - saldo_inicial;
			
			    cout<<"\n\t\t\tsu cuenta es :"<<numero<<endl;
			}
			
			break;
			case 4:
				break;
	}
	cin.get();
	system ("pause");
	return 0;
}
