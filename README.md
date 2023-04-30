# Api doc estudo
Está Api é utilizada para listar usuarios.
## Endpoints
### Get /admin/users
Esse Endpoint é responsavel por retornar todos os usuarios cadastrados
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Retorna a lista de dados de todos os usuarios cadastrados.
Exemplo de resposta:
```
{
    "users": [
        {
            "id": 2,
            "name": "Nicolas Ribeiro R",
            "email": "admin2@admin.com",
            "pass": "$2a$12$XBHw4jZd7eOle5l/x9uUdegVx1Q/gGFWSO64ZqWraNiiGZEDgCDp.",
            "createdAt": "2023-04-22T20:43:02.000Z",
            "updatedAt": "2023-04-22T20:43:02.000Z"
        },
        {
            "id": 7,
            "name": "Mika",
            "email": "mika@gmail.com",
            "pass": "$2a$12$L5Vpq.AWySJCn.3kxAoe6eNgU9/10dW.eMopHhhISgoK6rVsI1zOa",
            "createdAt": "2023-04-25T02:23:48.000Z",
            "updatedAt": "2023-04-25T02:23:48.000Z"
        },
        {
            "id": 8,
            "name": "Mika 1",
            "email": "mika1@gmail.com",
            "pass": "$2a$12$Li0t2viaOeSn2EgiZGwkOOv2rWlGVfidjWAjlbdzBRopmgvOJjjAW",
            "createdAt": "2023-04-25T02:24:22.000Z",
            "updatedAt": "2023-04-25T02:24:22.000Z"
        }
    ],
    "empresa": "Nativa Web Site"
}
```
##### Falha na autenticação! 401
Insso indica que aconteceu uma falha durante o processo de autenticação da requisição. Motivos: Toquen inválido, Token expirado.
Exemplo de resposta:
```
{
    "err": "Erro de autorização!"
}

```

### POST /auth
Resposnsavel por efetuar o processo de login do usuario.
#### Parametro:
(email): E-mail do usuario cadatrado no sistema.
(pass): Senha de acesso do usuario.
Exemplo:
```
{
    "email": "mika300@gmail.com",
    "pass": "123"
}
```
### Resposta:
##### OK! 200
Recebre o token de autenticação para acessar as rotas.
Recebe os dados do usuario logado.
Exemplo:
```
{
"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTEsImlhdCI6MTY4Mjg5MTk2OCwiZXhwIjoxNjgyOTEzNTY4fQ.uaBTCLw243P2nZY7wg-uCQKtH5ASV1a8fqkL8htRQvI",
    "user": {
        "id": 11,
        "name": "Mika 300",
        "pass": "$2a$12$dif5wRTaOfNIQtqhaG1I4umtnPrJBiHau9JHOLFqVH/.INqW94Cre"
    }
}
```

##### Falha na authenticação 401
Indica que os dados enviados pelo cliente estão invalido.
Exemplo:
```
{
    "err": "Dados de acesso invalido"
}
```
##### Falha no servidor 500
Indica a imposibilidade do servidor emprocessar os dados no momento.
Exemplo:
```
{
    err: "Server error!"
}
```



