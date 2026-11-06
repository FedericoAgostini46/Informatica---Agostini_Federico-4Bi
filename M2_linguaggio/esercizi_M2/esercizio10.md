# MODULO M2 - ESERCIZI
## Esercizio 10 - Statistiche di una sequenza letta con sentinella
Scrivere nella cella dell'esercizio 10 il programma che legge in ingresso una sequenza di voti in virgola mobile, uno per riga, e termina quando l'utente digita 0 . Il programma calcola e stampa il numero di voti inseriti, il massimo, il minimo, la media con due decimali e quanti voti sono risultati sufficienti, cioè maggiori o uguali a 6. I voti fuori dall'intervallo da 1 a 10 vanno segnalati e ignorati senza interrompere la lettura. Se non viene inserito alcun voto valido il programma lo dichiara e non calcola le statistiche.

Massimo e minimo vanno inizializzati con il primo valore valido letto, non con una costante scelta a priori: è la stessa scelta corretta già adottata in Java.

`````java
import java.util.Scanner;

public class Esercizio10 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int conteggio = 0;
        double somma = 0;
        double massimo = 0;
        double minimo = 0;
        int sufficienze = 0;

        while (true) {
            System.out.print("Voto (0 per finire): ");
            double voto = sc.nextDouble();

            if (voto == 0) {
                break;
            }
            if (voto < 1 || voto > 10) {
                System.out.println("valore " + voto + " fuori intervallo: ignorato");
                continue;
            }

            if (conteggio == 0) {
                massimo = voto;
                minimo = voto;
            }
            if (voto > massimo) {
                massimo = voto;
            }
            if (voto < minimo) {
                minimo = voto;
            }

            conteggio++;
            somma = somma + voto;
            if (voto >= 6) {
                sufficienze++;
            }
        }

        if (conteggio == 0) {
            System.out.println("Nessun voto valido inserito");
        } else {
            System.out.println("voti validi: " + conteggio);
            System.out.printf("massimo: %.2f%n", massimo);
            System.out.printf("minimo: %.2f%n", minimo);
            System.out.printf("media: %.2f%n", somma / conteggio);
            System.out.println("sufficienze: " + sufficienze);
        }
    }
}
`````