------ ATIVIDADDE 01 -----

package handson2;

public class Handson2 {
    public static void main(String[] args) {
        System.out.println(" +\"\"\"\"\"+");
        System.out.println("[| o o |]");
        System.out.println(" |  ^  |");
        System.out.println(" | '-' |");
        System.out.println(" +-----+");
    }
}



------ ATIVIDADDE 02 -----

package handson2;

public class Handson2 {
    public static void main(String[] args) {

        double lat1 = 25.0;
        double lon1 = 35.0;
        double lat2 = 35.5;
        double lon2 = 25.5;

        double r = 6371.01;
        
        lat1 = Math.toRadians(lat1);
        lon1 = Math.toRadians(lon1);
        lat2 = Math.toRadians(lat2);
        lon2 = Math.toRadians(lon2);


        double distancia = r * Math.acos(
                Math.sin(lat1) * Math.sin(lat2) +
                Math.cos(lat1) * Math.cos(lat2) * Math.cos(lon1 - lon2)
        );


        System.out.println("A distância entre esses pontos é: " + distancia + " km");
    }
}



------ ATIVIDADDE 03 -----

package handson2;

import java.util.Scanner;

public class Handson2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Digite uma string: ");
        String texto = sc.nextLine();

        int letras = 0;
        int numeros = 0;
        int espacos = 0;
        int outros = 0;

        for (int i = 0; i < texto.length(); i++) {
            char c = texto.charAt(i);

            if (Character.isLetter(c)) {
                letras++;
            } else if (Character.isDigit(c)) {
                numeros++;
            } else if (Character.isWhitespace(c)) {
                espacos++;
            } else {
                outros++;
            }
        }
        
        System.out.println("Letras: " + letras);
        System.out.println("Números: " + numeros);
        System.out.println("Espaços: " + espacos);
        System.out.println("Outros caracteres: " + outros);

        sc.close();
    }
}


------ ATIVIDADDE 04 -----

package handson2;

import java.util.Scanner;

public class Handson2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int tentativas = 0;
        char resposta;
        boolean acertou = false;

        do {
            System.out.println("\nQuestão:");
            System.out.println("Quanto é 3 x 3?");
            System.out.println("(a) 6");
            System.out.println("(b) 9");
            System.out.println("(c) 12");
            System.out.println("(d) 3");
            System.out.println("(e) 8");
            System.out.print("Escolha uma opção: ");

            resposta = sc.next().toLowerCase().charAt(0);
            tentativas++;

            if (resposta == 'b') {
                System.out.println("Resposta correta!");
                System.out.println("Você acertou na tentativa " + tentativas + ".");
                acertou = true;
            } else if (resposta == 'a' || resposta == 'c' || resposta == 'd' || resposta == 'e') {
                System.out.println("Resposta incorreta.");
            } else {
                System.out.println("Opção inválida.");
                tentativas--; 
            }

        } while (!acertou && tentativas < 3);

        if (!acertou) {
            System.out.println("Resposta incorreta nas 3 tentativas.");
        }

        sc.close();
    }
}
