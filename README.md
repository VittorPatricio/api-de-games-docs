# Api de Games
https://vittorpatricio.github.io/api-de-games-docs/API%20REST%20com%20nodejs/
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
#### Parametro
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games
Exemplo de resposta:
```
[
    {
        "id": 23,
        "title": "Call of duty MW",
        "year": "2019",
        "price": "47"
    },
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    },
    {
        "id": 2323,
        "title": "131312",
        "price": "123123",
        "year": "3123123"
    }
]
```

##### Falha na autenticação! 401
Exemplo de resposta:
```
{
    "err": "token invalido"
}
```
Caso essa resposta aconteceça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

### POST /auth
Esse endpoint é responsável por fazer o processo de loguin
#### Parametros
e-mail]: Email do usuário cadastrado no banco de dados
password: Senha cadastrada pelo usuário

Exemplo:

```
{
    "email": "victordevtb@guiadoprogramador.com",
    "password": "nodejs<3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games
Exemplo de resposta:
```
[
    {
        "id": 23,
        "title": "Call of duty MW",
        "year": "2019",
        "price": "47"
    },
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    },
    {
        "id": 2323,
        "title": "131312",
        "price": "123123",
        "year": "3123123"
    }
]
```

##### Falha na autenticação! 401
Caso essa resposta aconteceça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou E-mail incorretos
Exemplo de resposta:
```
{
  err: "Credenciais inválidas!"
}
```
##### OK! 200
Caso essa resposta aconteça, você vai receber o token JWT para conseguir acessar endpoints protegidos na API:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JkZXZ0YkBndWlhZG9wcm9ncmFtYWRvci5jb20iLCJpYXQiOjE2OTk4OTc4MjksImV4cCI6MTcwMDA3MDYyOX0.c_uRQYV09CVpKfllG9i01LXcFXyaAkL5Qt-ncxR94Gc"
}
```
