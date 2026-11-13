# E2 – Atletas e Plantel – User Stories

Ficha do atleta, encarregados de educação, consentimento parental e documentos.

**4 features · 14 user stories**

> Falhas marcadas com "(13/10)" foram encontradas nos testes de 13/10/2026.

---

## E2F1 – Ficha do atleta e plantel

### E2F1U1 – Como dirigente, quero que a ficha do atleta só aceite dados possíveis (altura, peso, data de nascimento), para que as estatísticas do plantel estejam corretas.

**Origem:** Auditoria – Ficha do jogador aceita dados físicos e data de nascimento impossíveis (Média); Altura média apresentada com a unidade errada (Baixa); Estatísticas com idade negativa (Baixa) (13/10)

**Critérios de aceitação:**
- Não é possível guardar alturas, pesos ou idades fora de valores realistas
- Não é possível guardar uma data de nascimento no futuro
- As estatísticas do plantel (médias de idade, altura e peso) nunca mostram valores negativos ou impossíveis

### E2F1U2 – Como dirigente, quero adicionar ao plantel um utilizador que já é membro do clube, para que a conta do atleta fique ligada à sua ficha.

**Origem:** Auditoria – Não é possível adicionar ao plantel um utilizador que já é membro do clube (Alta)

**Critérios de aceitação:**
- "Adicionar Jogador" permite escolher um utilizador que já é membro do clube
- A ficha do jogador fica ligada à conta desse utilizador (deixa de estar "sem conta")

### E2F1U3 – Como treinador, quero que a posição do jogador seja a mesma na ficha e nas estatísticas, em todas as modalidades, para que os dados sejam coerentes.

**Origem:** Auditoria – Dois campos de posição diferentes geram dados incoerentes (Média)

**Critérios de aceitação:**
- A posição preferida aparece igual na ficha e nas estatísticas
- Funciona em todas as modalidades (incluindo Futsal)

### E2F1U4 – Como dirigente, quero descarregar um modelo de ficheiro para importar jogadores, para que a importação não falhe por o ficheiro estar no formato errado.

**Origem:** Auditoria – Importação de jogadores sem modelo de ficheiro (Baixa)

**Critérios de aceitação:**
- Na importação de jogadores existe um botão para descarregar o modelo (Excel/CSV)
- O modelo tem as colunas que a importação aceita, com um exemplo preenchido
- Se o ficheiro tiver colunas em falta, a importação indica quais são

---

## E2F2 – Encarregados de educação associados aos atletas (consulta e justificação de faltas)

### E2F2U1 – Como dirigente, quero convidar um encarregado por email e associá-lo ao seu educando, para que os pais tenham acesso à plataforma.

**Origem:** Enunciado do TFC (perfis dirigentes, atletas, pais); Auditoria – Encarregados referidos como membros, mas sem papel na plataforma (Média)

**Critérios de aceitação:**
- Na ficha do atleta, o dirigente pode convidar um encarregado por email
- O encarregado fica associado a esse atleta depois de aceitar o convite

### E2F2U2 – Como encarregado, quero aceitar o convite e criar a minha conta, para que possa aceder à informação do meu educando.

**Origem:** Enunciado do TFC (perfil de pais)

**Critérios de aceitação:**
- O encarregado recebe o convite por email e consegue criar a conta a partir dele
- Depois de criar a conta, vê a informação do seu educando

### E2F2U3 – Como encarregado com mais de um educando no clube, quero alternar entre eles na mesma conta, para que não precise de vários acessos.

**Origem:** Plataforma multimodalidade (hipótese a validar com o orientador)

**Critérios de aceitação:**
- Um encarregado pode estar associado a vários atletas
- Consegue escolher qual educando quer ver, sem sair da conta

### E2F2U4 – Como encarregado, quero ver o calendário de treinos e jogos do meu educando, para que possa organizar os transportes.

**Origem:** Sobre o TFC – informação dispersa em grupos de chat

**Critérios de aceitação:**
- O encarregado vê os treinos e os jogos da equipa do educando, com data, hora e local
- Não consegue editar nem apagar treinos ou jogos

### E2F2U5 – Como encarregado, quero atualizar os contactos de emergência do meu educando, para que o clube tenha sempre dados corretos.

**Origem:** Auditoria – Ficha do jogador aceita dados físicos e data de nascimento impossíveis (Média)

**Critérios de aceitação:**
- O encarregado consegue editar os contactos de emergência do educando
- O telefone e o email são validados antes de guardar

### E2F2U6 – Como dirigente, quero ver que jogadores menores não têm encarregado associado, para que possa completar as fichas antes da época.

**Origem:** Auditoria – Encarregados referidos como membros, mas sem papel na plataforma (Média); consentimento parental obrigatório para menores de 16

**Critérios de aceitação:**
- Existe uma lista ou filtro de jogadores menores sem encarregado
- A lista atualiza quando um encarregado é associado

---

## E2F3 – Consentimento parental (menores de 16 anos)

### E2F3U1 – Como encarregado, quero dar o consentimento parental online para o meu educando com menos de 16 anos, para que o clube tenha a autorização válida sem papel.

**Origem:** Auditoria – Consentimento parental aceita email inválido (Média)

**Critérios de aceitação:**
- O encarregado consegue dar o consentimento a partir da sua conta ou de um link enviado por email
- Fica registada a data do consentimento

### E2F3U2 – Como dirigente, quero que o consentimento só fique "Válido" depois de o encarregado o confirmar num email válido, para que o clube tenha uma autorização real.

**Origem:** Auditoria – Consentimento parental "Válido" com email inválido (Média) (13/10); Consentimento parental aceita email inválido (Média)

**Critérios de aceitação:**
- Não é possível pedir o consentimento com um email inválido (ex.: "pai@")
- O estado fica "Pendente" até o encarregado confirmar
- Só passa a "Válido" depois da confirmação

---

## E2F4 – Documentos do atleta (exame médico, seguro, licença da federação) com validades

### E2F4U1 – Como dirigente, quero guardar na ficha do atleta o exame médico, o seguro e a licença da federação, para que os documentos estejam num só sítio.

**Origem:** Concorrência – ClubePT, EMJOGO e Adjunto guardam documentos dos atletas; o ClubOps360 não

**Critérios de aceitação:**
- É possível anexar ficheiros à ficha do atleta, indicando o tipo de documento
- Cada documento tem uma data de validade
- Os documentos podem ser consultados e substituídos

### E2F4U2 – Como dirigente, quero ser avisado quando um documento está perto de expirar, para que nenhum atleta jogue com documentos fora de validade.

**Origem:** Concorrência – controlo de validades de documentos nas plataformas concorrentes

**Critérios de aceitação:**
- O dirigente é avisado quando faltam poucos dias para um documento expirar
- Existe uma lista de documentos expirados ou em falta
