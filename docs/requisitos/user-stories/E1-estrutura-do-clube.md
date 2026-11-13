# E1 – Estrutura do Clube – User Stories

Criação e configuração do clube, épocas, escalões, equipas, papéis e entrada de novos membros.

**6 features · 28 user stories**

> Falhas marcadas com "(13/10)" foram encontradas nos testes de 13/10/2026.

---

## E1F1 – Configuração inicial do clube

### E1F1U1 – Como dirigente, quero que o email, website, telefone, NIF e morada do clube sejam validados, para que os contactos do clube estejam corretos.

**Origem:** Auditoria – Wizard aceita email e website inválidos (Baixa); Criação de clube aceita telefone, NIF, morada inválidos (Baixa)

**Critérios de aceitação:**
- Não é possível guardar um email sem formato válido (ex.: "teste@")
- Não é possível guardar um website sem formato válido
- O NIF só aceita 9 dígitos
- O telefone só aceita números (e o indicativo)
- Ao rejeitar um campo, o utilizador vê qual é e porquê

### E1F1U2 – Como administrador, quero que os dados do clube sejam validados em cada passo da criação, e não só no fim, para que não tenha de voltar atrás para corrigir.

**Origem:** Auditoria – Validação dos dados do clube só acontece no último passo da criação (Baixa)

**Critérios de aceitação:**
- Não é possível avançar para o passo seguinte com um campo inválido
- O erro aparece junto ao campo, no próprio passo
- Um subdomínio já usado é indicado logo no passo do subdomínio

### E1F1U3 – Como dirigente, quero poder editar todos os dados que preenchi ao criar o clube, incluindo o website, para que possa corrigir erros.

**Origem:** Auditoria – Campo Website só existe no wizard de criação (Baixa) (13/10)

**Critérios de aceitação:**
- A página de edição do clube tem todos os campos do assistente de criação, incluindo o website
- As alterações ficam guardadas e aparecem na página pública do clube

### E1F1U4 – Como administrador, quero criar um clube num só assistente, sem voltar a preencher os mesmos dados, para que o que introduzi não seja substituído.

**Origem:** Auditoria – Criação de clube tem dois assistentes que repetem os mesmos dados (Baixa)

**Critérios de aceitação:**
- Depois de "Clube criado com sucesso", não aparece um segundo assistente a pedir os mesmos dados
- Os dados introduzidos na criação (incluindo as datas da época) não são substituídos por valores por defeito

### E1F1U5 – Como administrador, quero que o assistente de IA e o formulário manual peçam os mesmos dados e tratem o criador da mesma forma, para que os clubes fiquem iguais seja qual for o caminho.

**Origem:** Auditoria – Assistente IA e wizard manual não pedem os mesmos dados na criação de clube (Baixa); Wizard manual e Assistente IA tratam de forma diferente o criador do clube (Média)

**Critérios de aceitação:**
- O assistente de IA pede os mesmos campos que o formulário manual (incluindo o NIF)
- Nos dois caminhos, quem cria o clube fica com o mesmo papel no clube
- Um clube criado pelo assistente de IA não fica sem membros

### E1F1U6 – Como administrador, quero que não possam existir dois clubes com o mesmo nome, para que os clubes não se confundam.

**Origem:** Auditoria – É possível criar dois clubes com o mesmo nome (Média)

**Critérios de aceitação:**
- Não é possível criar um clube com o nome de um clube que já existe
- Não é possível mudar o nome de um clube para o de outro que já existe
- O utilizador vê uma mensagem a dizer que o nome já está em uso

### E1F1U7 – Como administrador, quero que o botão "Gerar a partir do nome" gere o subdomínio a partir do nome do clube, para que faça o que diz.

**Origem:** Auditoria – Botão "Gerar a partir do nome" gera o subdomínio a partir da sigla (Baixa)

**Critérios de aceitação:**
- O botão gera o subdomínio a partir do nome do clube (ex.: "Clube Teste Admin" → "clube-teste-admin")
- Se esse subdomínio já existir, é sugerida uma variante (ex.: "-2")

---

## E1F2 – Épocas (criar, ativar e passar de época)

### E1F2U1 – Como dirigente, quero que a época proposta seja a atual e que as datas sejam validadas (fim depois do início), para que a época do clube esteja correta.

**Origem:** Auditoria – Época inicial por defeito no "Novo Clube" está desatualizada (Baixa); Época inicial aceita data de fim anterior à data de início (Média)

**Critérios de aceitação:**
- A época proposta por defeito é a que está a decorrer na data de criação
- Não é possível guardar uma época com a data de fim anterior à de início
- O nome da época corresponde às datas (ex.: 2026/2027 → 01/08/2026 a 30/06/2027)

---

## E1F3 – Escalões e equipas

