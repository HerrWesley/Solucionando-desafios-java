# Solucionando-desafios-java
## Área do Circulo 
A fórmula para calcular a área de uma circunferência é: area = π . raio2. Considerando para este problema que π = 3.14159:  - Efetue o cálculo da área, elevando o valor de raio ao quadrado e multiplicando por π. A fórmula para calcular a área de uma circunferência é: area = π . raio2. Considerando para este problema que π = 3.14159:  - Efetue o cálculo da área, elevando o valor de raio ao quadrado e multiplicando por π.
### Entrada:
A entrada contém um valor de ponto flutuante (dupla precisão), no caso, a variável raio.
### Saída
Apresentar a mensagem "A=" seguido pelo valor da variável area, conforme exemplo abaixo, com 4 casas após o ponto decimal. Utilize variáveis de dupla precisão (double). Como todos os problemas, não esqueça de imprimir o fim de linha após o resultado, caso contrário, você receberá "Presentation Error".


import java.util.Scanner; 

public class Classe{
	public static void main(String[] args){
		Scanner scan = new Scanner(System.in);

    double raio = scan.nextDouble();
		
		double area = 3.14159 * (Math.pow( raio ,2));

		System.out.printf("A=%.4f\n", area);
	}
}


## Média 3 

Leia quatro números (N1, N2, N3, N4), cada um deles com uma casa decimal, correspondente às quatro notas de um aluno. Calcule a média com pesos 2, 3, 4 e 1, respectivamente, para cada uma destas notas e mostre esta média acompanhada pela mensagem "Media: ". Se esta média for maior ou igual a 7.0, imprima a mensagem "Aluno aprovado.". Se a média calculada for inferior a 5.0, imprima a mensagem "Aluno reprovado.". Se a média calculada for um valor entre 5.0 e 6.9, inclusive estas, o programa deve imprimir a mensagem "Aluno em exame.".

No caso do aluno estar em exame, leia um valor correspondente à nota do exame obtida pelo aluno. Imprima então a mensagem "Nota do exame: " acompanhada pela nota digitada. Recalcule a média (some a pontuação do exame com a média anteriormente calculada e divida por 2). e imprima a mensagem "Aluno aprovado." (caso a média final seja 5.0 ou mais ) ou "Aluno reprovado.", (caso a média tenha ficado 4.9 ou menos). Para estes dois casos (aprovado ou reprovado após ter pego exame) apresente na última linha uma mensagem "Media final: " seguido da média final para esse aluno.

### Entrada

A entrada contém quatro números de ponto flutuante correspendentes as notas dos alunos.

### Saída

Todas as respostas devem ser apresentadas com uma casa decimal. As mensagens devem ser impressas conforme a descrição do problema. Não esqueça de imprimir o enter após o final de cada linha, caso contrário obterá "Presentation Error".

import java.io.IOException;
import java.util.Locale;
import java.util.Scanner;

public class Desafio{
    public static void main(String[] args) throws IOException {

        Scanner sc = new Scanner(System.in);
        sc.useLocale(Locale.ENGLISH);
        Locale.setDefault(new Locale("en", "US"));

        float n1, n2, n3, n4, media;
        double emexame, emexamefinal;
            n1 = sc.nextFloat();
            n2 = sc.nextFloat();
            n3 = sc.nextFloat();
            n4 = sc.nextFloat();

        media = ((n1 * 2) + (n2 * 3) + (n3 * 4) + (n4 * 1)) / 10;

        System.out.printf("Media: %.1f%n" , media);

        if (media >= 7.0) {
          System.out.println("Aluno aprovado.");
        } 
        if (media < 5.0) {
          System.out.println("Aluno reprovado.");
        }
        if (media >= 5.0 && media <= 6.9) {
          System.out.println("Aluno em exame.");
          emexame = sc.nextDouble();
          System.out.printf("Nota do exame: %.1f%n", emexame);
          emexamefinal = ((emexame + media) / 2.0);
            
            if (emexamefinal >= 5.0) {
              System.out.println("Aluno aprovado.");
              System.out.printf("Media final: %.1f%n", emexamefinal);
            }
            else {
              System.out.println("Aluno reprovado");
              System.out.printf("Media final: %.1f%n", emexamefinal);
            }
          
        }
        sc.close();
      
    }
  
}

# A Corrida de Tartarugas

A corrida de tartarugas é um esporte que cresceu muito nos últimos anos, fazendo com que vários competidores se dediquem a capturar tartarugas rápidas, e treina-las para faturar milhões em corridas pelo mundo. Porém a tarefa de capturar tartarugas não é uma tarefa muito fácil, pois quase todos esses répteis são bem lentos. Cada tartaruga é classificada em um nível dependendo de sua velocidade:


