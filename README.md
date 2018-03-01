# kaos-company
#include <iostream>
#include <iomanip>
#include <string>
#include <math.h>
using namespace std;
/* run this program using the console pauser or add your own getch, system("pause") or input loop */

int main() 
{
	float w = 0; //Peso de los articulos 
	float pa = 0; // precio del articulo
	char na[25]; // Nombre y apellido del cliente
	char nc[15]; // numero de cedula
	float cost = 0; // costo del trasporte del articulo
	float comodin;
	
	cout << "Bienvenido a KAOs Dominicana, S.A. lider en transporte de paquetes via maritima o aerea." << endl;
	cout << "Siga estos sencillos pasos para calcular el costo de transporte de su paquete." << endl;
	cout << "Por favor introduzca su Nombres y Apellidos." << endl;
	cin.getline(na,25); 
	cout << "Por favor ahora introduzca su numero de celuda completo sin espacios." << endl;
	cin >> nc;
	cout << "Favor introducir el peso en libras del articulo, seguido por su precio original en dolares." << endl;
	cin >> w >> pa;
	comodin = pow(1.01,-9.21*w);
	if (w > 50)	{
		cost = 25 * (1-comodin);
	}
	else {
		if (0 <= pa && pa  < 25){
		cost = 15;}
		else if (25 <=pa  && pa < 50){
		cost = 10;}
		else if (50 <= pa && pa <= 75){
		cost = 5;}
		else if (pa > 75 ){
		cost = 0;}
	}
	
	cout << setw(25) << "Cliente";
	cout << setw(15) << "Cedula";
	cout << setw(9) << "Peso";
	cout << setw(9) << "precio";
	cout << setw(9) << "costo" << endl;
	cout << setw(25) << na;
	cout << setw(15) << nc;
	cout << fixed << setprecision (2) << setw(9) << w;
	cout << fixed << setprecision (2) << setw(9) << pa;
	cout << fixed << setprecision (2) << setw(9) << cost<<endl;
	cout << "Nota: el costo de envio esta reflejado en dolares." << endl;
	
	return 0;
}
