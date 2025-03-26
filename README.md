# Desafio Desenvolvedor - iPag

## Instruções

1. Leia esse documento com atenção antes de iniciar as atividades.
2. Você tem 2 dias, para entregar o plano de trabalho (item 1).
3. Você tem até 7 dias corridos para concluir as atividades aqui solicitadas. Caso não consiga concluir todas as atividades, por favor, entregue o que foi feito até a data solicitada.
4. Crie um repositório no Github para seu projeto e mantenha o seu projeto como público.
5. Ao concluir as etapas de entrega, envie um e-mail, com o assunto "[DESAFIO IPAG] - SEU NOME COMPLETO", para: vagas@ipag.com.br, com o link do repositório do projeto.
6. Fique à vontade para utilizar tecnologias e técnicas não citadas nas atividades ou substituir as que julgar necessário. Informe em seu relatório as modificações e os motivos.
7. A aplicação deve ser entregue “rodando”, com instruções para interagir com ela.
8. Recomendamos a utilização do Docker (http://www.docker.com) para montagem do ambiente (MySql, RabbitMQ, Web Application, etc.). Caso opte pela utilização do Docker, crie uma única imagem com todos os containers e compartilhe em seu relatório final.
9. Não utilize frameworks prontos. Frameworks como Laravel, Nest, Adonis, Django são incríveis, mas não utilize-os. Permitido micro framework para criação de endpoints, como Express, Flask, Slim, etc. **A ideia é avaliar a sua capacidade de desenvolver soluções.**
10. Não se esqueça de documentar o seu projeto. A documentação é tão importante quanto o código.
11. Boa sorte!

## Escopo

Desenvolver uma aplicação que seja capaz de consumir dados de uma fila RabbitMQ e gravar em um banco de dados MySQL. A aplicação deve ser capaz de listar os pedidos cadastrados e consultar um pedido específico.

Para enviar dados para fila, crie um endpoint que receba um JSON com os dados do pedido e envie para a fila.

Exemplo de JSON para envio de pedido para fila:

```json
{
  "order": {
    "order_number": "123456",
    "customer_id": 1,
    "customer_name": "Fulano de Tal",
    "customer_document": "12345678900",
    "total_value": 100.00,
    "order_date": "2025-03-30",
    "order_status": "Aprovado",
    "payment_method": "Cartão de Crédito",
    "installments": 1,
    "items": [
      {
        "product_name": "Produto 1",
        "quantity": 1,
        "unit_value": 50.00
      },
      {
        "product_name": "Produto 2",
        "quantity": 1,
        "unit_value": 50.00
      }
    ]
  }
}
```

## Atividades

1. Elabore e entregue um plano de trabalho.
   - Crie suas atividades em tasks
   - Estime horas
2. Crie uma aplicação utilizando PHP, Node.js ou Python;
   - Tenha visão de código limpo e organizado;
   - Utilize boas práticas de programação;
   - Utilize padrões de projeto, como MVC, Repository, etc.;
3. Modele e implemente uma base de dados (MySQL, MariaDB, PostgreSQL).
   - Crie um script para criação das tabelas. (migration)
4. Crie um micro serviço que consuma dados de uma fila RabbitMQ e grave os dados no banco de dados.
5. Crie um endpoint para enviar um pedido para fila.
   - Exemplo citado no escopo.
6. Crie um endpoint para listar os pedidos cadastrados.
    - Filtros: data de criação, status do pedido, número do pedido.
7. Crie um endpoint para consultar um pedido específico.
8. Crie um endpoint que devolva de forma agregada o valor total de pedidos por cliente em um determinado período.
    - Filtros: data inicial, data final.

## O que será avaliado

- Qualidade do código (organização, padrão de escrita, boas práticas)
- Modelagem do banco de dados
- Uso correto de filas e processamento assíncrono
- Documentação clara do projeto (README explicativo, instruções de execução, arquitetura e decisões técnicas)
- Manejo de erros e logs
- Testes (unitários e/ou integração) (desejável, mas não obrigatório)