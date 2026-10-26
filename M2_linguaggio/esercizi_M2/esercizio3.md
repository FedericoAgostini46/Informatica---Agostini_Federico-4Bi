# MODULO M2 - ESERCIZI
## Esercizio 3 - Tavola di conversione incolonnata
Scrivere nella cella dell'esercizio 3 il programma che legge in ingresso un valore iniziale, un valore finale e un passo, tutti interi, e stampa la tavola di conversione da chilometri a miglia e a
metri per tutti i valori dell'intervallo, estremi compresi. Un chilometro corrisponde a 0,621371 miglia. La tabella ha un'intestazione e una riga di trattini, le colonne sono allineate a destra e i
valori in miglia hanno tre decimali. Se il passo non è positivo il programma stampa un messaggio e non produce la tabella.

`````java
import java.util.Scanner;

public class Esercizio3 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Valore iniziale: ");
        int inizio = sc.nextInt();
        System.out.print("Valore finale: ");
        int fine = sc.nextInt();
        System.out.print("Passo: ");
        int passo = sc.nextInt();

        if (passo <= 0) {
            System.out.println("Il passo deve essere positivo");
        } else {
            System.out.printf("%12s%12s%12s%n", "km", "miglia", "metri");
            System.out.println("------------------------------------");
            for (int km = inizio; km <= fine; km = km + passo) {
                double miglia = km * 0.621371;
                int metri = km * 1000;
                System.out.printf("%12d%12.3f%12d%n", km, miglia, metri);
            }
        }
    }
}
`````