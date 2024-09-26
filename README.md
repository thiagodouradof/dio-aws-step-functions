# Assistente de Delivery com AWS Step Functions e Amazon Bedrock

## Descrição do Projeto

Este projeto implementa um assistente de delivery automatizado usando **AWS Step Functions** para orquestrar o fluxo de pedidos de delivery, desde a recepção do pedido até a entrega final. O **Amazon Bedrock** é utilizado para aprimorar a personalização e eficiência do assistente, proporcionando uma experiência de cliente otimizada.

O fluxo automatiza etapas como:
- Recepção e validação de pedidos;
- Integração com serviços de pagamento;
- Personalização do assistente via Amazon Bedrock;
- Atualização do status da entrega;
- Confirmação da entrega.

## Arquitetura

1. **AWS Step Functions**: Coordena as diferentes etapas do fluxo do pedido.
2. **AWS Lambda**: Funções serverless que executam tarefas específicas (validação de pedidos, integração de pagamento, atualização de status).
3. **Amazon Bedrock**: Fornece personalização de alto nível, tornando o assistente mais eficiente e adaptado às preferências do cliente.

### Principais Estados no Fluxo de Trabalho

- **Recepção do Pedido**: Inicia o processo capturando o pedido.
- **Validação do Pedido**: Verifica a validade dos itens do pedido.
- **Integração com Pagamento**: Processa o pagamento utilizando serviços de terceiros.
- **Personalização com Amazon Bedrock**: Melhora a experiência de entrega, ajustando a interação com base em preferências.
- **Atualização de Status da Entrega**: Mantém o cliente informado sobre o status da entrega.
- **Confirmação da Entrega**: Verifica se o pedido foi entregue com sucesso.

## Requisitos

- **AWS Account**: Uma conta AWS ativa com permissões para criar Step Functions, Lambdas e usar o Amazon Bedrock.
- **AWS CLI** ou **AWS Management Console**: Para gerenciar e implantar os recursos.
- **Node.js** (ou outra linguagem de preferência) para criar e gerenciar as funções Lambda.

## Estrutura do Projeto

- **step_function_definition.json**: Definição do fluxo da Step Functions em formato JSON.
- **Lambdas**: Pastas com o código das funções Lambda para validação de pedidos, integração com pagamento e atualização de status.
- **Amazon Bedrock**: Utilizado para personalização do assistente, diretamente integrado no fluxo da Step Functions.

## Instalação

1. **Clonar o Repositório**

2. **Configurar AWS CLI**:

Certifique-se de que a AWS CLI está configurada em seu ambiente local:

```bash
  aws configure
```
3. **Criar as Funções Lambda**:

Implemente cada função Lambda descrita no arquivo step_function_definition.json. Você pode fazer isso manualmente ou automatizar via AWS SAM ou CloudFormation.

4. **Implantar Step Functions**:

Utilize o console da AWS ou AWS CLI para criar a Step Functions baseada no arquivo step_function_definition.json.

## Como Executar

Para executar o assistente de delivery, siga os passos abaixo:

  1. Submeter Pedido: O processo começa com a submissão de um pedido. Isso pode ser feito manualmente via Lambda ou integrado com uma API.
  
  2. Monitorar o Fluxo: Acompanhe a execução do fluxo via AWS Step Functions Console para verificar cada etapa do processo.
  
  3. Receber Notificações: Ao final do fluxo, o cliente é notificado sobre o status de sua entrega.
