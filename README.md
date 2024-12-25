# ConversaoDeEnergia2
 printf("=== Conversor de Energia ===\n");
    printf("Escolha o tipo de conversão:\n");
    printf("1. Joules para kWh\n"); // Opção 1
    printf("2. BTU para KWh\n"); // Opção 2
    printf("3. Calorias para kWh\n"); // Opção 3
    printf("Digite sua escolha (1-3): ");
    scanf("%d", &opcao); // Aqui lê o que o usuário escolheu

    // Verifica se a pessoa escolheu algo válido
    if (opcao < 1 || opcao > 3) {
        // Se digitou errado, já encerra o programa
        printf("Opção inválida! Tente de novo mais tarde.\n");
        return 1;
    }

    // Pede o valor da energia para converter
    printf("Digite o valor da energia (sem letras!): ");
    scanf("%lf", &energia); // Lê um número (double)

    // Faz a conversão baseada na escolha
    switch (opcao) {
        case 1:
            resultado = joules_para_kwh(energia); // Chama a função para joules -> kWh
            printf("%.2lf Joules viraram %.6lf kWh. Tá aí.\n", energia, resultado);
            break;
        case 2:
            resultado = energia * 0.00029307107; // Converte BTU para kWh
            printf("%.2f BTU se tornam %.5f kWh. Conversão concluída!\n", energia, resultado);
            break;
        case 3:
            resultado = calorias_para_kwh(energia); // Chama a função para calorias -> kWh
            printf("%.2lf Calorias viraram %.6lf kWh. Boa sorte com isso.\n", energia, resultado);
            break;
        default:
            // Essa parte nunca deve acontecer, mas coloquei só por segurança
            printf("Erro bizarro, não deveria chegar aqui.\n");
    }

    // Mensagem final antes de sair
    printf("Valeu por usar o conversor! Programa encerrado.\n");
   
printf("Pressione Enter para sair...");
getchar(); // Para capturar o "Enter"
getchar(); // Para consumir o buffer do scanf
    return 0; // Tudo deu certo
}
