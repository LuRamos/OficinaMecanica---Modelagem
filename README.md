# 📦 Modelagem de Banco de Dados para Sistema de Oficina Mecânica

Bem-vindo ao README da modelagem de banco de dados para um sistema de controle e gerenciamento de ordens de serviço (OS) em uma oficina mecânica! Este projeto tem como objetivo representar e gerenciar todas as informações relacionadas a clientes, veículos, ordens de serviço, mecânicos, serviços e peças, proporcionando uma operação eficiente e escalável para a oficina.

---

## 🖋️ Sobre a Modelagem

Esta modelagem é um desafio do **Bootcamp da Heineken - Inteligência Artificial Aplicada a Dados com Copilot** que foi desenvolvida para um sistema de oficina mecânica, garantindo que todos os dados essenciais sejam armazenados e gerenciados de maneira adequada. A modelagem busca a integridade das informações e a flexibilidade necessária para o gerenciamento de ordens de serviço, peças, serviços realizados e clientes.

### 🎯 Objetivos da Modelagem

- **Cadastro de Clientes**: Gerenciar informações de clientes, como nome, endereço, telefone e veículos.
- **Gestão de Veículos**: Controle de veículos pertencentes aos clientes, incluindo placa, modelo e ano.
- **Gestão de Mecânicos**: Cadastro e controle de mecânicos e suas especialidades.
- **Ordem de Serviço (OS)**: Registro e gerenciamento de ordens de serviço, incluindo serviços e peças utilizadas.
- **Serviços e Peças**: Controle de serviços executados e peças utilizadas durante as ordens de serviço.
- **Autorização de Cliente**: Controle da autorização dos clientes para a execução dos serviços.

---

## 🚀 Entidades Principais e Seus Atributos

### Cliente
```
idCliente (PK)
Nome
Telefone
CPF
Email
```
### Veículo
```
idVeiculo (PK)
Placa (Único)
Modelo
Marca
Ano
idCliente (FK)
```
### Mecânico
```
idMecanico (PK)
Nome
Endereço
Especialidade
```
### Equipe
```
idEquipe (PK)
```
### Ordem de Serviço (OS)
```
idOS (PK)
Data de Emissao
Valor
Status
Data de conclusão
idVeiculo (FK)
idEquipe (FK)
```
### Serviço
```
idServico (PK)
Descricao
Valor Mão de Obra
```

### Referência Mão de Obra
```
idReferencia (PK)
idServico (FK)
Tempo Estimado
Custo
Valor Total
```
### Peças
```
idPecas (PK)
Nome
Valor
```
### Autorização Cliente
```
idAutorizacaoCliente (PK)
Data Autorização
Status
idOS (FK)
idCliente (FK)
```

---

## 🔗 Relacionamentos

- **Cliente e Veículo**: Relacionamento 1:N, onde um cliente pode ter vários veículos, e cada veículo pertence a um único cliente.
- **Mecânico e Equipe**: (Equipes de Mecânicos) Relacionamento N:M, onde um mecânico pode pertencer a várias equipes, e uma equipe pode ter vários mecânicos.
- **Ordem de Serviço (OS) e Veículo**: Relacionamento 1:N, onde uma ordem de serviço está associada a um único veículo, mas um veículo pode ter várias ordens de serviço.
- **Ordem de Serviço (OS) e Equipe**: Relacionamento 1:N, onde uma ordem de serviço é atribuída a uma única equipe, mas uma equipe pode realizar várias ordens de serviço.
- **Serviço e Ordem de Serviço (OS)**: (OS_Serviço) Relacionamento N:M, onde uma ordem de serviço pode incluir vários serviços e um serviço pode estar em várias ordens de serviço.
- **Peça e Ordem de Serviço (OS)**: (OS Peça) Relacionamento N:M, onde uma ordem de serviço pode conter várias peças, e uma peça pode ser usada em várias ordens de serviço.
- **Autorização do Cliente**: Relacionamento 1:1, onde um cliente autoriza cada ordem de serviço antes da execução.

---
