![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)

[Leia em Português<img src="https://flagcdn.com/w20/br.png" width="20">](#versão-em-português) | [Read in English<img src="https://flagcdn.com/w20/us.png" width="20">](#english-version)

# Restful-Booker API Automation Suite (CI/CD Ready✅) 

---

## English Version
This project features a comprehensive automated testing suite for the **Restful-Booker API**. It demonstrates a robust CRUD lifecycle, security validation, and advanced error-handling scenarios.

## ⚙️ CI/CD & Automated Reporting
This project is fully integrated with **GitHub Actions** to perform automated API regression testing on every push (excluding documentation changes).

* **Continuous Testing (CT):** The pipeline automatically installs dependencies, executes the Postman collection via **Newman**, and validates all assertions.
* **Automated Delivery:** After execution, a professional HTML report is generated using `htmlextra` and automatically deployed to **GitHub Pages**.

### 📊 Live Test Report
You can access the latest automated execution dashboard here:
[**View Live Restful-Booker Report 📈**](https://mysterion147.github.io/restful-booker-api-test-automation/api-tests/)

## 🤓 Manual Execution (Newman)
If you wish to run the suite locally and generate the report manually:

1. **Install Dependencies:**
   ```bash
   npm install -g newman newman-reporter-htmlextra
2. **Generate Report:**
   ```bash
   newman run postman/collection.json -e postman/environment.json -r htmlextra --reporter-htmlextra-title "Restful-Booker Regression Report"

## Project Goals
* Automate the end-to-end flow of booking management.
* Implement dynamic data persistence using Postman Environment Variables.
* Validate API resilience through negative testing and edge-case discovery.
* Generate a complete report using Newman.

## 🛠️ Tech Stack
* **Tool:** Postman
* **Scripting:** JavaScript (Postman Sandbox)
* **Reporting:** Postman Collection Runner and/or Newman (CI/CD Ready)

## 📂 Suite Structure
1. **01 - Health Check**: Verifies if the service is up.
2. **02 - Authentication**: Generates a dynamic `token` for protected routes (PUT/PATCH/DELETE).
3. **03 - Booking Management**: 
    * **POST**: Creates a booking and stores the `bookingId` and `lastName`.
    * **GET**: Retrieves data to ensure persistence.
    * **PUT/PATCH**: Validates full and partial updates using auth headers.
    * **DELETE**: Cleans up the generated data.
4. **04 - Negative Scenarios**: Validates 403 (Unauthorized), 404 (Not Found), and handles the API-specific 405 behavior for redundant deletions.

## 💡 Key Technical Insights
* **Status Code Discovery**: During testing, I identified that the API returns a `405 Method Not Allowed` when attempting to delete a resource that has already been removed, rather than the traditional `404`. This was documented and integrated into the test assertions.
* **Dynamic Variables**: The suite is designed to be "zero-config." All IDs and tokens are passed between requests automatically via environment variables.

## 🚀 How to Run Locally
1. Clone this repository.
2. Import the files from the `/postman` folder into your Postman Workspace.
3. Select the `Restful-Booker-Prod` environment.
4. Open the **Collection Runner** and click **Run Restful-Booker**.


---

## Versão em Português
Este projeto apresenta uma suíte abrangente de testes automatizados para a **API Restful-Booker**. Ele demonstra um ciclo de vida CRUD robusto, validação de segurança e cenários avançados de tratamento de erros.

## ⚙️ CI/CD & Relatórios Automatizados
Este projeto é totalmente integrado ao **GitHub Actions** para realizar testes de regressão de API de forma automatizada a cada push (ignorando alterações apenas em documentação).

* **Teste Contínuo (CT):** O pipeline instala dependências, executa a collection do Postman via **Newman** e valida todas as asserções automaticamente.
* **Entrega Automatizada:** Após a execução, um relatório HTML profissional é gerado via `htmlextra` e publicado automaticamente no **GitHub Pages**.

### 📊 Relatório de Testes (Ao Vivo)
Você pode acessar o dashboard da última execução automatizada aqui:
[**Visualizar Relatório Restful-Booker 📈**](https://mysterion147.github.io/restful-booker-api-test-automation/api-tests/)

## 🤓 Execução Manual (Newman)
Caso deseje rodar a suíte localmente e gerar o relatório manualmente:

1. **Instale as Dependências:**
   ```bash
   npm install -g newman newman-reporter-htmlextra
2. **Gere o Relatorio:**
   ```bash
   newman run postman/collection.json -e postman/environment.json -r htmlextra --reporter-htmlextra-title "Restful-Booker Regression Report"

## Objetivos do Projeto
* Automatizar o fluxo de ponta a ponta da gestão de reservas.
* Implementar persistência dinâmica de dados usando Variáveis de Ambiente do Postman.
* Validar a resiliência da API através de testes negativos e descoberta de casos de borda (edge cases).
* Gerar um relatório completo utilizando Newman.

## 🛠️ Tecnologias
* **Ferramenta:** Postman
* **Scripting:** JavaScript (Postman Sandbox)
* **Relatórios:** Postman Collection Runner e/ou Newman (CI/CD Ready)

## 📂 Estrutura da Suíte
1. **01 - Health Check**: Verifica se o serviço está online.
2. **02 - Autenticação**: Gera um `token` dinâmico para rotas protegidas (PUT/PATCH/DELETE).
3. **03 - Gestão de Reservas**: 
    * **POST**: Cria uma reserva e armazena o `bookingId` e `lastName`.
    * **GET**: Recupera dados para garantir a persistência.
    * **PUT/PATCH**: Valida atualizações totais e parciais usando headers de autenticação.
    * **DELETE**: Limpa os dados gerados.
4. **04 - Cenários Negativos**: Valida 403 (Não autorizado), 404 (Não encontrado) e trata o comportamento específico da API (405) para deleções redundantes.

## 💡 Insights Técnicos
* **Descoberta de Status Code**: Durante os testes, identifiquei que a API retorna `405 Method Not Allowed` ao tentar excluir um recurso que já foi removido, em vez do tradicional `404`. Isso foi documentado e integrado às asserções de teste.
* **Variáveis Dinâmicas**: A suíte foi projetada para ser "zero-config". Todos os IDs e tokens são passados entre as requisições automaticamente via variáveis de ambiente.

## 🚀 Como Executar Localmente
1. Clone este repositório.
2. Importe os arquivos da pasta `/postman` para o seu Workspace do Postman.
3. Selecione o ambiente `Restful-Booker-Prod`.
4. Abra o **Collection Runner** e clique em **Run Restful-Booker**.
