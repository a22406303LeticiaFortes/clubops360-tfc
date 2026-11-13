# E7 – Gestão da Plataforma – User Stories

Área de administração da plataforma: clubes, planos, subscrições, Stripe, faturas, cupões, segurança, auditoria, suporte e site público.

**10 features · 32 user stories** (+ 1 técnica: E7TU1, ver `tech-user-stories.md`)

> Falhas marcadas com "(13/10)" foram encontradas nos testes de 13/10/2026.

---

## E7F1 – Gestão de clubes (criar, editar, apagar)

### E7F1U1 – Como administrador, quero que todos os clubes tenham um plano (Free por defeito) e um link de acesso, para que se saiba que limites se aplicam a cada clube.

**Origem:** Auditoria – Clubes podem existir sem plano atribuído (Média); Clubes podem ficar sem link de acesso (Baixa)

**Critérios de aceitação:**
- Um clube criado fica com o plano Free por defeito
- Todos os clubes têm um link de acesso
- Na lista de Clubes não aparece "Sem plano"

### E7F1U2 – Como administrador, quero que a sigla do clube seja validada, para que não fique vazia nem com valores errados.

**Origem:** Auditoria – Sigla do clube aceita valores inválidos ou vazios (Baixa)

**Critérios de aceitação:**
- A sigla é obrigatória e tem no máximo 10 caracteres
- O erro aparece no passo em que a sigla é preenchida

### E7F1U3 – Como administrador, quero entrar no meu clube depois do login e conseguir mudar de clube sempre, para que não faça alterações no clube errado.

**Origem:** Auditoria – Admin volta sempre a um clube de que não é membro ao atualizar a página e o seletor de clube pode ficar bloqueado (Média)

**Critérios de aceitação:**
- Depois do login ou de atualizar a página, o admin fica no último clube que escolheu
- O seletor de clube nunca fica bloqueado
- Criar um clube não muda o clube ativo sem o admin escolher

---

## E7F2 – Planos e limites aplicados de facto

### E7F2U1 – Como dirigente, quero ver os limites de cada plano antes de escolher, para que escolha o plano certo.

**Origem:** Auditoria – Planos na Subscrição não mostram os limites (Média)

**Critérios de aceitação:**
- Ao mudar de plano, cada opção mostra o número de equipas, modalidades e membros

### E7F2U2 – Como dirigente, quero ser avisado quando atinjo os limites do meu plano e que esses limites sejam aplicados, para que saiba quando tenho de mudar de plano.

**Origem:** Auditoria – Plano Free permite mais modalidades do que o limite (Alta)

**Critérios de aceitação:**
- Não é possível criar mais equipas, modalidades ou membros do que o plano permite
- Ao atingir o limite, o dirigente vê um aviso com a opção de mudar de plano

### E7F2U3 – Como administrador, quero que as funcionalidades de cada plano sejam aplicadas de facto, para que os planos pagos ofereçam mais do que o Free.

**Origem:** Auditoria – Funcionalidades dos planos não são aplicadas (são apenas texto descritivo) (Média)

**Critérios de aceitação:**
- Cada funcionalidade de um plano está ligada a uma permissão real
- Um clube só tem acesso às funcionalidades do seu plano

### E7F2U4 – Como dirigente, quero ver o preço do ciclo que escolhi (mensal ou anual), para que saiba quanto vou pagar.

**Origem:** Auditoria – Lista de planos confusa (Baixa) (13/10)

**Critérios de aceitação:**
- Com o ciclo "Anual" escolhido, os planos mostram o preço anual
- O plano Free não mostra opção de ciclo

---

## E7F3 – Subscrições

### E7F3U1 – Como dirigente, quero uma única secção de métodos de pagamento, para que saiba onde gerir a forma como pago.

**Origem:** Auditoria – Secções de pagamento duplicadas (Baixa)

**Critérios de aceitação:**
- Existe uma só secção para gerir os métodos de pagamento

### E7F3U2 – Como dirigente, quero que a página da subscrição mostre só as ações que se aplicam ao meu plano e que funcionam, para que não me confunda.

