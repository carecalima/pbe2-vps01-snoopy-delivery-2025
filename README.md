# SNOOPY PetShop Delivery API
Situação de Aprendizagem - Back-End (Node.JS, JavaSript, VsCode, ORM Prisma, Insomnia)
## Contextualização
SNOOPY PetShop tem atuado em nossa cidade com ótimo atendimento e agilidade, é nosso cliente e necessita de um sistema Web para registro das entregas ou serviços a domicílio, como busca de animais para banho, tosa e outros serviços.<br>O P.O. após uma visita ao cliente elaborou o DER e UML DC(Diagrama de Classes) a seguir e elencou os requisitos funcionais.<br>
![DER e DC](./docs/snoopy-der-dc.png)
## Desafio
Desenvolver as funcionalidades conforme requisitos

### Requisitos funcionais
- [RF001] O sistema deve permitir o CRUD de Motoristas.
    - [RF001.1] Um motorista pode possuir mais de um telefone ou nenhum, desta forma o campo telefones deve ter espaço suficiente para cadastrar vários números (255 caracteres) e permitir nulo.
    - [RF001.2] A rota **readOne** do motorista deve mostrar os dados de um cliente específico e seus pedidos.
- [RF002] O sistema deve permitir o CRUD de pedidos.
    - [RF002.1] O sistema deve associar o pedido a um motorista.
    - [RF002.1] O Pedido deve na rota **read** deve somar o total dos **valores**.

### Casos de teste (Insomnia)
- [CT001] Deve ser cadastrado pelo menos 5 motoristas.
- [CT002] Deve ser cadastrado 1 telefone para cada motorista.
    - [CT002.1] Pelo menos 1 motorista não deve ter telefone cadastrado, ou seja **nulo**.
- [CT003] Cadastre, altere e exclua um motorista.
- [CT004] Cadastre um pedido para cada motorista.
    - [CT004.1] Pelo menos um motorista deve ter dois ou mais pedidos cadastrados.
- [CT005] Cadastre, altere e exclua um pedido.

## Tecnologias
- Node.js
- Prisma
- XAMPP
- MySQL
- VsCode
- Insomnia

## Como testar
- 1 Clone este **repositório**
- 2 Abra o **XAMPP** Control Panel e inicie o Apache e o MySQL
- 3 Abra com o repositorio com **VsCode**
- 4 Crie o arquivo .env na pasta API e adicione as seguintes variáveis de ambiente
```js
DATABASE_URL="mysql://root@localhost:3306/snoopy-delivery?schema=public&timezone=UTC"
```
- 5 Abra o terminal **CTRL + '** cmd ou bash, navegue até a pasta API e execute os comandos
````bash
cd api
npm install
npx prisma migrate dev --name init
npx nodemon
# ou
npm start
````
- 6 Abra o **Insomnia** e importe o arquivo **./docs/insomnia_2025-03-28.yaml** para testar as rotas.
- 7 Caso queira visualizar o banco de dados, abra o **XAMPP** Control Panel e clique em **Admin** no módulo MySQL.
    - O arquivo ./docs/testes.sql é um script com dados de teste para inserir no banco de dados.
- 8 Para parar a execução do servidor, pressione **CTRL + C** no terminal.
