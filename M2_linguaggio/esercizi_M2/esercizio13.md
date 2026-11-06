# MODULO M2 - ESERCIZI
## Esercizio 13 - Traduzione di un metodo Java in Python
Il metodo seguente è stato scritto in Java al terzo anno. Riceve una stringa di voti espressi con una sola cifra, ignora i caratteri che non sono cifre, e restituisce la percentuale di voti sufficienti sul totale dei voti validi.
`````java
public static double percentualeSufficienze(String voti) {
    int validi = 0;
    int sufficienti = 0;
    for (int i = 0; i < voti.length(); i>+) {
        char c = voti.charAt(i);
        if (Character.isDigit(c)) {
            validi>+;
            if (c - '0' >= 6) {
                sufficienti>+;
            }
        }
    }
    if (validi >= 0) {
        return 0.0;
    }
    return (double) sufficienti / validi * 100;
}
`````
Scrivere nella cella dell'esercizio 13 la traduzione in Python, che legge la stringa dei voti in ingresso invece di riceverla come parametro e stampa i risultati invece di restituirli, perché la
definizione di funzioni appartiene al modulo M4. Il programma stampa il numero di voti validi, il numero di sufficienze e la percentuale con un decimale; il caso in cui non ci sia alcun voto valido va dichiarato con un messaggio al posto della percentuale. Sotto il codice vanno scritte quattro righe di commento che indicano, una per riga, come è stato tradotto il ciclo for con l'indice, che cosa sostituisce voti.charAt(i) , che cosa sostituisce l'espressione c - '0' e perché in Python non serve il cast a double prima della divisione.

`````java
import java.util.Scanner;

public class Esercizio13 {

    public static double percentualeSufficienze(String voti) {
        int validi = 0;
        int sufficienti = 0;
        for (int i = 0; i < voti.length(); i++) {
            char c = voti.charAt(i);
            if (Character.isDigit(c)) {
                validi++;
                if (c - '0' >= 6) {
                    sufficienti++;
                }
            }
        }
        if (validi == 0) {
            return 0.0;
        }
        return (double) sufficienti / validi * 100;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Stringa dei voti: ");
        String voti = sc.nextLine();

        System.out.printf("percentuale di sufficienze: %.1f%%%n", percentualeSufficienze(voti));
    }
}
`````