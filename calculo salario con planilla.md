# Algoritmos-I
#include "stdafx.h"
#include "conio.h"
#include <iostream>
#define tam 30
#define iva 0.13
#define afp 0.121
#define salariominimo 1650
using namespace std;
void cargar_vector(float v[], int n);
void mostrar_planilla(float v1[], float v2[], int n);
void calculo_salario(float v1[], float v2[], int n);
float calculo_promedio(float v[], int n);
void main()
{
float salariobruto[tam], salarioneto[tam], prom;
int n;
do{
cout << "ingrese el nro de empleados: ";
cin >> n;
} while ((n <= 0) || (n>tam));
cargar_vector(salariobruto, n);
calculo_salario(salariobruto, salarioneto, n);
prom = calculo_promedio(salarioneto, n);
mostrar_planilla(salariobruto, salarioneto, n);
cout << "el promedio es: " << prom;
_getch();
}
void cargar_vector(float v[], int n)
{
for (int i = 1; i <= n; i++)
{
cout << "ingrese salario bruto del empleado " << i << " : ";
cin >> v[i];
}
}
void mostrar_planilla(float v1[], float v2[], int n)
{
cout << "\tplanilla de sueldos" << endl;
cout << " n " << " salario bruto " << " salario neto " << endl;
cout << "-------------------------------------------------" << endl;
for (int i = 1; i <= n; i++)
{
cout << i << " " << v1[i] << " " << v2[i] << endl;
}
cout << "--------------------------------------------------" << endl;
}
void calculo_salario(float v1[], float v2[], int n)
{
float p = 0;
for (int i = 1; i <= n; i++)
{
if (v1[i] > (salariominimo * 2))
v2[i] = v1[i] - (v1[i] * afp*iva);
else
v2[i] = v1[i];
}
}
float calculo_promedio(float v[], int n)
{
float p = 0;
for (int i = 1; i <= n; i++)
{
p = v[i] + p;
}
p = p / n;
return p;
}
