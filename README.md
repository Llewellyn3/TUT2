# TUT2

#include <iostream>
using namespace std;

typedef struct
{
	int numer;
	int denom;
} Fraction;

int inline gcd(int x,int y)
{
	int temp;                                

    while (y != 0)
    {
        temp = y;
        y = x % y;
        x = temp;
    }
    return x;
}


Fraction Add(Fraction f1,Fraction f2)
{
	Fraction myfract;                                       

    int n = (f1.numer * f2.denom) + (f2.numer * f1.denom);  
    int d = (f1.denom * f2.denom);                          

	myfract.numer=n/gcd(n,d);                               
	myfract.denom=d/gcd(n,d);                               

	return myfract;                                         
}

Fraction Subtract(Fraction f1,Fraction f2)
{
	Fraction myfract;

    int n = (f1.numer * f2.denom) - (f2.numer * f1.denom);
    int d = (f1.denom * f2.denom);

	myfract.numer=n/gcd(n,d);
	myfract.denom=d/gcd(n,d);

	return myfract;
}

Fraction Multiply(Fraction f1,Fraction f2)
{
	Fraction myfract;

	int n = ( f1.numer*f2.numer);
	int d = ( f1.denom*f2.denom);

	myfract.numer=n/gcd(n,d);
	myfract.denom=d/gcd(n,d);

	return myfract;
}

Fraction Divide( Fraction f1,Fraction f2)
{
	Fraction myfract;

	int n = f1.numer*f2.denom;
	int d = f1.denom*f2.numer;

	myfract.numer=n/gcd(n,d);
	myfract.denom=d/gcd(n,d);

	return myfract;
}


void show(Fraction jj)
{
	
	{	
	if (jj.denom==1)              
		cout<<jj.numer<<endl;      

	       
			else 
				cout<<jj.numer<<"/"<<jj.denom<<endl;  
    }

}

int main()
{

Fraction fract1, fract2, fract3,fract4,fract5,fract6; 

cout << "Input the first numerator: ";    
cin >> fract1.numer;    
cout << "Input the first denominator: ";    
cin >> fract1.denom;
   
cout << "Input the second numerator: ";  
cin >> fract2.numer;    
cout << "Input the second denominator: ";   
cin >> fract2.denom;

fract3 = Add(fract1, fract2);
fract4= Subtract(fract1,fract2);
fract5= Multiply(fract1,fract2);
fract6= Divide(fract1,fract2);

cout<<"The addition of the fractions are: ";
show(fract3);
cout<<"The subtraction of the fractions are: ";
show(fract4);
cout<<"The multiplication of the fractions are: ";
show(fract5);
cout<<"The division of the fractions are: ";
show(fract6);
}

