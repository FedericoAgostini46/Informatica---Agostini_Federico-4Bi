# MODULO M2 - ESERCIZI
## Esercizio 5 - Conteggio dei caratteri di una frase
Scrivere nella cella dell'esercizio 5 il programma che legge in ingresso una frase e conta, con un unico ciclo for sui caratteri, quante vocali, quante consonanti, quante cifre e quanti altri
caratteri contiene. Il programma stampa i quattro conteggi e la percentuale di vocali sul totale dei caratteri, con un decimale. Le lettere accentate vanno considerate consonanti: è una semplificazione voluta, da dichiarare in un commento.

`````java
import java.util.Scanner;

public class Esercizio5 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Frase: ");
        String frase = sc.nextLine();

        int vocali = 0;
        int consonanti = 0;
        int cifre = 0;
        int altri = 0;

        for (int i = 0; i < frase.length(); i++) {
            char c = Character.toLowerCase(frase.charAt(i));
            if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
                vocali++;
            } else if (Character.isLetter(c)) {
                consonanti++;
            } else if (Character.isDigit(c)) {
                cifre++;
            } else {
                altri++;
            }
        }

        System.out.println("vocali: " + vocali + ", consonanti: " + consonanti
                + ", cifre: " + cifre + ", altri: " + altri);

        if (frase.length() > 0) {
            double percentuale = (double) vocali / frase.length() * 100;
            System.out.printf("percentuale di vocali: %.1f%%%n", percentuale);
        }
    }
}
`````