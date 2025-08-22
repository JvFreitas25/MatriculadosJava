# MatriculadosJava
Este projeto foi desenvolvido como parte dos meus estudos em Java Collections, com foco na interface Set e na implementação TreeSet. Esse exercício me ajudou a consolidar o entendimento sobre o funcionamento de conjuntos em Java e como eles podem ser usados em situações práticas do dia a dia.

```java
package colecoes;

import java.util.Scanner;
import java.util.SortedSet;
import java.util.TreeSet;

public class Matriculados {
	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		SortedSet<String> alunosMat = new TreeSet<>();
		SortedSet<String> alunosFis = new TreeSet<>();
		
		
		String nomeAluno;
		
		System.out.println("Quantas matrículas em Matemática? ");
		int qtdAlunoMat = sc.nextInt();
		sc.nextLine();
		
		for(int i = 0; i < qtdAlunoMat; i++) {
			System.out.printf("Digite o nome do aluno n°%d: ", i + 1);
			nomeAluno = sc.nextLine();
			alunosMat.add(nomeAluno);
		}
		
		System.out.println("Quantas matrículas em Física? ");
		int qtdAlunoFis = sc.nextInt();
		sc.nextLine();
		
		for(int i = 0; i < qtdAlunoFis; i++) {
			System.out.printf("Digite o nome do aluno n°%d: ", i + 1);
			nomeAluno = sc.nextLine();
			alunosFis.add(nomeAluno);
		}
		
		SortedSet<String> alunosComDuasMatriculas = new TreeSet<>(alunosMat);
		alunosComDuasMatriculas.retainAll(alunosFis);
		
		if(alunosComDuasMatriculas.isEmpty()) {
			System.out.println("Nenhum aluno está matriculado nas duas matérias!");
		}else {
			System.out.println("Alunos matriculados nas duas:");
			for(String nome: alunosComDuasMatriculas) {
				System.out.println("Aluno: " + nome);
			}
		}
		
				
		sc.close();
	}
}

```
