# MODULO M1 - ESERCIZI
## Esercizio 1 - Durata di una sessione di laboratorio
Scrivere nella cella dell'esercizio 1 il programma che legge in   ingresso la durata di una sessione di laboratorio espressa in secondi e la stampa nel formato ore, minuti e secondi, usando soltanto la divisione intera e il resto. Il programma stampa anche la stessa durata espressa in ore decimali con due cifre dopo la virgola, e segnala con un messaggio il caso in cui la durata superi le quattro ore.

`````java
import java.util.Scanner;

public class Esercizio1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Durata in secondi: ");
        int secondi = sc.nextInt();

        int ore = secondi / 3600;
        int minuti = (secondi % 3600) / 60;
        int sec = secondi % 60;

        System.out.printf("%02d:%02d:%02d%n", ore, minuti, sec);
        System.out.printf("in ore decimali: %.2f%n", secondi / 3600.0);

        if (secondi > 4 * 3600) {
            System.out.println("attenzione: la sessione supera le quattro ore");
        }
    }
}
`````