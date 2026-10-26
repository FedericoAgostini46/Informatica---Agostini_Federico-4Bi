# MODULO M1 - ESERCIZI
## Esercizio 4 - Lettura di un codice di postazione
Scrivere nella cella dell'esercizio 4 il programma che legge in ingresso un codice di postazione di laboratorio nel formato LAB2-PC17-2026 , dove le prime quattro posizioni indicano il labora‐
torio, le quattro successive al trattino indicano il calcolatore e le ultime quattro l'anno di installazione. Il programma ripulisce l'ingresso dagli spazi agli estremi, lo porta in maiuscolo ed
estrae con lo slicing le tre parti, stampandole su tre righe distinte. Stampa infine la lunghezza del codice e il suo ultimo carattere, ricavato con un indice negativo.

`````java
import java.util.Scanner;

public class Esercizio4 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Codice postazione: ");
        String codice = sc.next();
        codice = codice.trim().toUpperCase();

        System.out.println("laboratorio: " + codice.substring(0, 4));
        System.out.println("calcolatore: " + codice.substring(5, 9));
        System.out.println("anno: " + codice.substring(10, 14));
        System.out.println("lunghezza: " + codice.length()
                + ", ultimo carattere: " + codice.charAt(codice.length() - 1));
    }
}
`````