Nível 1: Se a velocidade é menor que 10 cm/h .
Nível 2: Se a velocidade é maior ou igual a 10 cm/h e menor que 20 cm/h .
Nível 3: Se a velocidade é maior ou igual a 20 cm/h .

Sua tarefa é identificar qual o nível de velocidade da tartaruga mais veloz de um grupo.

### Entrada
A entrada consiste de múltiplos casos de teste, e cada um consiste em duas linhas: A primeira linha contém um inteiro L (1 ≤ L ≤ 500) representando o número de tartarugas do grupo, e a segunda linha contém L inteiros Vi (1 ≤ Vi ≤ 50) representando as velocidades de cada tartaruga do grupo.

### Saída
Para cada caso de teste, imprima uma única linha indicando o nível de velocidade da tartaruga mais veloz do grupo.


import java.io.IOException;
import java.util.ArrayList;
import java.util.Scanner;

public class Classe {
    public static void main(String args[]) throws IOException {
        Scanner sc = new Scanner(System.in);

        int maior = 0;
        int atual = 0;
        ArrayList<Integer> arrayList = new ArrayList<>();
        int velocidade = 0;
        int nivel = 0;
        int tentativas = 3;
            while (tentativas>0) {
                int n = sc.nextInt();
                    for (int i = 0; i < n; i++) {
                        arrayList.add(sc.nextInt());
                        atual = arrayList.get(i);
                            if (atual > maior) {
                                maior = atual;
                                velocidade = atual;
                                if (velocidade < 10) {
                                    nivel = 1;
                                } else if (velocidade >= 10 && velocidade < 20) {
                                    nivel = 2;
                                } else if (velocidade >= 20) {
                                    nivel = 3;
                                }
                            }
                    }
                    maior = 0;
                    arrayList.clear();
                    tentativas--;
                    System.out.println(nivel);
            }
    }
}


# Combinação de Strings

Crie um algoritmo que receba dois inputs que sejam strings e combine-as alternando as letras de cada string. 

Deve começar pela primeira letra da primeira string, seguido pela primeira letra da segunda string, em seguida pela segunda letra da primeira string e continuar dessa forma sucessivamente.

As letras restantes da cadeia mais longa devem ser adicionadas ao fim da string resultante e retornada.

### Entrada
A entrada contém vários casos de teste. A primeira linha contém um inteiro N que indica a quantidade de casos de teste que vem a seguir. Cada caso de teste é composto por uma linha que contém duas cadeias de caracteres, cada cadeia de caracteres contém entre 1 e 50 caracteres inclusive.

### Saída
Combine as duas cadeias de caracteres da entrada como mostrado no exemplo abaixo e exiba a cadeia resultante.

import java.util.Scanner;

public class Main {
    
    public static void main(String[] args) {
       
        Scanner scan = new Scanner(System.in);
        int casos = Integer.parseInt(scan.nextLine());         
        
        for(int i = 1; i <= casos; i++) {
            
            StringBuilder analise = new StringBuilder();
            String[] palavras = scan.nextLine().split(" ");
        
            int maxSize = Math.max (     
            palavras[0].length(),
            palavras[1].length());
            
            for(int dados = 0; dados < maxSize; dados++) {
                
                if(dados < palavras[0].length()) {
                    
                    analise.append(palavras[0].charAt(dados));
                
                }
                
                if(dados < palavras[1].length()) {
                   
                    analise.append(palavras[1].charAt(dados));
                
                }
            
            }
            
            System.out.println(analise.toString());
       
        }
    
    }

}


# Encaixa ou Não? 

Paulinho tem em suas mãos um novo problema. Agora a sua professora lhe pediu que construísse um programa para verificar, à partir de dois valores muito grandes A e B, se B corresponde aos últimos dígitos de A.

### Entrada
A entrada consiste de vários casos de teste. A primeira linha de entrada contém um inteiro N que indica a quantidade de casos de teste. Cada caso de teste consiste de dois valores A e B maiores que zero, cada um deles podendo ter até 1000 dígitos.

### Saída
Para cada caso de entrada imprima uma mensagem indicando se o segundo valor encaixa no primeiro valor, confome exemplo abaixo.

import java.io.IOException;
import java.util.Scanner;

public class Desafio {

	public static void main(String[] args) throws IOException {
		Scanner leitor = new Scanner(System.in);
		int N = leitor.nextInt();

		for (int i = 0; i < N; i++) {
		  
			String A = leitor.next();
			String B = leitor.next();
			if (A.endsWith(B)) 
				System.out.println("encaixa");
			else 
				System.out.println("nao encaixa");
		}
	}

}
 