**Origem:** Auditoria – Plano Free com renovação e cancelamento (Baixa); Ferramenta interna de testes de notificações visível ao dirigente (Baixa); Botão "Confirmar" da janela de subscrição não tem efeito (Baixa)

**Critérios de aceitação:**
- O plano Free não mostra renovação nem cancelamento
- A ferramenta interna de testes não aparece ao dirigente
- Todos os botões da janela de subscrição têm uma ação

### E7F3U3 – Como dirigente, quero que uma subscrição cancelada mostre a data em que termina e me deixe passar para o Free, para que não fique preso num plano pago.

**Origem:** Auditoria – Subscrição cancelada continua a indicar "Próxima renovação" (Média); Impossível mudar para o plano Free (Média) (13/10)

**Critérios de aceitação:**
- Uma subscrição cancelada mostra "Termina a …" em vez de "Próxima renovação"
- É possível passar para o Free depois de cancelar, sem erro
- Na data de fim, o clube passa para o Free

### E7F3U4 – Como dirigente, quero ver no histórico todas as mudanças da minha subscrição, para que saiba o que mudou e quando.

**Origem:** Auditoria – Histórico da subscrição vazio (Baixa) (13/10)

**Critérios de aceitação:**
- Cada mudança de plano, cancelamento ou reativação aparece no histórico, com a data
- O histórico nunca fica vazio depois de uma mudança

---

## E7F4 – Ligação à Stripe

### E7F4U1 – Como administrador, quero que os preços e as subscrições da plataforma coincidam com os da Stripe, para que os clubes paguem o valor anunciado.

**Origem:** Auditoria – Preços dos planos Pro e Enterprise na plataforma não coincidem com os preços na Stripe (Alta)

**Critérios de aceitação:**
- Alterar o preço de um plano atualiza o preço na Stripe
- A verificação do clube não mostra preços divergentes
- As subscrições atribuídas pelo admin existem também na Stripe

### E7F4U2 – Como administrador, quero que o teste da ligação à Stripe explique o problema que encontra, para que o possa resolver.

**Origem:** Auditoria – Teste da conta Stripe indica "Problema" sem explicar a causa (Média)

**Critérios de aceitação:**
- Quando o teste devolve "Problema", indica qual é e como resolver
- Os campos da conta (ex.: pagamentos permitidos) mostram o valor real, e não "?"

---

## E7F5 – Faturas e pagamentos

### E7F5U1 – Como administrador, quero que as subscrições pagas gerem faturas, para que cada cobrança fique registada.

**Origem:** Auditoria – Subscrições pagas não geram faturas (Média)

**Critérios de aceitação:**
- Cada período de uma subscrição paga gera uma fatura
- A fatura aparece em Faturas e na conta do clube

### E7F5U2 – Como administrador, quero que faturas e pagamentos só aceitem valores e datas possíveis e que o pagamento seja comparado com o total da fatura, para que as contas da plataforma estejam certas.

**Origem:** Auditoria – Faturas aceitam valores e datas impossíveis (total negativo) (Alta); Pagamentos aceitam valores negativos e ficam logo "Concluídos" (Alta); Um pagamento de qualquer valor marca a fatura como totalmente paga (Alta); Valor do pagamento não é verificado contra o total da fatura (Alta)

**Critérios de aceitação:**
- Não é possível criar faturas com subtotal negativo, desconto maior que o subtotal ou IVA acima de 100%
- O fim do período e o vencimento não podem ser anteriores ao início e à emissão
- Não é possível registar pagamentos negativos
- Uma fatura só fica "Paga" quando os pagamentos somam o total; um pagamento a mais é recusado ou avisado

### E7F5U3 – Como administrador, quero que marcar uma fatura como paga crie o pagamento correspondente e que as faturas anuladas não contem nos totais, para que faturas e pagamentos batam certo.

**Origem:** Auditoria – Marcar uma fatura como paga não cria o pagamento correspondente (Média); Faturas anuladas continuam a contar no "Total emitido" (Média)

