import java.util.Scanner;

class Vetor {
    private int[] vetor;

    public void preencher(int n) {
        Scanner scanner = new Scanner(System.in);
        vetor = new int[n];
        System.out.println("Preencha o vetor com " + n + " números inteiros:");
        for (int i = 0; i < n; i++) {
            vetor[i] = scanner.nextInt();
        }
    }

    public int[] getVetor() {
        return vetor;
    }
}

class Matriz {
    private int[][] matriz;

    public void preencher(int m, int n) {
        Scanner scanner = new Scanner(System.in);
        matriz = new int[m][n];
        System.out.println("Preencha a matriz com " + m + " linhas e " + n + " colunas:");
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                matriz[i][j] = scanner.nextInt();
            }
        }
    }

    public int[][] getMatriz() {
        return matriz;
    }
}

class Verificador {
    public boolean éPar(int n) {
        return n % 2 == 0;
    }
}

public class Principal {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Vetor vetor = new Vetor();
        Matriz matriz = new Matriz();
        Verificador verificador = new Verificador();

        System.out.print("Digite o tamanho do vetor: ");
        int tamanhoVetor = scanner.nextInt();
        vetor.preencher(tamanhoVetor);

        System.out.print("Digite o número de linhas da matriz: ");
        int linhasMatriz = scanner.nextInt();
        System.out.print("Digite o número de colunas da matriz: ");
        int colunasMatriz = scanner.nextInt();
        matriz.preencher(linhasMatriz, colunasMatriz);

        int[] vetorInteiros = vetor.getVetor();
        int[][] matrizInteiros = matriz.getMatriz();

        System.out.println("Verificação do vetor:");
        for (int i = 0; i < vetorInteiros.length; i++) {
            System.out.println(vetorInteiros[i] + " é par? " + verificador.éPar(vetorInteiros[i]));
        }

        System.out.println("Verificação da matriz:");
        for (int i = 0; i < linhasMatriz; i++) {
            for (int j = 0; j < colunasMatriz; j++) {
                System.out.println(matrizInteiros[i][j] + " é par? " + verificador.éPar(matrizInteiros[i][j]));
            }
        }

        scanner.close();
    }
}
