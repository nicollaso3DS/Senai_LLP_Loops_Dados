# Senai_LLP_Loops_Dados
public class SorteioDados {
    public static void main(String[] args) {
        int quantidade = 1; // valor padrão

        // Verifica se o usuário passou argumentos na execução
        if (args.length > 0) {
            try {
                quantidade = Integer.parseInt(args[0]);
                if (quantidade < 1) {
                    System.out.println("A quantidade deve ser maior que 0. Usando 1 dado.");
                    quantidade = 1;
                }
            } catch (NumberFormatException e) {
                System.out.println("Valor inválido. Usando 1 dado.");
            }
        }

        int[] resultados = new int[quantidade];

        // Sorteia os dados
        for (int i = 0; i < quantidade; i++) {
            resultados[i] = (int) (Math.random() * 6) + 1;
        }

        // Mostra os desenhos
        System.out.println("\nResultado dos dados:");
        desenharDados(resultados);
    }

    // Método que imprime os desenhos lado a lado
    public static void desenharDados(int[] resultados) {
        String[][] faces = new String[resultados.length][5];

        for (int i = 0; i < resultados.length; i++) {
            faces[i] = gerarFace(resultados[i]);
        }

        // Imprime as linhas em paralelo
        for (int linha = 0; linha < 5; linha++) {
            for (int dado = 0; dado < resultados.length; dado++) {
                System.out.print(faces[dado][linha] + "   ");
            }
            System.out.println();
        }
    }

    // Retorna uma face desenhada com base no valor
    public static String[] gerarFace(int valor) {
        switch (valor) {
            case 1:
                return new String[]{
                    "+-------+",
                    "|       |",
                    "|   *   |",
                    "|       |",
                    "+-------+"
                };
            case 2:
                return new String[]{
                    "+-------+",
                    "| *     |",
                    "|       |",
                    "|     * |",
                    "+-------+"
                };
            case 3:
                return new String[]{
                    "+-------+",
                    "| *     |",
                    "|   *   |",
                    "|     * |",
                    "+-------+"
                };
            case 4:
                return new String[]{
                    "+-------+",
                    "| *   * |",
                    "|       |",
                    "| *   * |",
                    "+-------+"
                };
            case 5:
                return new String[]{
                    "+-------+",
                    "| *   * |",
                    "|   *   |",
                    "| *   * |",
                    "+-------+"
                };
            case 6:
                return new String[]{
                    "+-------+",
                    "| *   * |",
                    "| *   * |",
                    "| *   * |",
                    "+-------+"
                };
            default:
                return new String[]{
                    "+-------+",
                    "| ERRO  |",
                    "|       |",
                    "| ERRO  |",
                    "+-------+"
                };
        }
    }
}
