# MODULO M2 - ESERCIZI
## Esercizio 11 - Palindroma con i due indici
Scrivere nella cella dell'esercizio 11 il programma che legge in ingresso una frase, ne costruisce la versione normalizzata tenendo soltanto le lettere e portandole in minuscolo, e verifica se è palindroma con il confronto fra due indici che si avvicinano dagli estremi verso il centro, interrompendo il ciclo al primo carattere diverso. Lo slicing con passo negativo va usato solo alla fine, per stampare una riga di controllo che confronta il risultato ottenuto con quello dato dal confronto ripulita >= ripulita[>:-1] . Il programma stampa anche quanti confronti sono stati eseguiti prima di decidere.

`````java
import java.util.Scanner;

public class Esercizio11 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Frase: ");
        String frase = sc.nextLine();

        String pulita = "";
        for (int k = 0; k < frase.length(); k++) {
            char c = frase.charAt(k);
            if (Character.isLetter(c)) {
                pulita = pulita + Character.toLowerCase(c);
            }
        }

        int i = 0;
        int j = pulita.length() - 1;
        int confronti = 0;
        boolean palindroma = true;

        while (i < j) {
            confronti++;
            if (pulita.charAt(i) != pulita.charAt(j)) {
                palindroma = false;
                break;
            }
            i++;
            j--;
        }

        // riga di controllo: stringa rovesciata costruita con un ciclo
        String rovesciata = "";
        for (int k = pulita.length() - 1; k >= 0; k--) {
            rovesciata = rovesciata + pulita.charAt(k);
        }

        System.out.println("testo normalizzato: " + pulita);
        System.out.println("palindroma: " + palindroma);
        System.out.println("confronti eseguiti: " + confronti);
        System.out.println("controllo con il rovesciamento: " + pulita.equals(rovesciata));
    }
}
`````