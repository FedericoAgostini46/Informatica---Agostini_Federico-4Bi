# MODULO M2 - ESERCIZI
## Esercizio 12 - Occorrenze di una sottostringa senza il metodo count
Scrivere nella cella dell'esercizio 12 il programma che legge in ingresso un testo e una sottostringa da cercare, e conta quante volte la sottostringa compare nel testo usando find ripetutamente dentro un ciclo, senza chiamare count. Il programma stampa il numero di occorrenze e la posizione di ciascuna, contando da zero. Alla fine stampa la stessa cosa calcolata con count , come verifica del proprio risultato, e stampa il testo con tutte le occorrenze sostituite da un asterisco per ciascun carattere della sottostringa, ottenuto ricostruendo la stringa con lo slicing e la concatenazione, senza replace.

Attenzione al caso in cui la sottostringa cercata sia vuota: il programma deve rifiutarla con un messaggio prima di iniziare la ricerca.

`````java
import java.util.Scanner;

public class Esercizio12 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Testo: ");
        String testo = sc.nextLine();
        System.out.print("Sottostringa da cercare: ");
        String sotto = sc.nextLine();

        if (sotto.length() == 0) {
            System.out.println("La sottostringa non può essere vuota");
        } else {
            int occorrenze = 0;
            String posizioni = "";
            String mascherato = "";
            int inizio = 0;

            int pos = testo.indexOf(sotto, inizio);
            while (pos != -1) {
                occorrenze++;
                posizioni = posizioni + pos + " ";
                mascherato = mascherato + testo.substring(inizio, pos);
                for (int k = 0; k < sotto.length(); k++) {
                    mascherato = mascherato + "*";
                }
                inizio = pos + sotto.length();
                pos = testo.indexOf(sotto, inizio);
            }
            mascherato = mascherato + testo.substring(inizio);

            System.out.println("occorrenze: " + occorrenze);
            System.out.println("posizioni: " + posizioni);
            System.out.println("testo mascherato: " + mascherato);
        }
    }
}
`````