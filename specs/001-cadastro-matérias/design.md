# Design — Cadastro de matérias

## Objetivo da experiência

Permitir que a pessoa cadastre, edite e exclua matérias, com orientações claras durante cada ação.

## Histórias atendidas

- **HU01 — Cadastrar matéria:** cadastrar uma matéria para organizá-la e usá-la nas tarefas de estudo.
- **HU02 — Editar matéria:** atualizar o nome de uma matéria existente.
- **HU03 — Excluir matéria:** remover uma matéria da lista de matérias ativas.

## Como a tela funciona

1. A pessoa abre a tela **Matérias**.
2. Vê o formulário para informar o nome e a lista de matérias cadastradas.
3. Informa um nome e seleciona **Adicionar matéria**.
4. O sistema valida o nome e, se estiver correto, adiciona a matéria à lista.
5. A pessoa pode selecionar **Editar** para alterar o nome ou **Excluir** para remover a matéria da lista ativa.

## Elementos da tela

### Cabeçalho

- Título: **Matérias**
- Descrição: “Organize as matérias que fazem parte dos seus estudos.”

### Formulário

**Nome da matéria**
- Informa o nome da matéria. Placeholder: **Ex.: IA**
**Adicionar matéria** 
- Valida e cadastra uma nova matéria
**Salvar alterações**
- Valida e salva o nome durante a edição
**Cancelar** 
- Descarta a edição e limpa o formulário

No modo de cadastro, o botão principal exibe **Adicionar matéria**. No modo de edição, exibe **Salvar alterações**, junto à ação **Cancelar**.

### Lista de matérias

Cada item mostra:

- Nome da matéria.
- Ação **Editar**.
- Ação **Excluir**.

Em telas largas, o conteúdo pode ocupar uma coluna central. Em telas estreitas, o formulário e os itens da lista devem se organizar verticalmente.

## Fluxo principal

1. A pessoa informa o nome da matéria.
2. Seleciona **Adicionar matéria**.
3. O sistema remove espaços do início e do fim e valida o nome.
4. Se o nome for válido e não estiver duplicado, o sistema cadastra a matéria e atualiza a lista.
5. O formulário é limpo e volta ao modo de cadastro.

## Editar uma matéria

1. A pessoa seleciona **Editar** no item desejado.
2. O nome atual é carregado no formulário.
3. O botão principal muda para **Salvar alterações** e aparece a ação **Cancelar**.
4. Ao salvar, o sistema valida o novo nome e atualiza a matéria.
5. Após o sucesso, o formulário é limpo e volta ao modo de cadastro.

O nome atual da própria matéria pode ser mantido sem gerar erro de duplicidade. A validação compara o nome informado com as demais matérias ativas.

## Excluir uma matéria

1. A pessoa seleciona **Excluir** no item desejado.
2. O sistema realiza a exclusão lógica da matéria.
3. A matéria deixa de aparecer na lista ativa.
4. Se a matéria excluída estava em edição, o formulário é limpo e volta ao modo de cadastro.

## Validações e mensagens

- Se o campo nome estiver vazio ou contiver apenas espaços, impedir o envio e mostrar: **Informe o nome da matéria.**
- Remover espaços no início e no fim antes de salvar.
- Comparar nomes sem diferenciar maiúsculas e minúsculas. Por exemplo, **Matemática** e **matemática** são duplicados.
- Se já existir uma matéria ativa com o mesmo nome, mostrar: **Já existe uma matéria com esse nome.**
- Em caso de erro, preservar o texto informado e manter o foco no campo para que a pessoa possa corrigi-lo.

## Estados da tela

- **Lista vazia:** mostrar “Nenhuma matéria cadastrada” e orientar a pessoa a adicionar a primeira.
- **Cadastro:** campo vazio e botão **Adicionar matéria**.
- **Edição:** campo preenchido, botão **Salvar alterações** e ação **Cancelar**.
- **Erro:** mensagem próxima ao campo; o valor digitado permanece disponível para correção.
- **Sucesso:** lista atualizada e formulário limpo.

## Acessibilidade

- Usar um rótulo visível para o campo **Nome da matéria**.
- Permitir operar formulário e ações pelo teclado.
- Exibir foco visível nos controles.
- Anunciar mensagens de validação para leitores de tela.
- Identificar os botões com o nome da matéria, por exemplo, **Editar Matemática** e **Excluir Matemática**.

# Tasks — Cadastro de matérias

- [ ] **T01 — Criar o formulário de matérias**
- [ ] **T02 — Validar o nome**
- [ ] **T03 — Impedir nomes duplicados**
- [ ] **T04 — Cadastrar matérias**
- [ ] **T05 — Exibir a lista de matérias**
- [ ] **T06 — Editar matérias**
- [ ] **T07 — Cancelar edição**
- [ ] **T08 — Excluir matérias logicamente**
- [ ] **T09 — Aplicar o layout responsivo**
- [ ] **T10 — Garantir acessibilidade**
- [ ] **T11 — Conferir os critérios de aceitação**