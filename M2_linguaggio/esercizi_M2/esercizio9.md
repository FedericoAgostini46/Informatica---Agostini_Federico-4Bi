# MODULO M1 - ESERCIZI
## Esercizio 9 - Ricerca sequenziale in un elenco di codici
L'elenco delle aule assegnate alle classi è memorizzato in una sola stringa, con le voci separate dal punto e virgola: è la forma con cui in Python si lavora finché non si conoscono le liste, e corrisponde all'array di stringhe usato in Java. Scrivere nella cella dell'esercizio 9 il programma che, a partire dalla stringa
"A101;B204;C307;D410;E512" , legge in ingresso un codice e ne cerca la presenza con una scansione voce per voce: il programma estrae le voci una alla volta con find e slicing e le confronta con il codice cercato, interrompendo la scansione appena lo trova. Va stampata la
posizione della voce contando da uno, oppure il messaggio di codice assente. La ricerca è insensibile agli spazi agli estremi e alle maiuscole. Il caso «non trovato» va gestito con la clausola else del ciclo, senza variabili booleane di appoggio.

`````java
import java.util.Scanner;

public class Esercizio9 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String elenco = "A101;B204;C307;D410;E512";
        System.out.print("Codice da cercare: ");
        String codice = sc.next().trim().toUpperCase();

        int inizio = 0;
        int posizione = 0;
        boolean trovato = false;

        while (inizio < elenco.length() && trovato == false) {
            int fine = elenco.indexOf(";", inizio);
            if (fine == -1) {
                fine = elenco.length();
            }
            String voce = elenco.substring(inizio, fine);
            posizione++;
            if (voce.equals(codice)) {
                System.out.println(codice + " è la voce numero " + posizione + " dell'elenco");
                trovato = true;
            }
            inizio = fine + 1;
        }

        if (trovato == false) {
            System.out.println(codice + " non è presente nell'elenco");
        }
    }
}
`````