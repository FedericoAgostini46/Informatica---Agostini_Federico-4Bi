# MODULO M1 - ESERCIZI
## Esercizio 7 - Analisi delle cifre di un numero
Scrivere nella cella dell'esercizio 7 il programma che legge in ingresso un intero non negativo e ne calcola, con un ciclo while che usa soltanto il resto e la divisione intera per dieci, la somma delle cifre, il numero di cifre e la cifra maggiore. Il numero zero va gestito correttamente: ha una cifra, la somma è zero e la cifra maggiore è zero. Non è ammesso trasformare il numero in stringa.

`````java
import java.util.Scanner;

public class Esercizio7 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Numero intero non negativo: ");
        int numero = sc.nextInt();

        int cifre = 0;
        int somma = 0;
        int maggiore = 0;

        if (numero == 0) {
            cifre = 1;
        } else {
            while (numero > 0) {
                int cifra = numero % 10;
                cifre++;
                somma = somma + cifra;
                if (cifra > maggiore) {
                    maggiore = cifra;
                }
                numero = numero / 10;
            }
        }

        System.out.println("cifre: " + cifre);
        System.out.println("somma delle cifre: " + somma);
        System.out.println("cifra maggiore: " + maggiore);
    }
}
`````