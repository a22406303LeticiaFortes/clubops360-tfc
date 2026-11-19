# Auditoria de falhas – 19/11/2026

Testes feitos com o perfil **Dirigente**, no clube de teste "TFC Test Club".
Objetivo: voltar a testar as falhas de 13/10 antes de as registar no Notion.
A descrição completa de cada falha (passos para reproduzir, o que acontece, o que devia acontecer) está no Notion.

## Falhas novas

### Treinos

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 1 | Criar Treino pede equipa mas o formulário não tem esse campo | Usabilidade | Baixa |

O erro "Selecione um clube e equipa primeiro." aparece quando está escolhido "Todas as equipas" no menu lateral. É a mesma situação da falha "Criar Jogo pede equipa mas o formulário não tem esse campo" (05/11), mas nos treinos.

## Re-teste das falhas de 13/10

### Não reproduzidas (deixam de contar)

| Falha de 13/10 | Resultado a 19/11 |
|---|---|
| Escalão novo não aparece sem refresh | Não reproduzida – o escalão novo aparece logo, sem atualizar a página |
| Mensagem "Presença guardada" enganadora | Não reproduzida – a mensagem de sucesso só aparece em treinos sem jogadores; com jogadores aparece o erro da falha "Presenças mostram o jogador como 'Sem nome' e não podem ser guardadas" (08/10) |

### Reclassificadas

| Falha de 13/10 | Resultado a 19/11 |
|---|---|
| Impossível criar exercícios na biblioteca (erro de permissões) – Bug, Alta | Passa a "Dirigente vê a opção de criar exercícios mas recebe um erro técnico" – Usabilidade, Baixa. Com os papéis de Admin e de Treinador Principal é possível criar exercícios; só com o papel de Dirigente aparece o erro |

### Confirmadas
- Aviso de validação aparece antes de submeter
- Impossível mudar para o plano Free
- "Volume (min)" do Plano de Treino não é calculado
- Botões de presenças incoerentes – o estado de cada jogador muda num botão "–" que nunca muda de aspeto; o estado (Presente, Atrasado, Ausente, Justificado) só aparece à direita; os botões de cima só têm "Todos presentes" e "Todos ausentes"

As outras falhas de 13/10 passaram para o Notion como estavam.

## Novos detalhes sobre falhas já registadas
- **Presenças "Sem nome" (08/10):** ao guardar com jogadores aparece o erro técnico `invalid input syntax for type uuid: "null"`; ao mudar o estado de um jogador, o estado muda em todos ao mesmo tempo.
- **Espaço aceita capacidade negativa ou zero (08/10):** o espaço "Campo Teste" aparece com "-5 lug." no formulário de criar treino.
- **Importação de jogadores sem modelo de ficheiro (08/10):** confirmada – não há modelo para descarregar nem indicação das colunas; só depois de carregar o ficheiro aparece o passo "Mapear Colunas".

## O que funciona
- Com os papéis de Admin e de Treinador Principal é possível criar exercícios na biblioteca
- O escalão novo aparece logo na lista, sem atualizar a página

## Por confirmar
- A janela "Importar Jogadores" abre e aceita um ficheiro com "Todas as equipas" selecionado, apesar de a página pedir para escolher uma equipa. Falta testar (só com um ficheiro de jogadores de teste) para que equipa iriam os jogadores.
