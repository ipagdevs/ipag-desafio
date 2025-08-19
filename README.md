# 🚀 Desafio Desenvolvedor - iPag

## 📌 Instruções Gerais

1. Leia esse documento com atenção antes de iniciar as atividades.
2. Você terá:

   * **2 dias** para entregar o plano de trabalho (item 1).
   * **Até 7 dias corridos** para concluir as atividades solicitadas.
   * Caso não consiga concluir todas as atividades, entregue o que tiver feito até a data.
   * **Importante:** qualidade e clareza serão mais valorizadas do que quantidade de funcionalidades.
3. Crie um repositório **público** no Github para seu projeto.
4. Ao concluir, envie um e-mail com o assunto:
   `[DESAFIO IPAG] - SEU NOME COMPLETO` para: **[vagas@ipag.com.br](mailto:vagas@ipag.com.br)**, incluindo o link do repositório.
5. Você pode utilizar tecnologias, libs ou técnicas adicionais, desde que documente em seu relatório final os motivos.
6. A aplicação deve rodar com instruções claras de execução (README).
7. Recomendamos a utilização de **Docker** para montagem do ambiente (MySQL, RabbitMQ, aplicação).

   * Se usar Docker, crie uma única imagem com todos os containers configurados.
8. **Não utilize frameworks prontos** (ex.: Laravel, Nest, Adonis, Django).

   * Permitido uso de micro frameworks para endpoints (Express, Flask, Slim, etc.).
   * O objetivo é avaliar sua capacidade de estruturar soluções do zero.
9. Documente bem o seu projeto (README explicativo, arquitetura, decisões técnicas).
10. **Boa sorte!**

---

## 🎯 Escopo

O desafio consiste em criar uma aplicação que simule o fluxo de **cadastro e consulta de pedidos** usando **RabbitMQ + Banco de Dados Relacional**.

### Funcionalidades obrigatórias:

1. **Plano de Trabalho**

   * Liste as atividades como **tasks**.
   * Estime as horas de cada atividade.

2. **API Backend** (PHP, Node.js ou Python)

   * Estrutura limpa, organizada, com boas práticas de programação.
   * Utilize padrões de projeto (MVC, Repository, etc.).

3. **Banco de Dados (MySQL, MariaDB ou PostgreSQL)**

   * Modele e implemente as tabelas necessárias.
   * Crie migrations para criação das tabelas.

4. **Fila (RabbitMQ)**

   * Criar um micro serviço que consome dados da fila e grava no banco.

5. **Endpoints REST**

   * **Enviar pedido para a fila** (conforme JSON abaixo).
   * **Listar pedidos cadastrados** com filtros (data, status, número).
   * **Consultar um pedido específico**.
   * **Valor total de pedidos por cliente em determinado período** (com filtros de data).

### Exemplo de JSON de entrada:

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

---

## 📊 O que será avaliado

* **Qualidade do código** (organização, padrões, clean code).
* **Modelagem do banco** (clareza, normalização, migrations).
* **Uso de filas** (publicar e consumir corretamente).
* **Boas práticas de arquitetura** (separação de responsabilidades, padrões de projeto).
* **Documentação clara** (README com setup, execução, endpoints, decisões).
* **Tratamento de erros e logs** (resiliência e observabilidade).
* **Testes automatizados** (unitários/integrados). → **diferencial importante**.

---

## 🔒 Diferenciais (opcionais)

* Implementação de **testes automatizados**.
* Considerações de **segurança** (validação de entrada, autenticação simples, sanitização de dados).
* Uso de **Docker Compose** para orquestrar todos os serviços (API + Banco + RabbitMQ).
* Arquitetura mais avançada (ex.: Domain-Driven Design, Event-Driven Design).
