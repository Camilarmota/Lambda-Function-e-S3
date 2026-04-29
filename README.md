# ☁️ Amazon S3 - Armazenamento em Nuvem

O **Amazon S3** (Simple Storage Service) é um serviço de armazenamento em nuvem da **AWS** que permite **armazenar e acessar dados** de forma **segura** e **escalável**.  
Ele suporta qualquer tipo de arquivo, como vídeos, áudios, imagens, documentos, entre outros.  
É uma solução ideal para **backup** e **armazenamento de objetos**.

---

## 🚀 Vantagens de usar o S3

- **Durabilidade:**  
  Altamente confiável, com **redundância**. Isso significa ter recursos duplicados ou alternativos que garantem que, se um componente falhar, outro imediatamente assume o lugar sem causar interrupção.

- **Disponibilidade:**  
  Garante acesso contínuo aos dados, sem quedas de serviço.

- **Escalabilidade:**  
  Ajusta automaticamente a capacidade de armazenamento conforme a demanda.

- **Segurança:**  
  Oferece **criptografia**, **controle de acesso** e **monitoramento de atividades**.

---

## 📌 Uso comum
- Backup de dados.  
- Hospedagem de sites estáticos.  
- Armazenamento de arquivos para aplicações web e móveis.  
- Suporte para análise de big data e machine learning.  

---

✨ Com o Amazon S3, seus dados ficam sempre **protegidos, disponíveis e escaláveis** para qualquer necessidade.

---

# ⚡ AWS Lambda - Computação Serverless

O **AWS Lambda** é um serviço de **computação serverless** que permite executar código em resposta a **eventos**, **sem a necessidade de gerenciar servidores**.  

Assim que o código é enviado, o Lambda se encarrega de executar automaticamente e **escalar conforme a demanda**.

---

## 🚀 Vantagens do AWS Lambda

- **Execução sob demanda:**  
  O código é executado apenas quando necessário, respondendo a eventos específicos.

- **Escalabilidade automática:**  
  Ajusta a capacidade de execução automaticamente de acordo com o número de eventos.

- **Custo eficiente:**  
  Você paga apenas pelo tempo de execução e pela quantidade de solicitações processadas.

- **Integração com serviços AWS:**  
  Atua como um conector entre diversos serviços da AWS, como **S3**, **DynamoDB**, **API Gateway**, entre outros.

---

## 📌 Uso comum
- Processamento de arquivos enviados para o **S3**.  
- Execução de funções em resposta a mudanças em tabelas do **DynamoDB**.  
- Criação de APIs serverless com **API Gateway**.  
- Automação de fluxos de trabalho e tarefas recorrentes.  

---

✨ Com o **AWS Lambda**, você escreve apenas o código e a AWS cuida do resto: execução, escalabilidade e custo otimizado.

---

# 🚀 Projeto Hands-On: AWS Lambda + S3 + DynamoDB + API Gateway

Este repositório apresenta um **hands-on** (ou seja, um exercício prático, "mão na massa") com os serviços da **AWS**.  
A ideia é aprender de forma prática como os serviços se conectam entre si para formar uma solução completa na nuvem.  

---

## ✨ O que você vai aprender com esse projeto
- O que significa **computação serverless** e como o Lambda funciona.  
- Como criar um bucket no **S3** e trabalhar com eventos de upload.  
- Como gravar e consultar informações em uma tabela **DynamoDB**.  
- Como disponibilizar dados em tempo real através de uma **API Gateway**.  
- Como conectar serviços da AWS para formar uma **arquitetura moderna e escalável**.  

---

# ☁️ Tarefas com Lambda e S3 HandsOn: Projeto de Processamento de Arquivos e Registro no DynamoDB

## 🌟 Sobre o projeto

Este projeto HandsOn demonstra uma arquitetura serverless utilizando AWS S3, Lambda e DynamoDB para o upload, processamento e registro de dados de arquivos. O objetivo é criar um sistema onde o usuário pode fazer upload de arquivos (JSON ou CSV) para um bucket S3, que por sua vez, dispara um processo automatizado para extrair e armazenar os dados em uma tabela DynamoDB. Além disso, uma API será disponibilizada via API Gateway para consulta dos dados registrados.

