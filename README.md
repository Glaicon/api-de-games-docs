# API de Games
Está API foi desenvolvida em Node.js - Um Crud de games.
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça vai ser retornado a lista de games.

Exemplo de resposta:

```
[
    {
        "id": 1,
        "title": "Call of duty MW",
        "year": 2020,
        "price": "60",
        "createdAt": "2020-11-04T19:33:16.000Z",
        "updatedAt": "2020-11-10T21:28:26.000Z"
    },
    {
        "id": 2,
        "title": "Sea of Thieves",
        "year": 2017,
        "price": "40",
        "createdAt": "2020-11-04T19:33:16.000Z",
        "updatedAt": "2020-11-10T21:30:49.000Z"
    },
    {
        "id": 7,
        "title": "PES 2020",
        "year": 2020,
        "price": "70",
        "createdAt": "2020-11-10T21:32:50.000Z",
        "updatedAt": "2020-11-10T21:32:50.000Z"
    },
    {
        "id": 9,
        "title": "CS",
        "year": 2019,
        "price": "30",
        "createdAt": "2020-11-12T15:56:56.000Z",
        "updatedAt": "2020-11-12T17:25:43.000Z"
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivo: Token inválido, Token expirado.

Exemplo de resposta:

```
{
    "err": "Token Inválido!"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de autenticação.
#### Parâmetros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
    "email": "glaiconreis@gmail.com",
    "password": 123456
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça vai receber o token JWT para conseguir acessar endpoint protegidos na API. 

Exemplo de resposta:

```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJnbGFpY29ucmVpc0BnbWFpbC5jb20iLCJpYXQiOjE2MDU2OTA5MjYsImV4cCI6MTYwNTg2MzcyNn0.cfrWKWgewBl7Mm-DnwmsOPkvB6L8d4SYFjtwG0cHadU"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivo: Senha e/ou e-mail errado.

Exemplo de resposta:

```
{
    "err": "Credenciais inválidas!"
}
```
