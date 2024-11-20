# Refinando um Projeto Conceitual de Banco de Dados E-COMMERCE

### Projeto proposto no Bootcamp Suzano - Análise de Dados com Power BI - na plataforma DIO

---

- [Plataforma Dio](https://web.dio.me/home)

---

## Ferramentas utilizadas

- [MySQL Workbench](https://www.mysql.com/products/workbench/)

---

## Descrição do Desafio

*"Modelamos juntos um contexto de e-commerce. Podemos optar pela ferramenta de modelagem utilizada. Porém, é necessário ficar atento! Caso opte por uma variação do modelo entidade-relacionamento, como nas ferramentas MySQL Workbench ou DBDesigner, será preciso especificar as PK e FKs corretamente. Mesmo que esse conceito não seja utilizado na modelagem conceitual, exploramos brevemente suas definições. Portanto, o esquema conceitual desenvolvido será a base empregada para modelar o cenário de E-commerce."*

**Instrutora:** _Juliana Mascarenhas_

---

## Objetivo

Refine o modelo apresentado acrescentando os seguintes pontos:

- **Cliente PJ e PF** – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
- **Pagamento** – Pode ter cadastrado mais de uma forma de pagamento;
- **Entrega** – Possui status e código de rastreio.

---

## Respostas do Desafio

---

- [Esquema do E-commerce](https://github.com/gugagalvaocouto/desafio/blob/main/ecommerce.png)


- Para a entidade **Cliente**, foram criadas duas novas entidades: `Pessoa Jurídica` e `Pessoa Física`, contendo as informações necessárias para cada tipo de cliente.
- Para **Pagamento**, a entidade foi atribuída a outras três entidades para detalhar as formas de pagamento: **Cartão**, **Pix** e **Boleto**.
- A entidade **Entrega** foi criada para armazenar as informações de envio de cada pedido, detalhando: **data do pedido**, **data de envio**, **data de entrega**, **status** e **código de rastreio**.
