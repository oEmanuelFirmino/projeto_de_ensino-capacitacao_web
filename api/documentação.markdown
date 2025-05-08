# 🚀 Configuração do Ambiente Backend com Express + TypeScript

> **Objetivo:** Neste guia, vamos estruturar do zero um ambiente backend utilizando **Node.js**, **Express**, e **TypeScript**. Ao final, você terá seu **primeiro servidor rodando**!

---

## 📁 1. Estrutura Inicial do Projeto

Crie a pasta principal onde ficará sua API:

```bash
mkdir api && cd api
```

Abra o projeto no VS Code:

```bash
code .
```

> 💡 _Dica:_ Se o comando `code .` não funcionar, certifique-se de que o VS Code está no seu `PATH`.

---

## 🧱 2. Inicialização do Projeto Node

Execute o comando abaixo e apenas pressione `Enter` para todas as perguntas:

```bash
npm init
```

> ✅ Isso criará o arquivo `package.json`, essencial para gerenciar suas dependências.

---

## 🛠️ 3. Instalação do TypeScript e Ferramentas de Execução

Instale o TypeScript e ferramentas auxiliares para execução:

```bash
npm install typescript ts-node tsx
```

Adicione os tipos do Node (dependência de desenvolvimento):

```bash
npm install @types/node -D
```

---

## 🌐 4. Instalação do Express e Variáveis de Ambiente

Adicione o framework Express e o dotenv:

```bash
npm install express dotenv
```

Instale os tipos do Express para uso com TypeScript:

```bash
npm install @types/express
```

---

## 🧪 5. Arquivo de Variáveis de Ambiente

Crie um arquivo chamado `.env` na **raiz do projeto** com o seguinte conteúdo:

```env
HOST=localhost
PORT=3000
```

> 📦 Esse arquivo será utilizado para armazenar variáveis sensíveis ou configuráveis, como porta e host do servidor.

---

## 🔢 6. Configurando Script de Desenvolvimento

Edite o arquivo `package.json` e adicione o seguinte script na seção de `scripts`:

```json
"scripts": {
  "dev": "tsx --watch src/server.ts"
}
```

> ⚡ Isso permite que você inicie o servidor em modo de desenvolvimento com hot reload.

---

## 🧬 7. Estrutura de Código Fonte

Crie a pasta onde ficará seu código fonte:

```bash
mkdir src
```

Dentro da pasta `src`, crie um arquivo chamado `server.ts` (ou `index.ts`):

```bash
touch src/server.ts
```

---

## 🗞 8. Código do Servidor Express

No arquivo `src/server.ts`, cole o seguinte código:

```ts
import dotenv from "dotenv";
import express from "express";

dotenv.config();

const app = express();
const PORT = process.env.PORT || 3000;
const HOST = process.env.HOST || "localhost";

app.get("/", (req, res) => {
  res.send("Hello World!");
});

app.listen(PORT, () => {
  console.log(`Server is running on http://${HOST}:${PORT}`);
});
```

> 📌 _Este é o seu primeiro endpoint! Quando acessarmos a raiz `/`, ele responderá com “Hello World!”._

---

## 🔧 9. Rodando o Servidor

Para iniciar seu servidor em modo desenvolvimento:

```bash
npm run dev
```

Se tudo estiver correto, você verá no terminal:

```
Server is running on http://localhost:3000
```

Acesse no navegador: [http://localhost:3000](http://localhost:3000)

---

## 📌 Conclusão

🎉 Você configurou um ambiente backend com TypeScript e Express do zero. Este será o ponto de partida para estruturas mais robustas, incluindo rotas, middlewares, autenticação e conexão com banco de dados.

---

> Posteriormente veremos: _Estrutura de rotas e organização de arquivos para escalabilidade._
