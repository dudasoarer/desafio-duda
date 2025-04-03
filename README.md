# 🏆 Desafio - Consumo de API Pública

Este repositório contém a implementação completa do desafio de desenvolvimento frontend e backend para consumir dados da API pública do **TCE-RJ**.

## 📌 Descrição do Projeto

O projeto consiste em uma aplicação web desenvolvida com **React + TypeScript + Vite** para exibir dados extraídos da API pública do TCE-RJ. Além disso, um **backend Node.js** foi implementado para atuar como proxy e contornar bloqueios de CORS atrelados a API pública.

A aplicação permite que os usuários filtrem, visualizem e analisem os dados relacionados a **compras diretas do estado e municípios do RJ**, utilizando gráficos interativos.

---

## 🚀 Tecnologias Utilizadas

### 🖥️ **Frontend**
| Tecnologia  | Descrição |
|------------|------------|
| **React**  | Biblioteca para construção da interface do usuário |
| **TypeScript** | Superset do JavaScript com tipagem estática |
| **Vite** | Ferramenta de build rápida para projetos modernos |
| **Material-UI** | Biblioteca de componentes para UI |
| **Recharts** | Visualização de dados e gráficos interativos |
| **Axios** | Cliente HTTP para consumo de API |

### ⚙️ **Backend**
| Tecnologia  | Descrição |
|------------|------------|
| **Node.js**  | Ambiente de execução JavaScript no backend |
| **Express.js** | Framework minimalista para Node.js |
| **Axios** | Cliente HTTP para comunicação com API externa |
| **CORS Middleware** | Middleware para permitir requisições cross-origin |

---

## ✨ Funcionalidades

### **Frontend** 📊
- ✅ Consumo da API pública do **TCE-RJ**
- ✅ Interface responsiva e moderna
- ✅ Filtros avançados para busca:
  - **Município**
  - **Valor**
  - **Enquadramento Legal**
  - **Tipo de Compra** (Estado ou Município)
  - **Tipo de Dados** (Normal ou COVID)
- ✅ Exibição organizada das informações
- ✅ Visualização interativa dos dados em **gráficos**:
  - 📊 **Gráfico de Barras**
  - 🥧 **Gráfico de Pizza**
  - 📈 **Gráfico de Linha**
  - 📉 **Gráfico de Barras Horizontais**

### **Backend** 🔧
- ✅ Proxy para API pública, contornando bloqueios de **CORS**
- ✅ Roteamento para diferentes endpoints
- ✅ Filtragem via **query string**
- ✅ Tratamento de erros e respostas padronizadas

---

## 📂 Estrutura do Projeto

```
/desafio-duda
│── frontend/              # Código do frontend (React + TS + Vite)
│   ├── src/
│   │   ├── components/    # Componentes reutilizáveis
│   │   ├── hooks/         # Hooks customizados
│   │   ├── services/      # Configuração do Axios
│   │   ├── layouts/       # Layout principal da aplicação
│   │   ├── App.tsx        # Componente raiz
│   │   ├── main.tsx       # Ponto de entrada
│   │   ├── theme.ts       # Configuração de tema
│   ├── public/            # Arquivos estáticos
│   ├── index.html         # Página principal
│   ├── package.json       # Dependências do projeto
│   ├── tsconfig.json      # Configuração do TypeScript
│   ├── vite.config.ts     # Configuração do Vite
│── backend-proxy/         # Código do backend (Node.js + Express)
│   ├── server.js          # Código principal do backend
│   ├── package.json       # Dependências do backend
│── README.md              # Documentação do projeto
```

---

## 🔧 Como Executar

### **Frontend** 🎨

1️⃣ Clone o repositório:
```sh
git clone https://github.com/seu-usuario/desafio-duda.git
cd desafio-duda/frontend
```

2️⃣ Instale as dependências:
```sh
npm install
```

3️⃣ Inicie o frontend:
```sh
npm run dev
```

4️⃣ Acesse `http://localhost:5173` no navegador.

---

### **Backend** 🛠️

1️⃣ Acesse o diretório do backend:
```sh
cd desafio-duda/backend-proxy
```

2️⃣ Instale as dependências:
```sh
npm install
```

3️⃣ Inicie o backend:
```sh
npm start
```

4️⃣ O backend estará rodando em `http://localhost:3001`.

---

## 🌍 Endpoints do Backend

### **1️⃣ Compras Diretas por Estado**
```
GET /api/compras_diretas_estado
```

- Exemplo de requisição:
```
GET http://localhost:3001/api/compras_diretas_estado?municipio=Rio de Janeiro&valor_minimo=10000
```

### **2️⃣ Compras Diretas por Município**
```
GET /api/compras_diretas_municipio
```

- Exemplo de requisição:
```
GET http://localhost:3001/api/compras_diretas_municipio?enquadramento_legal=Dispensa
```

### **3️⃣ Compras Relacionadas à COVID-19 no Estado**
```
GET /api/compras_covid_estado
```

### **4️⃣ Compras Relacionadas à COVID-19 por Município**
```
GET /api/compras_covid_municipio
```

---

## 🛡️ Tratamento de Erros

| Código | Descrição |
|--------|------------|
| **500** | Erro interno ao acessar a API externa |
| **404** | Endpoint não encontrado |
| **400** | Parâmetros inválidos na requisição |

Exemplo de resposta de erro:
```json
{
  "error": "Erro ao acessar a API"
}
```

---

## 📜 Licença

Este projeto é de código aberto e pode ser utilizado livremente.

📌 Criado para fins de processo seletivo e para contornar bloqueios de CORS na API do TCE-RJ.