**Critérios de aceitação:**
- Marcar uma fatura como paga cria o pagamento em Pagamentos
- As faturas anuladas não contam no "Total emitido"
- O total pago em Faturas é igual ao total concluído em Pagamentos

### E7F5U4 – Como administrador, quero confirmar e poder corrigir as alterações ao estado de uma fatura, para que um clique por engano tenha volta.

**Origem:** Auditoria – Ações das faturas não pedem confirmação e uma fatura "Falhada" ou "Paga" não pode ser corrigida nem anulada (Média)

**Critérios de aceitação:**
- Marcar como paga, falhada ou anulada pede confirmação
- Uma fatura "Falhada" ou "Paga" pode ser corrigida ou anulada, ficando registado quem o fez

### E7F5U5 – Como dirigente, quero receber as faturas em PDF com os dados fiscais do clube e da plataforma, para que sejam documentos válidos.

**Origem:** Auditoria – Faturas não têm PDF nem dados fiscais do cliente e do emitente (Média)

**Critérios de aceitação:**
- Cada fatura pode ser descarregada em PDF
- O PDF tem o NIF e a morada do clube e os dados de quem emite
- (A validar com o orientador: emissão por software certificado pela AT)

---

## E7F6 – Cupões

### E7F6U1 – Como administrador, quero que os cupões só aceitem valores possíveis e mostrem o estado certo, para que nenhum desconto seja aplicado por engano.

**Origem:** Auditoria – Cupões aceitam valores impossíveis e cupões expirados aparecem como "Ativo" (Média)

**Critérios de aceitação:**
- O desconto em percentagem não pode passar de 100%
- A duração e o limite de usos não podem ser negativos
- Um cupão expirado aparece como "Expirado"
- Ao recusar um cupão, o utilizador vê o motivo
- Um código repetido mostra uma mensagem clara, e não o erro da base de dados

---

## E7F7 – Segurança de contas (bloqueio, papéis de plataforma)

### E7F7U1 – Como administrador, quero que um utilizador bloqueado não consiga fazer login, para que quem não deve ter acesso não veja os dados do clube.

**Origem:** Auditoria – Utilizador bloqueado continua a conseguir fazer login e aceder à plataforma (Alta)

**Critérios de aceitação:**
- Um utilizador bloqueado não consegue fazer login
- Ao bloquear, as sessões abertas desse utilizador terminam
- O utilizador vê uma mensagem a dizer que a conta está bloqueada

### E7F7U2 – Como administrador, quero que os papéis de plataforma não fiquem duplicados, para que se saiba quem tem cada permissão.

**Origem:** Auditoria – Papel de plataforma atribuído em duplicado ao mesmo utilizador (Média)

**Critérios de aceitação:**
- Não é possível atribuir o mesmo papel de plataforma duas vezes à mesma pessoa
- Os papéis duplicados que já existem são limpos

### E7F7U3 – Como membro, quero só ver as páginas e os botões que tenho permissão para usar, mesmo pelo link direto, para que não tente fazer ações que me são negadas.

**Origem:** Auditoria – Página de Administração do clube acessível a qualquer membro através do link direto (Baixa); Jogador vê e pode preencher formulários de criação que não tem permissão para submeter (Baixa)

**Critérios de aceitação:**
- Um jogador que abre a página de Administração pelo link é redirecionado ou vê "Sem permissão"
- Os botões de criar jogos e treinos não aparecem a quem não pode usá-los

---

## E7F8 – Auditoria

### E7F8U1 – Como administrador, quero que todas as ações fiquem na auditoria, incluindo faturas, pagamentos e cupões, para que se saiba quem fez cada alteração.

**Origem:** Auditoria – Ações sobre faturas, pagamentos e cupões não ficam registadas na auditoria (Alta)

**Critérios de aceitação:**
- Criar, alterar ou anular faturas, pagamentos e cupões fica registado na auditoria
- Cada registo indica quem fez, o quê e quando

