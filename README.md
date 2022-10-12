# Proyecto-II
// Kevin Aguilar
// Carné; 7690-21-12389
#include<iostream>
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
#include<fstream>

using namespace std;

void crear();

int main(){
	
	crear();
	int opcion = 0;
	char nombre[20], codigo[10], proveedor[20], estado[1], mod[20];
	double precio, existencia, descuento;
	
	cout << "////////////////////////////////////////////////////////////////////////" << endl;
	cout << "//_________________Plataforma oficial Tiendas Llamasa_________________//" << endl;
	cout << "////////////////////////////////////////////////////////////////////////" << endl;
	do{
		cout << "\n\tMenu de Opciones" << endl;
		cout << "1.Agregar producto" << endl;
		cout << "2.Buscar producto" << endl;
		cout << "3.Modificar los datos de un producto" << endl;
		cout << "4.Salir" << endl;
		cout << "\nElija la opcion segun su necesidad: ";
		cin >> opcion;
		switch(opcion){
			case 1:
				cout << "\nIngrese el nombre a asignar: ";
				cin >> nombre;
				system("pause");
				cout << "Ingrese un Codigo: ";
				cin >> codigo;
				system("pause");
				cout << "Asigne un Precio: ";
				cin >> precio;
				system("pause");
				cout << "Su Proveedor es: ";
				cin >> proveedor;
				system("pause");
				cout << "En Existencias hay: ";
				cin >> existencia, " unidades";
				system("pause");
				cout << "Estado: ";
				cin >> estado;
				system("pause");
				cout << "Descuento: ";
				cin >> descuento;
				system("pause");
				system("cls");
				break;
			case 2: 
				cout << "Ingresa el nombre o el codigo: ";
				cin >> nombre, codigo;
				if(nombre == codigo)
					cout << "Este es lo que encontramos: " << nombre << codigo << endl;
				else
					cout << "Necesitamos mas datos o ingresaste un dato erroneo. Intenta de nuevo" << endl;
				system("pause");
				system("cls");
				break;
			case 3:
				cout << "Producto a modificar: ";
				cin >> mod;
				if(mod == codigo)
					cout << "El dato ingresado es igual al codigo, es decir, no se puede editar!" << endl;
				else
					cout << "El dato ha sido actualizado con exito!" << endl;
				system("pause");
				system("cls");
				break;
			case 4:
				break;
			default:
				cout << "Opcion ingresada no existe en el sistema!" << endl;
				system("pause");
				system("cls");
				break;
		}
	}while(opcion != 4);
	return 0;
}

void crear(){
	ofstream archivo;
	string nombreArchivo, opcion;
	getline(cin, nombreArchivo);
	
	archivo.open("Inventario.txt.c_str()", ios::out);
	
	if(archivo.fail()){	
		cout << "No se pudo agregar el producto";
		exit(1);
	}
	
	archivo << opcion;
	
	archivo.close();
}