### E1F3U1 – Como dirigente, quero gerir equipas e escalões sem erros, para que possa organizar os plantéis da época.

**Origem:** Auditoria – Página de Equipas não carrega (Alta); Escalão aceita ano mínimo maior que o máximo (Baixa)

**Critérios de aceitação:**
- A página de Equipas carrega a lista de equipas sem erros
- Não é possível criar um escalão com o ano mínimo maior que o máximo
- As equipas criadas aparecem na lista e podem ser editadas e apagadas

### E1F3U2 – Como dirigente, quero ver os escalões ordenados por idade, para que os encontre facilmente.

**Origem:** Auditoria – Escalões listados por ordem alfabética e não por idade (Baixa)

**Critérios de aceitação:**
- Os escalões aparecem do mais novo para o mais velho (ex.: Sub-8, Sub-10, …, Seniores)
- A ordem é a mesma em todas as listas onde os escalões aparecem

### E1F3U3 – Como dirigente, quero que os escalões propostos pelo assistente de IA não se sobreponham, para que cada atleta pertença a um só escalão.

**Origem:** Auditoria – Escalões sugeridos pelo Assistente IA sobrepõem-se (Baixa)

**Critérios de aceitação:**
- Nenhum ano de nascimento fica em dois escalões ao mesmo tempo
- Não é possível guardar escalões sobrepostos, sejam criados pela IA ou à mão

---

## E1F4 – Papéis dos utilizadores

### E1F4U1 – Como dirigente, quero atribuir o papel de Encarregado, para que os pais possam ter acesso à plataforma.

**Origem:** Enunciado do TFC (perfis dirigentes, atletas, pais); Auditoria – Encarregados referidos como membros, mas sem papel na plataforma (Média)

**Critérios de aceitação:**
- O papel "Encarregado" aparece na lista de papéis ao convidar ou atribuir
- Um utilizador com o papel Encarregado só consulta a informação do seu educando
- O papel aparece nos filtros de Utilizadores

### E1F4U2 – Como dirigente que também é treinador, quero acumular os dois papéis sem contornar as regras de segurança, para que num clube pequeno não seja preciso um segundo dirigente.

**Origem:** Auditoria – Dirigente não pode atribuir-se o papel de Treinador (Média) (13/10); Regra que impede atribuir papéis a si próprio pode ser contornada pelo pedido de adesão (Média)

**Critérios de aceitação:**
- Existe uma forma segura de um dirigente ficar também com o papel de treinador
- Não é possível um utilizador dar a si próprio papéis através de um pedido de adesão
- A recusa mostra uma mensagem clara, e não um código técnico

### E1F4U3 – Como dirigente que criou o clube, quero não poder ser removido nem despromovido por outro dirigente, para que não perca o controlo do clube.

**Origem:** Auditoria – Qualquer dirigente pode remover ou despromover o dirigente que criou o clube (Média)

**Critérios de aceitação:**
- O dirigente que criou o clube não pode ser removido nem despromovido por outros dirigentes
- O clube nunca fica sem nenhum dirigente

### E1F4U4 – Como dirigente, quero ver uma linha por pessoa na lista de utilizadores, com todos os seus papéis, para que não pareça haver pessoas repetidas.

**Origem:** Auditoria – Lista de utilizadores mostra uma linha por papel, parecendo pessoas duplicadas (Baixa)

**Critérios de aceitação:**
- Cada pessoa aparece numa só linha, com todos os seus papéis
- O contador da lista conta pessoas, e não papéis

### E1F4U5 – Como dirigente, quero confirmar antes de remover um papel, para que um clique por engano não tire o acesso a alguém.

**Origem:** Auditoria – Remover um papel de um utilizador não pede confirmação (Média)

**Critérios de aceitação:**
- Ao carregar em remover, aparece uma confirmação com o nome da pessoa e o papel
- O papel só é removido depois de confirmar

### E1F4U6 – Como dirigente, quero ser avisado quando atribuo um papel que a pessoa já tem, para que saiba que nada mudou.

**Origem:** Auditoria – Atribuir um papel que o utilizador já tem mostra mensagem de sucesso (Baixa)

**Critérios de aceitação:**
- Ao atribuir um papel que a pessoa já tem, aparece o aviso "Este utilizador já tem este papel"
- Não aparece a mensagem de sucesso

---

## E1F5 – Convites e importação de utilizadores

### E1F5U1 – Como dirigente, quero convidar outro dirigente, para que a gestão do clube não dependa de uma só pessoa.

**Origem:** Auditoria – Não é possível atribuir ou convidar o papel de Dirigente (Média)

**Critérios de aceitação:**
- É possível convidar um novo utilizador com o papel de Dirigente
- O convidado recebe o convite e, ao aceitá-lo, fica com o papel de Dirigente

