# IMC_ALUNO

Exercicio Bônus que foi oferecido

## 🚀 Enunciado

Crie um pacote para armazenar as classes Pessoa e Aluno.

Uma pessoa tem os atributos nome, cpf, peso e altura.

Um aluno tem os mesmos atributos de pessoa mais sua nota, e percentual de presença. 

Crie ainda uma classe chamada FuncoesUteis com os métodos para:

Verificar cpf;
Calcular o IMC (Índice de Massa Corporal);
Avaliar o aluno onde nota >= 5 e presença >= 75% → Aprovado.
Crie uma classe chamada Main que possui o método main() para testar as demais classes.

### 📋 Pré-requisitos

package Pacote;

public class Pessoa {
	 
    String nome; //Começo Criando os Atributos da classe PESSOA
    String cpf;
    double peso;
    double altura;

   
    public Pessoa(String nome, String cpf, double peso, double altura) { //Aqui o Construtor
        this.nome = nome;
        this.cpf = cpf;
        this.peso = peso;
        this.altura = altura;
    }

        public void mostrarInfo() { //Método para mostrar as informações da pessoa conforme foram pedidas

        System.out.println("Nome: " + nome);
        System.out.println("CPF: " + cpf);
        System.out.println("Peso: " + peso + " kg");
        System.out.println("Altura: " + altura + " m");
    }
}

////////////////////////////////////////////////////////////////////////////////

package Pacote;

public class Aluno extends Pessoa { //Aqui eu pego o modelo usado na classe Pessoa e adiciono nota e percentual de presença por ser um Aluno
	  
    double nota;
    double percentualPresenca;

   
    public Aluno(String nome, String cpf, double peso, double altura, double nota, double percentualPresenca) { //Uso o  Construtor
        //Aqui chamo o construtor da classe Pessoa
        super(nome, cpf, peso, altura);
        this.nota = nota;
        this.percentualPresenca = percentualPresenca;
    }

    //Utilizo o ,étodo para mostrar as informações do aluno
    @Override
    public void mostrarInfo() {
        super.mostrarInfo(); //Mostro as informações herdadas da classe Pessoa
        System.out.println("Nota: " + nota);
        System.out.println("Presença: " + percentualPresenca + "%");
    }
}
///////////////////////////////////////////////////////////////////////////////
package Pacote;

public class FuncoesUteis {
	
    public static boolean verificarCpf(String cpf) { //Conforme foi pedido verifico se o CPF tem o formato correto (simples, sem validação completa)
        return cpf.length() == 14 && cpf.charAt(3) == '.' && cpf.charAt(7) == '.' && cpf.charAt(11) == '-';
    }

    
    public static double calcularImc(double peso, double altura) { //Calculo o IMC da pessoa
        if (altura <= 0) {
            return -1; //Aqui retorna um valor inválido se altura for zero ou negativa
        }
        return peso / (altura * altura);
    }

    
    public static boolean avaliarAluno(double nota, double percentualPresenca) { //E por ultimo avalia se o aluno está aprovado com base na nota e percentual de presença
        return nota >= 5 && percentualPresenca >= 75;
    }

}
/////////////////////////////////////////////////////////////////////////////

package Pacote;

public class Main {
	 public static void main(String[] args) { //Conforme foi pedido irei testar as demais classes
	        
	        Pessoa pessoa = new Pessoa("João Silva", "123.456.789-00", 80.0, 1.75); //Criando pessoa
	        System.out.println("Informações da Pessoa:");
	        pessoa.mostrarInfo();
	        System.out.println();

	       
	        Aluno aluno = new Aluno("Maria Souza", "987.654.321-00", 70.0, 1.65, 8.0, 80); //Criando um Aluno
	        System.out.println("Informações do Aluno:");
	        aluno.mostrarInfo();
	        System.out.println();

	        
	        System.out.println("Verificando CPF do aluno: " + FuncoesUteis.verificarCpf(aluno.cpf)); //E usando as funções úteis
	        System.out.println("IMC do aluno: " + FuncoesUteis.calcularImc(aluno.peso, aluno.altura));
	        System.out.println("Aluno aprovado? " + FuncoesUteis.avaliarAluno(aluno.nota, aluno.percentualPresenca));
	    }
}
////////////////////////////////////////////////////////////////////////////////


### 🔧 Instalação

* Explicação de como deve ser utilizado o projeto

## 🛠️ Construído com

Ferramentas utilizadas e bibliotecas

* IDE Eclipse

## 📌 Versão

* **Versão 1.0** caso seja atualizado manter a descrição inicial e inserir uma nova linha com descrição da atualização.
* **Versão 1.1** - *Refatoração* *data 09/09/24*

## ✒️ Autores

* João Carlos Ferreira de Araujo RA 248152 - AC2 BÔNUS GAME
