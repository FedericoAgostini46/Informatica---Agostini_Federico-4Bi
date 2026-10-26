# MODULO M2 - ESERCIZI
## Esercizio 8 - Conversione fra decimale e binario nei due sensi
Scrivere nella cella dell'esercizio 8 il programma che legge in ingresso un intero non negativo, ne costruisce la rappresentazione binaria come stringa con il metodo dei resti successivi, e la confronta con il risultato della funzione predefinita bin , stampando verifica superata oppure verifica fallita . Il programma legge poi una seconda stringa composta di soli zeri e uni e ne calcola il valore decimale scorrendone i caratteri da sinistra a destra, senza usare la conversione predefinita. Se la seconda stringa contiene caratteri diversi da 0 e 1 , il programma lo segnala e non calcola nulla.

`````java
import java.util.Scanner;

public class Esercizio8 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Numero intero non negativo: ");
        int numero = sc.nextInt();

        // da decimale a binario
        int copia = numero;
        String binario = "";
        if (copia == 0) {
            binario = "0";
        }
        while (copia > 0) {
            binario = (copia % 2) + binario;
            copia = copia / 2;
        }

        System.out.println(numero + " in binario: " + binario);
        if (binario.equals(Integer.toBinaryString(numero))) {
            System.out.println("verifica superata");
        } else {
            System.out.println("verifica fallita");
        }

        // da binario a decimale
        System.out.print("Stringa di zeri e uni: ");
        String stringa = sc.next();

        boolean valido = true;
        for (int i = 0; i < stringa.length(); i++) {
            char c = stringa.charAt(i);
            if (c != '0' && c != '1') {
                valido = false;
            }
        }

        if (valido) {
            int valore = 0;
            for (int i = 0; i < stringa.length(); i++) {
                valore = valore * 2 + (stringa.charAt(i) - '0');
            }
            System.out.println(stringa + " in decimale: " + valore);
        } else {
            System.out.println("La stringa deve contenere solo 0 e 1");
        }
    }
}
`````