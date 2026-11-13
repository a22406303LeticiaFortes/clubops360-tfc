# E3 – Treinos – User Stories

Exercícios, planos de treino, calendário, espaços e presenças.

**5 features · 18 user stories**

> Falhas marcadas com "(13/10)" foram encontradas nos testes de 13/10/2026.

---

## E3F1 – Biblioteca de exercícios

### E3F1U1 – Como treinador, quero criar exercícios na biblioteca do clube sem erros, para que os possa usar nos treinos.

**Origem:** Auditoria – Impossível criar exercícios na biblioteca (Alta) (13/10)

**Critérios de aceitação:**
- É possível criar um exercício na biblioteca sem erro de permissões
- O botão de exercícios pré-definidos carrega os exercícios sem erro
- Os exercícios criados aparecem na biblioteca

---

## E3F2 – Planos de treino reutilizáveis

### E3F2U1 – Como treinador, quero que os exercícios que adiciono a um treino fiquem guardados, para que o plano esteja disponível no dia do treino.

**Origem:** Auditoria – Exercícios adicionados a um treino não ficam guardados (Alta)

**Critérios de aceitação:**
- Depois de guardar o treino, os exercícios continuam lá ao reabrir
- A ordem e a duração dos exercícios mantêm-se

### E3F2U2 – Como treinador, quero abrir e editar um plano de treino guardado, para que o possa reutilizar e ajustar.

**Origem:** Auditoria – Plano de Treino guardado não pode ser consultado nem editado (Alta)

**Critérios de aceitação:**
- Um plano guardado abre no editor de Plano de Treino (e não no de Treino)
- Mostra todos os dados: formato dos campos, objetivos, microciclo e exercícios
- As alterações ficam guardadas

### E3F2U3 – Como treinador, quero criar planos de treino a partir da biblioteca de exercícios do clube, para que não tenha de reescrever os mesmos exercícios.

**Origem:** Auditoria – Plano de Treino não usa a biblioteca de exercícios (Média)

**Critérios de aceitação:**
- Ao adicionar um exercício ao plano, é possível escolhê-lo da biblioteca
- O exercício escolhido traz a descrição e a duração da biblioteca

### E3F2U4 – Como treinador, quero aplicar um plano de treino a um treino agendado, para que não introduza a mesma informação duas vezes.

**Origem:** Auditoria – Plano de Treino e Treino funcionam em separado, com informação duplicada (Média)

**Critérios de aceitação:**
- Num treino agendado, é possível escolher um plano de treino existente
- O mesmo plano pode ser usado em vários treinos
- Aplicar um plano não cria um treino novo duplicado

### E3F2U5 – Como treinador, quero que a duração dos exercícios só aceite valores positivos e que o volume do treino seja calculado sozinho, para que o tempo total esteja correto.

**Origem:** Auditoria – Plano de Treino aceita duração negativa nos exercícios (Baixa); "Volume (min)" do Plano de Treino não é calculado (Baixa) (13/10)

**Critérios de aceitação:**
- Não é possível guardar um exercício com duração negativa ou zero
- O volume total do treino é a soma da duração dos exercícios e atualiza sozinho

---

## E3F3 – Calendário e regras de geração de treinos

### E3F3U1 – Como treinador, quero que o horário de um treino se mantenha igual quando o edito, para que os jogadores não recebam a hora errada.

**Origem:** Auditoria – Editar um treino altera o horário em +1 hora (Alta)

**Critérios de aceitação:**
- Editar e guardar um treino não altera a hora, com ou sem todos os campos preenchidos
- A hora é a mesma antes e depois da mudança de hora (verão/inverno)

### E3F3U2 – Como dirigente, quero que os treinos sejam gerados mesmo que uma regra do calendário seja inválida, para que um erro não bloqueie a época inteira.

**Origem:** Auditoria – Uma regra com horário inválido bloqueia a geração de todos os treinos (Alta)

**Critérios de aceitação:**
- Os treinos das regras válidas são gerados mesmo que exista uma regra inválida
- O dirigente vê que regra falhou e porquê

### E3F3U3 – Como dirigente, quero que as regras de calendário rejeitem horários impossíveis ou duplicados, para que os treinos gerados sejam válidos.

**Origem:** Auditoria – Regras de calendário sem validação de horários, disponibilidade e duplicados (Média)

