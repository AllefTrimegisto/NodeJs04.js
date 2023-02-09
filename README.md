# NodeJs04.js
Crie um pequeno servidor web que contenha várias rotas.
Em cada rota, você deverá fazer o controle do fluxo de requisições de maneira estática ou dinâmica, alterne entre essas formas usando placeholders e query.

const express = require('express');
const app = express();
const port = 8080;

app.get('/', (req, res) => {
  res.send('Bem-vindo ao servidor');
});

app.get('/:nome', (req, res) => {
  res.send(`Olá, ${req.params.nome}`);
});

app.get('/produto', (req, res) => {
  const produto = req.query.nome;
  res.send(`Você está procurando pelo produto: ${produto}`);
});

app.listen(port, () => {
  console.log(`Servidor rodando na porta ${port}`);
});

Neste exemplo, a primeira rota simplesmente retorna a mensagem "Bem-vindo ao servidor". A segunda rota usa um placeholder para capturar o nome do usuário e retornar a mensagem "Olá, [nome]". A terceira rota usa uma query para capturar o nome do produto e retornar a mensagem "Você está procurando pelo produto: [nome do produto]".
