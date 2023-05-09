# **Instalação do Chatwoot + Quepasa + PgAdmin via Docker**

Este é um tutorial passo a passo para instalar o Chatwoot + Quepasa usando Docker, através do repositório **[https://github.com/leomangueira/Chatwoot-Quepasa-Docker.git](https://github.com/leomangueira/Chatwoot-Quepasa-Docker.git)**.

## **Requisitos**

Antes de começar, certifique-se de ter instalado em sua máquina os seguintes softwares:

- Docker
- Docker Compose

## **Passo 1: Clone o repositório**

Clone o repositório **`Chatwoot-Quepasa-Docker`** usando o seguinte comando:

```
git clone https://github.com/leomangueira/Chatwoot-Quepasa-Docker.git
```

## **Passo 2: Configure o arquivo .env**

No diretório clonado, procure os arquivos **`.env`** e configure as variáveis de ambiente de acordo com suas preferências. Certifique-se de que as variáveis estão configuradas corretamente.

```jsx
# Diretórios onde estão salvos os arquivos .env
quepasa-chatwoot/.env
quepasa-source/helpers/.env
```

## **Passo 3: Inicie os containers**

No diretório clonado, execute o seguinte comando para construir e iniciar os containers:

```
docker-compose up --build -d
```

Este comando irá construir as imagens e iniciar os seguintes containers:

**• nginx**
**• quepasa**
**• chatwoot**
**• chatwoot-rails**
**• chatwoot-sidekiq**
**• chatwoot-pgadmin4**
**• chatwoot-postgres**
**• chatwoot-redis**

Aguarde alguns minutos para que todos os serviços sejam iniciados.

![Portainer](https://technervs.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb79832e2-2f82-4caa-a3c4-94bbbc42813a%2FUntitled.png?id=25816eb4-192a-48de-866e-541c1de895cf&table=block&spaceId=5c8ae723-5bac-4d9d-8118-cde809eef646&width=2000&userId=&cache=v2)

## **Passo 4: Acesse o Chatwoot**

Após a inicialização dos containers, abra o navegador e acesse o Chatwoot em **`http://localhost:8080`**.

## **Passo 5: Acesse a API Quepasa**

Após a inicialização dos containers, abra o navegador e acesse a API Quepasa em **`http://localhost:8081/setup`** e crie seu login utilizando uma senha forte.

## **Passo 6: Acesse o PgAdmin**

Após a inicialização dos containers, abra o navegador e acesse o PgAdmin em **`http://localhost:8082`**.

## **Passo 7: Configurações adicionais**

Caso deseje, você pode configurar outras opções nos arquivos **`docker-compose.yml`**, como as portas dos serviços, as versões das imagens, entre outras. Leia a documentação do Docker Compose para mais informações.

## **Conclusão**

💡 Portas configuradas no Nginx para cada aplicação. Para alterar as portas é necessário ajustas os arquivos **`docker-compose.yml`** e **`nginx.conf`**.

```
- "8080:8080" #chatwoot
- "8081:8081" #quepasa
- "8082:8082" #pgadmin
- "8083:8083" #redis
```

Pronto! Agora você tem o Chatwoot + Quepasa + PgAdmin com Nginx rodando em sua máquina, usando Docker. A partir daqui, você pode personalizar e explorar todas as funcionalidades dessas ferramentas de atendimento ao cliente.
