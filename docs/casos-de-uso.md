# Casos de Uso — Sistema de Aluguel de Automóveis

## Atores
| Ator | Descrição |
|---|---|
| Usuário | Ator genérico que representa qualquer pessoa cadastrada no sistema. Cliente e Agente herdam dele. |
| Cliente | Pessoa física que solicita o aluguel de automóveis e acompanha seus pedidos. |
| Agente | Instituição (empresa ou banco) que cadastra automóveis e realiza a análise financeira dos pedidos. |
| Agente Banco | Agente do tipo banco. Realiza as mesmas ações do Agente e também pode conceder contrato de crédito. |

## Casos de Uso

### Usuário (comum a todos)
- Realizar login
- Realizar logout

### Cliente
- Cadastrar-se como cliente
- Consultar dados cadastrais
- Editar dados cadastrais
- Excluir conta
- Consultar automóveis disponíveis
- Criar pedido de aluguel
- Consultar pedidos de aluguel
- Editar pedido de aluguel
- Cancelar pedido de aluguel
- Confirmar pedido aprovado

### Agente
- Cadastrar-se como agente
- Consultar dados cadastrais
- Editar dados cadastrais
- Excluir conta
- Cadastrar automóvel
- Consultar automóveis
- Editar automóvel
- Consultar pedidos pendentes
- Avaliar pedido

### Agente Banco
- Conceder contrato de crédito

## Decisões de projeto

### Agentes
- O agente foi modelado como a própria instituição (empresa ou banco). Cada instituição possui sua própria conta e realiza a própria análise de crédito.
- Alternativa considerada: instituição com vários agentes (funcionários) vinculados. Foi descartada para reduzir a complexidade do protótipo e registrada como possível evolução futura.

### Automóveis
- Apenas agentes cadastram automóveis.
- Um agente gerencia apenas os automóveis cadastrados por ele (sua própria instituição).
- Ao cadastrar um automóvel, o proprietário é definido automaticamente como a instituição do agente. O modelo permite que o proprietário seja cliente, empresa ou banco, conforme o enunciado, mas no protótipo apenas o cadastro pela instituição proprietária foi contemplado.
- Situações do automóvel: **Disponível**, **Alugado** e **Indisponível**.
- Um automóvel é considerado disponível quando sua situação não é Alugado nem Indisponível. Apenas automóveis disponíveis aparecem para os clientes.
- A situação muda para **Alugado** automaticamente quando o pedido passa para *Contrato em execução*, e volta para **Disponível** automaticamente quando o pedido passa para *Finalizado*.
- **Indisponível** é usada quando o agente precisa retirar o automóvel do catálogo, por qualquer motivo. O agente continua vendo o automóvel, mas os clientes não. Essa alteração é feita no caso de uso *Editar automóvel*.
- O caso de uso *Excluir automóvel* foi substituído pela situação Indisponível (exclusão lógica). Assim, o histórico dos pedidos é preservado.

### Pedidos
- Pedido cancelado não é excluído, apenas tem seu status alterado para *Cancelado*.
- O agente visualiza apenas os pedidos dos automóveis cadastrados por ele.
- Status adicional criado: **Finalizado**, quando o período do contrato termina.
- Após a aprovação, o cliente deve confirmar o pedido. Ao confirmar, o status passa de *Aprovado* para *Contrato em execução*.
- O cliente pode cancelar um pedido aprovado que ainda não foi confirmado.
- O status passa automaticamente para *Finalizado* quando o período de aluguel solicitado termina.

### Contrato de crédito
- O Agente Banco concede contrato de crédito apenas para pedidos dos automóveis cadastrados por ele.
- Alternativa considerada: bancos sem frota própria financiando pedidos de outras empresas. Foi descartada para reduzir a complexidade do protótipo.