### E1F5U2 – Como dirigente, quero que os convites mostrem o estado certo (pendente, expirado, aceite) e que os filtros funcionem, para que saiba que convites estão por aceitar.

**Origem:** Auditoria – Convites expirados aparecem no filtro "Pendente" e não no filtro "Expirado" (Baixa); Título "Convites pendentes" não muda com o filtro de estado (Baixa)

**Critérios de aceitação:**
- Um convite expirado aparece no filtro "Expirado" e não no "Pendente"
- O título da secção corresponde ao filtro escolhido (ou é genérico: "Convites")

### E1F5U3 – Como dirigente, quero que os avisos de validação só apareçam depois de submeter o formulário, para que não veja erros antes de preencher.

**Origem:** Auditoria – Aviso de validação aparece antes de submeter (Baixa) (13/10)

**Critérios de aceitação:**
- Ao abrir o formulário de convite, não aparecem avisos de erro
- O aviso "Selecione pelo menos um role" só aparece ao tentar submeter sem escolher papel

### E1F5U4 – Como dirigente, quero que a importação de papéis explique porque é que uma linha foi ignorada, para que possa corrigir o ficheiro.

**Origem:** Auditoria – Importação de roles não explica porque é que as linhas foram ignoradas (Baixa)

**Critérios de aceitação:**
- No fim da importação, cada linha ignorada mostra o motivo (ex.: "pessoa não encontrada", "sem permissão")
- Uma importação com 0 linhas importadas não aparece com o ícone de sucesso

---

## E1F6 – Pedidos de adesão ao clube

### E1F6U1 – Como visitante, quero que me seja pedido o login antes de enviar um pedido de adesão, para que o pedido não falhe em silêncio.

**Origem:** Auditoria – Pedido de adesão sem sessão iniciada falha em silêncio (Alta)

**Critérios de aceitação:**
- Sem sessão iniciada, "Pedir adesão" leva primeiro ao login
- Depois do login, o utilizador volta ao formulário com o clube já selecionado
- O botão "Enviar pedido" nunca fica sem resposta (sucesso ou erro)

### E1F6U2 – Como membro de um clube, quero não poder pedir adesão ao clube a que já pertenço, para que não se criem pedidos sem sentido.

**Origem:** Auditoria – Utilizador já membro de um clube consegue pedir adesão ao mesmo clube (Baixa)

**Critérios de aceitação:**
- Um membro não consegue enviar um pedido de adesão ao seu próprio clube
- Aparece a mensagem "Já é membro deste clube"

### E1F6U3 – Como dirigente, quero escolher a equipa ao aprovar um pedido de adesão, para que o atleta apareça logo no plantel certo.

**Origem:** Auditoria – Aprovar pedido de adesão não permite escolher a equipa (Média)

**Critérios de aceitação:**
- A janela "Aprovar pedido" permite escolher a equipa
- Depois de aprovado, o atleta aparece no plantel dessa equipa

### E1F6U4 – Como membro, quero que o botão "Entrar" na página pública do clube me leve a esse clube, para que não entre noutro clube por engano.

**Origem:** Auditoria – Botão "Entrar" na página pública de um clube abre outro clube (Média)

**Critérios de aceitação:**
- Um membro que entra pela página pública de um clube fica dentro desse clube
- Isto funciona mesmo que o membro pertença a vários clubes

### E1F6U5 – Como visitante que não é membro, quero que "Entrar" me proponha pedir adesão ao clube da página, para que não tenha de o procurar outra vez.

**Origem:** Melhoria – "Entrar" na página de um clube não propõe adesão a quem não é membro (Baixa)

**Critérios de aceitação:**
- Depois do login, um não-membro vê a opção "Pedir adesão a este clube"
- O formulário de adesão abre com esse clube já selecionado

### E1F6U6 – Como utilizador com pedido pendente, quero aceder ao meu perfil e aos meus pedidos, para que possa gerir a conta enquanto espero aprovação.

**Origem:** Melhoria – Utilizador sem clube aprovado só tem acesso ao ecrã de espera (Baixa)

**Critérios de aceitação:**
- Um utilizador sem clube aprovado consegue abrir o seu perfil
- Vê o estado dos seus pedidos e pode pedir adesão a outro clube
- Não tem acesso a dados de nenhum clube

### E1F6U7 – Como atleta, quero indicar a modalidade e o escalão quando peço adesão ao clube, para que o dirigente saiba logo em que equipa me deve colocar.

**Origem:** Melhoria – Pedido de adesão não pede modalidade nem escalão (Média)

**Critérios de aceitação:**
- O formulário de pedido de adesão pede a modalidade e o escalão (só os que o clube tem)
- O dirigente vê a modalidade e o escalão pedidos na lista de pedidos e ao aprovar
