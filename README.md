# find_result_C-

```C++
#include <iostream>
#include <cmath>

using namespace std;

void function(unsigned long long int numero){
    
    unsigned long long int tmp = numero;
    unsigned long long int digito = 0;
    unsigned long long int acum = 0;
    unsigned long long int potencia = 0;
    
    unsigned long long int numero2;
    
    if( tmp % 10 != 0 ){
        while (tmp > 0) {
            digito = tmp % 10;
            tmp /= 10;
            
            acum += digito;
            potencia++;
        }
        
        tmp = numero;
        
        if(acum % 9 == 0){
          
            // Invertir
            digito = tmp % 10;
            tmp /= 10;
            
            numero2 = tmp + digito * std::pow(10,potencia-1);
            
            if(double(numero2) / double(numero) == 9.0){
               cout << numero << " ->" << numero2 << "|" << (numero2 / numero) << endl; 
            }
        }
    }
}

int main()
{
    
    for (unsigned long long int i = 0; i < 100000000000; i++) {
        function(i);
        if(i % (100000000000/8) == 0){
            cout << "count -> " << i << endl;
        }
    }

    return 0;
}
```