## 🎯 Caso de Uso Real: Sistema de Processamento de Notas Fiscais

*   O usuário envia um arquivo JSON contendo informações de uma nota fiscal (número, cliente, valor, data, etc.).
*   A Lambda lê e valida o arquivo, depois grava no DynamoDB os campos relevantes.

## 🔄 Fluxo do Projeto

1.  **Upload do Arquivo:** O usuário faz upload de um arquivo (JSON ou CSV) para um bucket configurado no Amazon S3.
2.  **Trigger S3 para Lambda:** Um evento configurado no S3 detecta o novo arquivo e dispara uma função AWS Lambda.
3.  **Processamento da Lambda (Python):** A função Lambda (escrita em Python) é invocada. Ela lê o conteúdo do arquivo uploaded, processa os dados (por exemplo, validação, transformação) e os prepara para armazenamento. A função precisa de uma IAM Role com permissões de leitura no S3 (s3:GetObject) e escrita no DynamoDB (dynamodb:PutItem
4.  **Registro no DynamoDB:** Após o processamento, a Lambda grava os dados extraídos em uma tabela no Amazon DynamoDB.
5.  **API de Consulta (Lambda + API Gateway):** Uma segunda função Lambda será responsável por consultar a tabela do DynamoDB. Esta função será exposta ao mundo externo através de um Amazon API Gateway, permitindo que outros serviços ou aplicações consumam os dados registrados.

## 🛠️ Componentes AWS Utilizados

*   **Amazon S3:** Para armazenamento de objetos (arquivos JSON/CSV).
*   **AWS Lambda:** Para executar código serverless em resposta a eventos (upload no S3, chamadas de API).
*   **Amazon DynamoDB:** Um banco de dados NoSQL totalmente gerenciado para armazenar os dados processados.
*   **Amazon API Gateway:** Para criar, publicar, manter, monitorar e proteger APIs RESTful que integram com as funções Lambda de consulta.

## ▶️ Como Começar (Passos Iniciais)

*   **Configurar Bucket S3:** Crie um bucket S3 para receber os arquivos.
*   **Criar Tabelas DynamoDB:** Defina a estrutura e crie as tabelas necessárias no DynamoDB.
*   **Desenvolver Funções Lambda:** Escreva o código Python para as funções de processamento e consulta.
*   **Configurar Triggers S3:** Configure os eventos no S3 para disparar a Lambda de processamento.
*   **Configurar API Gateway:** Crie e configure o API Gateway para expor a Lambda de consulta.

---

## 📌 Arquitetura Resumida

- **S3** → Recebe os arquivos enviados pelo usuário.  
- **Lambda (1)** → Processa o conteúdo do arquivo.  
- **DynamoDB** → Armazena os dados processados.  
- **Lambda (2)** → Consulta os dados do DynamoDB.  
- **API Gateway** → Exibe os dados processados via endpoint HTTP.  

---

## 🛠️ Pré-requisitos
- Conta na **AWS** (pode usar o [Free Tier](https://aws.amazon.com/free/)).  
- Conhecimentos básicos de **Python** (para entender as funções Lambda).  
- Familiaridade mínima com a **console da AWS** ou com a **AWS CLI**.  

## ✨ Observações

* É recomendado criar uma IAM Role com permissões para Lambda acessar S3 e DynamoDB.

* Estruture os dados no DynamoDB de forma a permitir consultas eficientes (ex: chave primária por ID da nota fiscal).

---

## ✨ Benefícios da Solução

*   Escalabilidade automática: não importa quantas notas fiscais forem processadas, a arquitetura se ajusta automaticamente.
*   Baixo custo: paga-se apenas pelo uso (quantidade de requisições e tempo de execução).
*   Automação completa: desde o upload até a consulta via API.
*   Integração simples: os serviços da AWS trabalham de forma integrada e segura.

---

💡 Esse projeto é uma ótima forma de aprender, na prática, como diferentes serviços da AWS podem trabalhar juntos para criar soluções inteligentes, sem precisar gerenciar servidores.  
