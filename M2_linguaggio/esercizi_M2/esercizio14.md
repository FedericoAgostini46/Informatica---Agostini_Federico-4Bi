# MODULO M2 - ESERCIZI
## Esercizio 14 - Ordinamento per conteggio delle cifre
In Java l'ordinamento di un array di numeri si è scritto con lo scambio fra elementi, tipicamente con l'algoritmo a bolle o per selezione. Senza le liste quella tecnica non è disponibile, ma per un insieme di valori che appartengono a un intervallo piccolo e noto esiste un'alternativa: contare quante volte compare ciascun valore possibile e ricostruire il risultato in ordine. È l'idea dell'ordinamento per conteggio. 

Scrivere nella cella dell'esercizio 14 il programma che legge in ingresso una stringa di sole cifre e ne stampa le cifre in ordine crescente, ottenendo il risultato con un ciclo for sulle die‐
ci cifre possibili e con il conteggio delle occorrenze di ciascuna. Il programma stampa anche la distribuzione delle cifre presenti, una riga per cifra, con un istogramma fatto di asterischi. Se l'ingresso contiene caratteri che non sono cifre, il programma lo segnala e si ferma. 

Nel commento finale della cella vanno scritte tre righe che confrontano questo procedimento con l'ordinamento a bolle scritto in Java: quale dei due esegue meno confronti, perché questo qui non è applicabile a un insieme di valori qualsiasi, e che cosa cambierà quando in M3
saranno disponibili le liste.

`````java
import java.util.Scanner;

public class Esercizio14 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Stringa di sole cifre: ");
        String numeri = sc.next();

        boolean soloCifre = true;
        for (int i = 0; i < numeri.length(); i++) {
            if (!Character.isDigit(numeri.charAt(i))) {
                soloCifre = false;
            }
        }

        if (soloCifre == false) {
            System.out.println("L'ingresso contiene caratteri che non sono cifre");
        } else {
            int[] conteggi = new int[10];
            for (int i = 0; i < numeri.length(); i++) {
                conteggi[numeri.charAt(i) - '0']++;
            }

            String ordinate = "";
            for (int d = 0; d < 10; d++) {
                for (int k = 0; k < conteggi[d]; k++) {
                    ordinate = ordinate + d;
                }
            }
            System.out.println("cifre ordinate: " + ordinate);

            for (int d = 0; d < 10; d++) {
                if (conteggi[d] > 0) {
                    String asterischi = "";
                    for (int k = 0; k < conteggi[d]; k++) {
                        asterischi = asterischi + "*";
                    }
                    System.out.println(d + " " + asterischi);
                }
            }
        }
    }
}
`````

Il conteggio non confronta mai le cifre tra loro: fa una passata sulla stringa e una sulle 10 cifre, mentre l'ordinamento a bolle fa circa n*n/2 confronti, quindi con molte cifre ne esegue molti di più.

Non è applicabile a un insieme qualsiasi perché serve un intervallo piccolo e noto di valori possibili: con numeri reali o molto grandi non si può avere un array di contatori per ogni valore.

In M3 con le liste in Python basterà una lista di 10 contatori riempita con una sola passata, come qui l'array, e si potrà usare anche sort() per ordinare valori qualsiasi.