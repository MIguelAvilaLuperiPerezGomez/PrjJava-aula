# Prj Java - Aula

Projeto Java com exercícios práticos de lógica de programação, utilizando estruturas condicionais, laços de repetição e operações matemáticas.

## Exercícios

### Exercício 01 — Conversão de Temperatura
Entrar via teclado com o valor de uma temperatura em graus Celsius, calcular e exibir sua temperatura equivalente em Fahrenheit.

**Fórmula:** `F = C * 1.8 + 32`

### Exercício 02 — Média Aritmética e Situação do Aluno
Calcular e exibir a média aritmética de quatro valores quaisquer digitados pelo usuário.

- Se a média for **maior ou igual a 6** → Aprovado
- Se a média for **menor que 3** → Reprovado
- Se a média for **maior ou igual a 3 e menor que 6** → Exame

### Exercício 03 — Média Geométrica
Calcular e exibir a média geométrica de quatro valores quaisquer digitados.

**Fórmula:** `M = raiz quarta de (v1 * v2 * v3 * v4)`

### Exercício 04 — Dias no Mês
O programa solicita a digitação dos valores de mês e ano em formato numérico.

- Se o mês estiver **fora do intervalo de 1 a 12**, sinaliza erro e solicita novamente.
- Caso contrário, informa quantos dias tem o mês em questão, considerando anos bissextos para fevereiro.

## Código Final

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        //ex 1
        System.out.println("Digite quantos graus:");
        double l = scanner.nextDouble();
        double f = l * 1.8 + 32;
        System.out.println("convesao para Fahrenheit " + f);

        //ex2
        double soma = 0;
        for (int i = 1; i <= 4; i++) {
            System.out.print("Digite o " + i + "º valor: ");
            double valor = scanner.nextDouble();
            soma += valor;
        }
        double media = soma/4;
        if(media>=6){
            System.out.println("Aprovado");
        } else if (media<3) {
            System.out.println("Reprovado");
        }
        else {
            System.out.println("Exame");
        }
        //ex3
        double produto = 1;
        for(int i = 1; i<=4;i++){
            System.out.print("Digite o valor " + i + ": ");
            double valorR = scanner.nextDouble();
            produto *= valorR;
        }
        double mediaR = Math.pow(produto, 0.25);
        System.out.println("A media geometrica é " +  mediaR);

        //ex4
        int mes;
        int ano;

        do {
            System.out.println("Digite o mes");
            mes = scanner.nextInt();

            if (mes < 1 || mes > 12) {
                System.out.println("Erro: mês inválido! Digite um valor entre 1 e 12.");
            }
        } while (mes < 1 || mes > 12);

        System.out.println("Digite o ano");
        ano = scanner.nextInt();

        int dias;
        switch (mes) {
            case 1: case 3: case 5: case 7: case 8: case 10: case 12:
                dias = 31;
                break;
            case 4: case 6: case 9: case 11:
                dias = 30;
                break;
            case 2:
                boolean bissexto = (ano % 4 == 0 && ano % 100 != 0) || (ano % 400 == 0);
                dias = bissexto ? 29 : 28;
                break;
            default:
                dias = 0;

        }
        System.out.println("O mês " + mes + " de " + ano + " tem " + dias + " dias.");
    }
}
```

## Tecnologias

- Java
- IntelliJ IDEA.

## Autor

Miguel Avila Luperi Perez Gomez
