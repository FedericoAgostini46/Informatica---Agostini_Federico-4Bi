# MODULO M1 - ESERCIZI
## Esercizio 2 - Media dei voti e giudizio
Scrivere nella cella dell'esercizio 2 il programma che legge in ingresso il nome di uno studente, tre voti in virgola mobile e le ore di assenza, calcola la media dei tre voti e stampa il giudizio
secondo questa regola: se le ore di assenza superano 50 il giudizio è non valutabile , indipendentemente dalla media; altrimenti il giudizio è ottimo da 8 in su, sufficiente da 6 in su, insufficiente sotto il 6. La media va stampata con due decimali dentro una f-string, insieme al nome dello studente.

`````java
import java.util.Scanner;

public class Esercizio2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Nome: ");
        String nome = sc.next();
        System.out.print("Voto 1: ");
        double v1 = sc.nextDouble();
        System.out.print("Voto 2: ");
        double v2 = sc.nextDouble();
        System.out.print("Voto 3: ");
        double v3 = sc.nextDouble();
        System.out.print("Ore di assenza: ");
        int assenze = sc.nextInt();

        double media = (v1 + v2 + v3) / 3;
        String giudizio;

        if (assenze > 50) {
            giudizio = "non valutabile";
        } else if (media >= 8) {
            giudizio = "ottimo";
        } else if (media >= 6) {
            giudizio = "sufficiente";
        } else {
            giudizio = "insufficiente";
        }

        System.out.printf("%s: media %.2f, giudizio %s%n", nome, media, giudizio);
    }
}
`````