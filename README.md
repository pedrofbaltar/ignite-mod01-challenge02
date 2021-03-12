<img alt="Ignite" src="https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fad01ee79-762a-4775-bbb6-354f2f42879a%2Fcover-node.js.png?table=block&id=59ccb235-aecd-43a6-a06b-f09a24e7ede8&width=3840&userId=2851198d-6d7e-47d6-b66a-5928d7b96353&cache=v2" />

<h3 align="center">
  Desafio 02: Trabalhando com middlewares
</h3>

<p align="center">
  🧠 Aplicação de gerenciamento de tarefas - (ToDo).
</p>

---

## 🚀 Sobre o desafio

Nesse desafio foi trabalhado mais a fundo conceitos sobre middlewares no Express. Para fixar mais ainda os conhecimentos obtidos até agora.

É uma aplicação para gerenciar tarefas (em inglês _todos_). Será permitida a criação de um usuário com `name` e `username`, bem como fazer o CRUD de _todos_:

Será permitida a criação de um usuário com `name` e `username`, bem como fazer o CRUD de *todos*:

- Criar um novo _todo_;
- Listar todos os _todos_;
- Alterar o `title` e `deadline` de um _todo_ existente;
- Marcar um _todo_ como feito;
- Excluir um _todo_;

Tudo isso para cada usuário em específico. Além disso, dessa vez teremos um plano grátis onde o usuário só pode criar até dez _todos_ e um plano Pro que irá permitir criar _todos_ ilimitados, isso tudo usando middlewares para fazer as validações necessárias.

---

### 💻 Instalação e Execução do Projeto

- Clone este repositório

```
$ git clone https://github.com/pedrofbaltar/ignite-challenge02
```

- Navegue até o diretório principal do projeto

```
$ cd ignite-challenge02
```

- Instale as dependências com o Yarn

```
$ yarn
```

- Rode a suite de testes

```
$ yarn test
```

- Execute o projeto

```
$ yarn dev
```

---

### 🗺️ Middlewares da aplicação

Aqui teremos uma breve descrição do que cada middleware.

### checksExistsUserAccount

Esse middleware é responsável por receber o username do usuário pelo header e validar se existe ou não um usuário com o username passado. Caso exista, o usuário deve ser repassado para o request e a função next deve ser chamada.

### checksCreateTodosUserAvailability

Esse middleware deve receber o **usuário** já dentro do request e chamar a função next apenas se esse usuário ainda estiver no **plano grátis e ainda não possuir 10 _todos_ cadastrados** ou se ele **já estiver com o plano Pro ativado**.

### checksTodoExists

Esse middleware deve receber o **username** de dentro do header e o **id** de um _todo_ de dentro de `request.params`. Você deve validar o usuário, validar que o `id` seja um uuid e também validar que esse `id` pertence a um _todo_ do usuário informado.

Com todas as validações passando, o _todo_ encontrado deve ser passado para o `request` assim como o usuário encontrado também e a função next deve ser chamada.

### findUserById

Esse middleware possui um funcionamento semelhante ao middleware `checksExistsUserAccount` mas a busca pelo usuário deve ser feita através do **id** de um usuário passado por parâmetro na rota. Caso o usuário tenha sido encontrado, o mesmo deve ser repassado para dentro do `request.user` e a função next deve ser chamada.

---

### 🤨 Observações

Você pode ter acesso à documentação no Notion sobre as rotas e testes clicando [aqui](https://www.notion.so/Desafio-02-Trabalhando-com-middlewares-4f89bf538c2e4ee291382b92bdc36790).

---

### 📜 LIcença

Esse projeto está sob a licença do MIT. Veja o arquivo [LICENSE](./LICENSE).

---

Feito com 💜 por <a href="https://www.linkedin.com/in/pedro-felipe-baltar-2a26a31ab/">Pedro Felipe Baltar</a>
