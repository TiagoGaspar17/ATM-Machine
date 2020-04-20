import java.util.Scanner;
class Main {
  public static void main(String[] args) {
    for(;;){
    System.out.println("Olá, seja Bem-vindo ao BTG");

    Scanner entrada = new Scanner(System.in);
    String CPF; 
    String conta;
    String banco;

    do {
      System.out.println("Digite seu CPF:");
      CPF = entrada.nextLine();
      if (CPF.equals("123.456.789-00")){
      System.out.println("CPF Válido");
    } else {
      System.out.println("CPF Inválido. Tente Novamente");
    }
    } while (!CPF.equals("123.456.789-00"));
    
    String Senha;
    int i;
    for(i = 0; i < 3; i++){
      System.out.println("Digite sua Senha");
      Senha = entrada.nextLine();
      if(Senha.equals("01020304")){
        break;
      } else if(i == 2) {
        System.out.println("Conta Bloqueada!");
        System.exit(0);
      }
      }
    

    int opt;
    int Saldo = 1000;
    int valordep;
    int valorsaque;
    String agencia;
    int valortransf;

    for(;;){
    System.out.println("Escolha a transação: ");
    System.out.println("[1] Saldo");
    System.out.println("[2] Depósito");
    System.out.println("[3] Saque");
    System.out.println("[4] Transferência");
    System.out.println("[0] Sair");
    opt = entrada.nextInt();
    do {
      if(opt != 1 && opt != 2 && opt != 3 && opt != 4 && opt != 0){
      System.out.println("Digite novamente a opção:");
      opt = entrada.nextInt();
      }
    } while (opt != 1 && opt != 2 && opt != 3 && opt != 4 && opt != 0);

    switch(opt){
      case 1:
      System.out.println("Saldo: R$ " + Saldo + ",00");
      break;
      
      case 2:
      System.out.println("Insira valor a depositar:");
      valordep = entrada.nextInt();
      Saldo = valordep + Saldo;
      System.out.println("Novo Saldo: R$ " + Saldo + ",00");
      break;

      case 3:
      System.out.println("Quantidade à Sacar:");
      valorsaque = entrada.nextInt();
      Saldo = Saldo - valorsaque;
      System.out.println("Novo Saldo: R$ " + Saldo + ",00");
      break;

      case 4:
      do {
      System.out.println("Banco à ser transferido:");
      banco = entrada.nextLine();
      banco = entrada.nextLine();

      System.out.println("Agência:");
      agencia = entrada.nextLine();

      System.out.println("Conta e Dígito com Hífen:");
      conta = entrada.nextLine();

      if(banco.equals("Banco Bitau") && agencia.equals("2370-3") && conta.equals("85682-8")){
        System.out.println("Informações Corretas");
      } else {
        System.out.println("Informações Incorretas. Digite Novamente");
      }
      } while (!banco.equals("Banco Bitau") || !agencia.equals("2370-3") || !conta.equals("85682-8"));
      System.out.println("Valor a ser transferido:");
      valortransf = entrada.nextInt();
      Saldo = Saldo - valortransf;
      System.out.println("Agora seu saldo é: R$" + Saldo + ",00");

      case 0:
      System.out.println("Tudo Bem!");
    }
      
      int again;
      System.out.println("Deseja realizar mais uma transação?");
      System.out.println("Digite [1] para Sim e [2] para Não");
      again = entrada.nextInt();

      if(again == 2){
        System.out.println("Volte Sempre!");
        System.out.println("");
        break;
      }
    }
    }
    }
    }
  
  