### E7F8U2 – Como administrador, quero que cada ação apareça uma só vez, com um nome e detalhes legíveis, para que a auditoria seja fácil de ler.

**Origem:** Auditoria – Auditoria regista a mesma ação duas vezes com nomes diferentes (Baixa); Detalhes da auditoria mostram "[object Object]" em vez da informação (Baixa)

**Critérios de aceitação:**
- Cada ação gera um só registo
- Os nomes das ações estão em português e sem termos técnicos
- A coluna Detalhes mostra a informação, e nunca "[object Object]"

### E7F8U3 – Como administrador, quero que as ações feitas pelo assistente de IA registem o utilizador que as pediu, para que se saiba sempre quem fez o quê.

**Origem:** Auditoria – Ações feitas pelo Assistente IA ficam registadas com o utilizador "00000000" (Média)

**Critérios de aceitação:**
- As ações feitas pelo assistente de IA ficam registadas com o nome de quem as pediu
- Não aparece o utilizador "00000000"

---

## E7F9 – Suporte e tickets

### E7F9U1 – Como administrador, quero atribuir um ticket a um responsável, para que se saiba quem o está a tratar.

**Origem:** Auditoria – Não é possível atribuir tickets a nenhum responsável (Média)

**Critérios de aceitação:**
- A lista "Atribuir a" mostra os administradores da plataforma
- O responsável escolhido aparece no ticket e na lista de tickets

### E7F9U2 – Como administrador, quero ver o nome de quem abriu e respondeu a cada ticket, para que possa contactar a pessoa.

**Origem:** Auditoria – Autor dos tickets aparece como ID técnico ou vazio em vez do nome (Baixa)

**Critérios de aceitação:**
- A lista e o detalhe do ticket mostram o nome do autor
- As respostas mostram o nome de quem respondeu, e não um ID

### E7F9U3 – Como administrador, quero que as mudanças de estado fiquem no histórico do ticket, para que se saiba quem mudou o quê e quando.

**Origem:** Auditoria – Mudanças de estado dos tickets não ficam no histórico (Baixa)

**Critérios de aceitação:**
- Cada mudança de estado, prioridade ou responsável aparece no histórico, com a data e quem fez
- O contador do histórico conta todos os eventos

### E7F9U4 – Como utilizador, quero consultar os meus tickets e ler as respostas, para que saiba em que ponto está o meu pedido.

**Origem:** Auditoria – Utilizador não consegue consultar os seus tickets nem ler as respostas (Média)

**Critérios de aceitação:**
- Existe uma área "Os meus pedidos" com os tickets do utilizador
- A notificação de nova resposta abre o ticket
- O utilizador vê as respostas, mas não as notas internas

### E7F9U5 – Como utilizador, quero que o botão "Reportar / Pedir" não tape a navegação das listas, para que consiga mudar de página.

**Origem:** Auditoria – Botão "Reportar / Pedir" tapa a navegação entre páginas das listas (Baixa)

**Critérios de aceitação:**
- O botão "Reportar / Pedir" não fica por cima da paginação nem de outros botões

---

## E7F10 – Site público, demo e manual

### E7F10U1 – Como visitante, quero entrar na conta demo, para que conheça a plataforma antes de aderir.

**Origem:** Auditoria – Login na conta demo falha (Alta); Erro técnico mostrado ao utilizador (Baixa)

**Critérios de aceitação:**
- "Entrar na conta demo" entra na plataforma sem erro
- Se a demo estiver indisponível, aparece uma mensagem clara, e não um erro técnico

### E7F10U2 – Como visitante, quero exportar o manual em PDF com o conteúdo completo, para que o possa consultar fora da plataforma.

**Origem:** Auditoria – Exportar PDF do manual gera documento em branco (Média)

**Critérios de aceitação:**
- O PDF exportado tem o texto e as imagens do manual
- O PDF tem todas as secções, e não só uma página

> A user story técnica desta feature (E7TU1 – páginas internas do manual não públicas) está em `tech-user-stories.md`.
