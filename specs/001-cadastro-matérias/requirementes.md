# Requisitos — Cadastro de matérias

## Objetivo

Permitir que a pessoa cadastre, edite e exclua matérias, evitando nomes vazios ou duplicados.

## Histórias de usuário

### HU01 — Cadastrar matéria

Como pessoa usuária,  
quero cadastrar uma matéria,  
para organizá-la e utilizá-la nas minhas tarefas de estudo.

### HU02 — Editar matéria

Como pessoa usuária,  
quero editar uma matéria cadastrada,  
para corrigir ou atualizar seu nome.

### HU03 — Excluir matéria

Como pessoa usuária,  
quero excluir uma matéria,  
para removê-la da lista de matérias ativas.

## Regras de negócio

- **RN01:** cada matéria deve possuir um identificador único.
- **RN02:** o nome da matéria é obrigatório e não pode ficar vazio.
- **RN03:** espaços no início e no fim do nome devem ser removidos antes de validar e salvar.
- **RN04:** não podem existir matérias ativas com nomes duplicados. A comparação deve ignorar diferenças entre maiúsculas e minúsculas e espaços excedentes.
- **RN05:** a exclusão de uma matéria deve ser lógica; o registro não deve ser apagado permanentemente.

## Critérios de aceitação

### Cenário 1 — Cadastrar matéria

**Dado que** a pessoa informou um nome válido que ainda não está cadastrado  
**Quando** ela aciona **Adicionar matéria**  
**Então** o sistema salva a matéria com um identificador único, mostra-a na lista e limpa o formulário.

### Cenário 2 — Impedir nome vazio

**Dado que** o campo de nome está vazio ou contém apenas espaços  
**Quando** a pessoa tenta cadastrar a matéria  
**Então** o sistema impede o cadastro e informa: **Informe o nome da matéria.**

### Cenário 3 — Remover espaços excedentes

**Dado que** o nome informado contém espaços no início ou no fim  
**Quando** a pessoa cadastra a matéria  
**Então** o sistema remove esses espaços antes de salvar.

### Cenário 4 — Impedir nomes duplicados

**Dado que** já existe uma matéria ativa com o mesmo nome  
**Quando** a pessoa tenta cadastrar outra matéria com esse nome, mesmo com diferenças de capitalização ou espaços externos  
**Então** o sistema impede o cadastro e informa: **Já existe uma matéria com esse nome.**

### Cenário 5 — Editar matéria

**Dado que** existe uma matéria ativa  
**Quando** a pessoa altera seu nome para um valor válido e salva  
**Então** o sistema atualiza a matéria sem alterar seu identificador.

### Cenário 6 — Excluir matéria

**Dado que** existe uma matéria ativa  
**Quando** a pessoa aciona **Excluir**  
**Então** o sistema marca a matéria como excluída e remove-a da lista de matérias ativas.