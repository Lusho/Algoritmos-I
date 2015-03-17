# Algoritmos-I
// palindromo.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"
#include "conio.h"
#include <iostream>
#include <string>
using namespace std;

bool palindromo (string p);

void main()
{
	string p;
	bool a=false;
	cout<<"ingrese frase a revisar"<<endl;
	
	getline (cin,p);
	a=palindromo(p);
	if (a==true)
		
		cout<<"\t\tes palindromo";
	else
		cout<<"no es palindromo";
	_getch();
	
}

bool palindromo (string p)
{
	bool a=true;
	int tam= p.length();
	int i;

	 for (i=0;i<(tam/2);i++)
		 {if (p[i]!= p[tam-1-i])
			{a=false;
			return a;
			}
	     }
return a;
}


