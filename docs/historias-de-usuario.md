# 📖 Histórias de Usuário — Sistema de Aluguel de Automóveis

> Documento da **Sprint 1 — Modelagem**. Cada história indica os casos de uso que ela cobre (ver [casos-de-uso.md](casos-de-uso.md)).

---

## 🔐 Usuário

| ID | História | Casos de uso |
|---|---|---|
| US01 | **Como** usuário, **quero** realizar login apenas com email e senha, **para** acessar as funções do meu perfil de forma rápida e segura. | UC01, UC02 |

## 🙋 Cliente

| ID | História | Casos de uso |
|---|---|---|
| US02 | **Como** cliente, **quero** me cadastrar informando meus dados pessoais e meus rendimentos, **para** poder solicitar aluguéis de automóveis. | UC03 |
| US03 | **Como** cliente, **quero** consultar, editar e excluir meus dados cadastrais, **para** manter minhas informações atualizadas, já que elas são usadas na análise financeira. | UC04, UC05, UC06 |
| US04 | **Como** cliente, **quero** consultar os automóveis disponíveis, **para** escolher qual deles desejo alugar. | UC07 |
| US05 | **Como** cliente, **quero** criar pedidos de aluguel escolhendo o automóvel e o período, e acompanhá-los, **para** saber se já foram analisados e aprovados. | UC08, UC09, UC10 |
| US06 | **Como** cliente, **quero** confirmar meu pedido após a aprovação do agente ou cancelá-lo caso desista, **para** ter o controle final sobre o aluguel. | UC11, UC12 |

## 🏢 Agente

| ID | História | Casos de uso |
|---|---|---|
| US07 | **Como** agente, **quero** me cadastrar com as informações da minha instituição e gerenciar esses dados, **para** poder cadastrar automóveis e avaliar pedidos no sistema. | UC13, UC14, UC15, UC16 |
| US08 | **Como** agente, **quero** cadastrar meus automóveis e gerenciá-los, **para** disponibilizá-los para aluguel ou retirá-los do catálogo quando necessário. | UC17, UC18, UC19 |
| US09 | **Como** agente, **quero** consultar os pedidos pendentes dos meus automóveis e registrar uma avaliação financeira, **para** decidir se o cliente tem condições de realizar o aluguel. | UC20, UC21 |

## 🏦 Agente Banco

| ID | História | Casos de uso |
|---|---|---|
| US10 | **Como** agente do tipo banco, **quero** conceder contratos de crédito, **para** financiar o aluguel de clientes que não podem pagar o valor integral. | UC22 |
