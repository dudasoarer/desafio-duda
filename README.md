desafio-duda

📌 Descrição
Este projeto consiste em um servidor backend desenvolvido com Node.js e Express.js que atua como um proxy para a API de Dados Abertos do TCE-RJ.

O objetivo principal é contornar bloqueios de CORS impostos pela API pública e permitir que uma aplicação frontend consiga consumir os dados sem restrições.

O backend recebe as requisições do frontend, encaminha-as à API pública e retorna os dados processados de forma segura e organizada.

🏆 Motivação
Durante o desenvolvimento do frontend do desafio, foi identificado que a API de Dados Abertos do TCE-RJ bloqueia requisições diretas de origens diferentes (CORS). Isso impossibilita o consumo direto dos dados por aplicações web hospedadas em domínios distintos.

Para solucionar esse problema, este backend proxy foi criado para:

✅ Evitar bloqueios de CORS
✅ Centralizar e processar os dados da API pública
✅ Fornecer um endpoint amigável para o frontend
✅ Permitir filtros dinâmicos via query string

🚀 Funcionalidades
🔹 Proxy para a API pública: Encaminha requisições e retorna os dados tratados.
🔹 Rotas para diferentes endpoints da API: Disponibiliza consultas para compras diretas e compras relacionadas à COVID-19.
🔹 Filtragem via query string: Permite passar parâmetros como município, valor e enquadramento legal.
🔹 Tratamento de erros e respostas padronizadas: Mensagens de erro amigáveis e seguras.
🔹 Middleware CORS ativo: Garante compatibilidade com qualquer frontend.

📦 Tecnologias Utilizadas
Tecnologia	Descrição
Node.js	Runtime para execução do servidor backend
Express.js	Framework para criação de APIs REST
Axios	Cliente HTTP para requisições à API pública
CORS	Middleware para permitir requisições de origens diferentes
📂 Estrutura do Projeto

```/backend-proxy
│── package.json          # Dependências e scripts do projeto
│── package-lock.json     # Controle de versões dos pacotes
│── server.js             # Código principal do servidor
```

🚀 Instalação e Execução
📥 Pré-requisitos
Node.js instalado (versão 14+ recomendada)

Gerenciador de pacotes npm ou yarn

🔧 Passo a Passo
1️⃣ Clone o repositório

```git clone <URL_DO_REPOSITORIO>
cd backend-proxy```

2️⃣ Instale as dependências

```npm install```

3️⃣ Inicie o servidor

```npm start```

4️⃣ O backend estará rodando em `http://localhost:3001`

🌍 Endpoints Disponíveis
🔹 1. Compras Diretas por Estado

Endpoint:
```GET /api/compras_diretas_estado```

Descrição: Retorna a lista de compras diretas realizadas pelo Estado do RJ.

Exemplo de requisição:
```GET http://localhost:3001/api/compras_diretas_estado?municipio=Rio de Janeiro&valor_minimo=10000```

🔹 2. Compras Diretas por Município

Endpoint:
```GET /api/compras_diretas_municipio```

Descrição: Retorna compras diretas feitas pelos municípios do RJ.

Exemplo de requisição:

```GET http://localhost:3001/api/compras_diretas_municipio?enquadramento_legal=Dispensa```

🔹 3. Compras Relacionadas à COVID-19 no Estado
Endpoint:

```GET /api/compras_covid_estado```

Descrição: Retorna a lista de compras emergenciais relacionadas à COVID-19 feitas pelo Estado do RJ.

🔹 4. Compras Relacionadas à COVID-19 por Município
Endpoint:

```GET /api/compras_covid_municipio```

Descrição: Retorna as compras relacionadas à COVID-19 feitas pelos municípios.

🛡️ Tratamento de Erros
O servidor retorna mensagens padronizadas em caso de erro:

```Código	Descrição
500    	Erro interno ao acessar a API externa
404	    Endpoint não encontrado
400	    Parâmetros inválidos na requisição```

Exemplo de erro:

```{
  "error": "Erro ao acessar a API"
}```

🏗 Como Funciona?

📌 Arquitetura
1️⃣ O frontend faz uma requisição para `http://localhost:3001/api/compras_diretas_estado`
2️⃣ O backend recebe a requisição e a repassa para `https://dados.tcerj.tc.br/api/v1/compras_diretas_estado`
3️⃣ A API pública responde com os dados brutos
4️⃣ O backend processa os dados e os retorna ao frontend

Isso garante que o frontend possa acessar os dados sem ser bloqueado pelo CORS.

🔧 Personalização
Se precisar rodar o backend em outra porta, basta definir a variável PORT no ambiente:

```PORT=4000 npm start```
E o backend rodará em `http://localhost:4000`

📜 Licença
Este projeto é de código aberto e pode ser utilizado livremente.

📌 Criado para fins de processo seletivo e para contornar bloqueios de CORS na API do TCE-RJ.
