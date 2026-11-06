# MODULO M2 - ESERCIZI
## Esercizio 6 - Riparazione di un programma difettoso
Il programma seguente dovrebbe leggere la durata di una lezione in minuti e stampare il nome del docente, la durata espressa in ore intere e minuti, e i minuti che restano al netto di una pausa di dieci. Contiene quattro difetti: uno impedisce l'avvio del programma, uno lo interrompe alla prima operazione aritmetica, uno lo interrompe più avanti e uno produce un risultato sbagliato senza alcun messaggio.
Copiare il programma nella cella dell'esercizio 6 e ripararlo, procedendo un difetto alla volta e rieseguendo dopo ogni correzione. Sopra il codice corretto vanno scritte quattro righe di commento, una per difetto, ciascuna nella forma «riga n: messaggio dell'interprete oppure sintomo osservato, causa, correzione». Il difetto silenzioso va descritto indicando che cosa si vede nell'uscita, dato che non produce alcun messaggio.

`````java
import java.util.Scanner;

public class Esercizio6 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Durata della lezione in minuti: ");
        int durata = sc.nextInt();
        String docente = "Trentini";
        int pausa = 10;
        int ore = durata / 60;
        int minuti = durata % 60;

        if (ore >= 2) {
            System.out.println("lezione lunga");
        }
        System.out.println("docente: " + docente);
        System.out.println("durata: " + ore + " ore e " + minuti + " minuti");
        System.out.println("minuti al netto della pausa: " + (durata - pausa));
    }
}
`````