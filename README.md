# Tarefas Automatizadas com Lambda Function e S3
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

## 🎯 Objetivo do Projeto

Criar um fluxo onde arquivos enviados para um bucket **S3** sejam automaticamente processados por uma **função Lambda** e os dados resultantes sejam armazenados em uma tabela **DynamoDB**.  
Depois, outra função Lambda disponibilizará esses dados através de uma **API Gateway**, permitindo consulta via endpoint HTTP.

---

## 🔄 Fluxo do Projeto

1. **Upload do arquivo (JSON ou CSV) para o S3**  
   - O usuário envia um arquivo para o **bucket S3**.  
   - Esse bucket é como uma “pasta” na nuvem, capaz de armazenar arquivos de forma segura.

2. **Disparo automático da Lambda (Processamento)**  
   - O envio do arquivo gera um **evento no S3**.  
   - Esse evento aciona automaticamente uma **função Lambda** (em Python).  
   - A função lê o conteúdo do arquivo e prepara os dados.

3. **Gravação dos dados no DynamoDB**  
   - A função Lambda salva os dados processados em uma tabela do **DynamoDB**.  
   - O DynamoDB é um banco de dados NoSQL altamente escalável da AWS, ideal para armazenar informações estruturadas sem depender de servidores.

4. **Consulta dos dados via API Gateway**  
   - Uma segunda **função Lambda** será responsável por buscar os dados no DynamoDB.  
   - Essa função é exposta através do **API Gateway**, que cria uma **API REST**.  
   - Assim, qualquer aplicação ou usuário pode acessar os dados pelo navegador ou ferramentas como o Postman, usando apenas um link (endpoint).

---

## 📌 Arquitetura Resumida

- **S3** → Recebe os arquivos enviados pelo usuário.  
- **Lambda (1)** → Processa o conteúdo do arquivo.  
- **DynamoDB** → Armazena os dados processados.  
- **Lambda (2)** → Consulta os dados do DynamoDB.  
- **API Gateway** → Exibe os dados processados via endpoint HTTP.  

---

## ✨ O que você vai aprender com esse projeto
- O que significa **computação serverless** e como o Lambda funciona.  
- Como criar um bucket no **S3** e trabalhar com eventos de upload.  
- Como gravar e consultar informações em uma tabela **DynamoDB**.  
- Como disponibilizar dados em tempo real através de uma **API Gateway**.  
- Como conectar serviços da AWS para formar uma **arquitetura moderna e escalável**.  

---

## 🛠️ Pré-requisitos
- Conta na **AWS** (pode usar o [Free Tier](https://aws.amazon.com/free/)).  
- Conhecimentos básicos de **Python** (para entender as funções Lambda).  
- Familiaridade mínima com a **console da AWS** ou com a **AWS CLI**.  

---

💡 Esse projeto é uma ótima forma de aprender, na prática, como diferentes serviços da AWS podem trabalhar juntos para criar soluções inteligentes, sem precisar gerenciar servidores.  


---
