# Azure Data Factory: Processo de Redundância de Arquivos




## 🚀 Etapas do Projeto

A seguir, detalhamos as etapas cruciais para a construção da nossa solução de redundância de dados no Azure:

### 1. Criação do Azure Data Factory (ADF) 🏭

Provisionamos a instância do ADF, que será responsável por orquestrar nosso fluxo de dados.

<p style="text-align:center;">
  <img src="./assets/img/01_data_factory_criado.PNG" alt="Tela de criação do Azure Data Factory concluída" width="100%">
</p>

### 2. Configuração do Banco de Dados SQL Azure 💾

Criamos e configuramos o banco de dados SQL que servirá como nossa fonte de dados original.

<p style="text-align:center;">
  <img src="./assets/img/02_criacao_do_banco_sql_parte1.PNG" alt="Configuração básica do Banco de Dados SQL Azure - Parte 1" width="80%">
</p>

<p style="text-align:center;">
  <img src="./assets/img/03_criacao_do_banco_sql_parte2.jpg" alt="Configuração de segurança e adicionais do Banco de Dados SQL Azure - Parte 2" width="80%">
</p>

### 3. Provisionamento da Conta de Armazenamento (Storage Account) 📦

Configuramos a Conta de Armazenamento com Data Lake Storage Gen2 habilitado, definindo opções de redundância e segurança. Este será o nosso destino.

<p style="text-align:center;">
  <img src="./assets/img/04_storage_account_criado_parte1.jpg" alt="Configuração básica e avançada da Conta de Armazenamento Azure" width="100%">
</p>

<p style="text-align:center;">
  <img src="./assets/img/05_storage_account_criado_parte2.PNG" alt="Configuração de rede, proteção de dados e criptografia da Conta de Armazenamento Azure" width="100%">
</p>

### 4. Criação dos Contêineres no Storage Account 🗂️

Organizamos nosso Data Lake criando contêineres (pastas) como `bronze`, `prata`, `ouro` e `logs`.

<p style="text-align:center;">
  <img src="./assets/img/06_criacao_dos_containers_storage_account.PNG" alt="Lista de contêineres criados na Conta de Armazenamento" width="100%">
</p>

### 5. Configuração do Integration Runtime (IR) 🔌

Utilizamos o `AutoResolveIntegrationRuntime` padrão do Azure para conectividade na nuvem.

<p style="text-align:center;">
  <img src="./assets/img/07_criacao_integration_runtime.jpg" alt="Tela de configuração do Integration Runtime padrão" width="100%">
</p>

### 6. Configuração dos Linked Services 🔗

Definimos as conexões (Linked Services) no ADF para o nosso Banco de Dados SQL (fonte) e para o Data Lake Storage Gen2 (destino).

<p style="text-align:center;">
  <img src="./assets/img/08_linked_services.PNG" alt="Lista de Linked Services criados" width="100%">
</p>

### 7. Construção do Pipeline de Cópia ⚙️➡️📄

Criamos o pipeline no ADF com uma atividade `Copy data` configurada para:
*   Ler dados da tabela especificada no Azure SQL Database (Source).
*   Gravar os dados como um arquivo de texto delimitado no contêiner `prata` do Data Lake (Sink).

<p style="text-align:center;">
  <img src="./assets/img/09_pipeline_parte1.PNG" alt="Adicionando a atividade Copy Data ao pipeline" width="100%">
</p>

<p style="text-align:center;">
  <img src="./assets/img/10_pipeline_parte2.PNG" alt="Configuração do Sink (Destino) da atividade Copy Data" width="100%">
</p>

<p style="text-align:center;">
  <img src="./assets/img/11_pipeline_parte3.PNG" alt="Configuração do Source (Fonte) da atividade Copy Data" width="100%">
</p>

<br>


## ✅ Resultado

Após a configuração completa do pipeline, realizamos um teste de execução (`Debug`). A execução foi bem-sucedida 🎉, confirmando que a atividade de cópia leu os dados do Azure SQL Database e criou um novo arquivo correspondente no contêiner `prata` do Azure Data Lake Storage Gen2. Com isso, alcançamos o objetivo de criar uma redundância básica dos dados da fonte no Data Lake.

<br>


## 👨‍💻 Expert

<p>
    <img 
      align=left 
      margin=10 
      width=80 
      src="https://avatars.githubusercontent.com/u/44624583?v=4"
    />
    <p>&nbsp&nbsp&nbspMarcos Winther<br>
    &nbsp&nbsp&nbsp
    <a href="https://github.com/MarcosWinther">
    GitHub</a>&nbsp;|&nbsp;
    <a href="https://www.linkedin.com/in/marcoswinthersilva/">LinkedIn</a>
    </p>
</p>
<br/><br/>

---

⌨️ com 💜 por [Marcos Winther](https://github.com/MarcosWinther)