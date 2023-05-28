# -AyED
#include <iostream>

using namespace std;

int main (){

    double pi = 0.0;
    double denominador = 1.0; // Ingreso el denominador para la Serie Leibniz que no puede ser 0.
    int iteraciones = 0; // Cantidad de veces que se va a iterar.

    for(int i = 0; i < 250000; i++){
        denominador = 2.0 * i + 1; // Como se calcula el denominador en la Serie de Leibniz.
        double termino = 4.0 / denominador; 

        if (i % 2 == 0){
            pi += termino; //El término es positivo.
        } else {
            pi -= termino; // El término es negativo.
        }

        iteraciones++;

        //Hay que verificar si logramos calcular los 6 primeros números de forma correcta.

        double diferencia = pi - 3.141592;
        if (iteraciones >= 10000000 && pi >= 3.141591 && pi <= 3.141593) {
            break;
        }
    }
        cout << "El valor de pi calculado es: " << pi << endl;
        cout << "Numero de iteraciones: " << iteraciones << endl;
    return 0;
}