**Critérios de aceitação:**
- Não é possível criar uma regra com hora de fim anterior à hora de início
- Não é possível criar duas regras iguais para a mesma equipa
- Não é possível criar uma regra fora da disponibilidade do espaço
- Ao rejeitar uma regra, o dirigente vê o motivo

### E3F3U4 – Como dirigente, quero que gerar treinos não crie treinos repetidos, para que o calendário não fique duplicado.

**Origem:** Auditoria – evidência na falha "Plano de Treino e Treino funcionam em separado" (treino de 26/10 18:00 duplicado)

**Critérios de aceitação:**
- Gerar treinos várias vezes para o mesmo período não cria treinos repetidos
- Não aparecem dois treinos da mesma equipa à mesma hora

---

## E3F4 – Locais, espaços e reservas

### E3F4U1 – Como dirigente, quero reservar espaços apenas dentro da sua disponibilidade e sem sobreposições, para que duas equipas nunca fiquem marcadas no mesmo espaço.

**Origem:** Auditoria – Disponibilidades e reservas aceitam horários impossíveis e duplicados (Baixa); Reservas não respeitam a disponibilidade do espaço (Média) (13/10)

**Critérios de aceitação:**
- Não é possível reservar um espaço fora da sua disponibilidade
- Não é possível criar uma reserva com o fim antes do início
- Continua a não ser possível criar reservas sobrepostas no mesmo espaço

### E3F4U2 – Como dirigente, quero que os locais e espaços só aceitem dados válidos (email, telefone, capacidade), para que a informação dos espaços esteja correta.

**Origem:** Auditoria – Local aceita email e telefone inválidos (Baixa); Espaço aceita capacidade negativa ou zero (Baixa)

**Critérios de aceitação:**
- O email e o telefone do local são validados antes de guardar
- A capacidade de um espaço tem de ser maior que zero

### E3F4U3 – Como dirigente, quero criar disponibilidades para vários dias de uma vez e editá-las, para que não tenha de apagar e criar de novo.

**Origem:** Auditoria – Gestão de slots de disponibilidade pouco prática (Baixa)

**Critérios de aceitação:**
- É possível escolher vários dias da semana ao criar uma disponibilidade
- Uma disponibilidade existente pode ser editada
- Não é possível criar duas disponibilidades iguais

---

## E3F5 – Presenças (incluindo avisos e justificações de falta pelo encarregado)

### E3F5U1 – Como treinador, quero registar as presenças com o nome de cada jogador, para que saiba quem esteve em cada treino.

**Origem:** Auditoria – Presenças mostram o jogador como "Sem nome" e não podem ser guardadas (Alta); Mensagem "Presença guardada" enganadora (Média) (13/10)

**Critérios de aceitação:**
- A lista de presenças mostra o nome de cada jogador
- É possível guardar qualquer estado (presente, ausente, atraso) sem erro
- Ao reabrir, as presenças guardadas aparecem como foram registadas

### E3F5U2 – Como treinador, quero que os botões "Todos presentes" e "Todos ausentes" mostrem o estado real da lista, para que não me confunda.

**Origem:** Auditoria – Botões de presenças incoerentes (Baixa) (13/10)

**Critérios de aceitação:**
- O botão realçado corresponde ao estado dos jogadores na lista
- Se os estados forem diferentes, nenhum dos dois botões fica realçado

### E3F5U3 – Como encarregado, quero avisar o treinador de que o meu educando vai faltar, para que ele se possa organizar com antecedência.

**Origem:** Módulo de Presenças existente; Sobre o TFC – comunicação dispersa em grupos de chat

**Critérios de aceitação:**
- O encarregado consegue marcar a falta num treino ou jogo futuro do educando
- O aviso fica registado antes do treino

### E3F5U4 – Como encarregado, quero justificar uma falta do meu educando, para que fique registado o motivo.

**Origem:** Decisão do grupo (o encarregado pode marcar e justificar faltas)

**Critérios de aceitação:**
- O encarregado consegue escrever o motivo de uma falta
- A justificação fica associada ao treino e ao atleta

### E3F5U5 – Como treinador, quero ver as faltas avisadas e justificadas na lista de presenças, para que saiba com quem posso contar.

**Origem:** Decisão do grupo (complemento das faltas avisadas pelo encarregado)

**Critérios de aceitação:**
- Na lista de presenças, as faltas avisadas aparecem assinaladas
- O treinador vê o motivo das faltas justificadas
