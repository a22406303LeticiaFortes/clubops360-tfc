# E8 – Qualidade e Fiabilidade da Plataforma – User Stories

Validação de dados, mensagens de erro, traduções, ambiente de testes e atualização dos dados.

**5 features · 4 user stories** (+ 3 técnicas: E8TU1, E8TU2, E8TU3, ver `tech-user-stories.md`)

> Falhas marcadas com "(13/10)" foram encontradas nos testes de 13/10/2026.

---

## E8F1 – Validação de dados em todos os formulários e na base de dados

> Esta feature só tem uma user story técnica: **E8TU1** (ver `tech-user-stories.md`).

---

## E8F2 – Registo de erros e mensagens claras ao utilizador

> A user story técnica desta feature (**E8TU2** – erros do servidor registados e mensagens claras) está em `tech-user-stories.md`.

### E8F2U2 – Como utilizador, quero que a mensagem de sucesso só apareça quando a alteração foi mesmo guardada, para que saiba se o que fiz ficou registado.

**Origem:** Auditoria – Mensagem de sucesso aparece mesmo quando a alteração é bloqueada (Média); Mensagem "Presença guardada" enganadora (Média) (13/10)

**Critérios de aceitação:**
- A mensagem de sucesso só aparece depois de confirmar que a alteração foi guardada
- Se a alteração for bloqueada, aparece uma mensagem de erro

### E8F2U3 – Como utilizador, quero que as mensagens do assistente de IA apareçam formatadas, sem asteriscos nem símbolos, para que sejam fáceis de ler.

**Origem:** Auditoria – Mensagens do Assistente IA mostram a formatação em bruto (asteriscos) (Baixa)

**Critérios de aceitação:**
- Os negritos, listas e tabelas das respostas da IA aparecem formatados
- Não aparecem asteriscos nem símbolos de tabela no texto

---

## E8F3 – Traduções completas (sem textos técnicos ou em inglês)

### E8F3U1 – Como utilizador, quero que todos os textos, estados e erros apareçam no idioma escolhido e sem nomes técnicos, para que perceba o que a plataforma me diz.

**Origem:** Auditoria – Estado das reservas aparece em inglês (Baixa); Textos da área de administração em inglês (Baixa); Funções no "Aprovar pedido" aparecem com o nome técnico (Baixa); Botão de cancelar no "Aprovar pedido" tem o texto "Todos" (Baixa); Traduções incompletas na demo (Baixa) (13/10); Texto em inglês na ficha do jogador (Baixa) (13/10)

**Critérios de aceitação:**
- Todos os textos, estados e mensagens aparecem no idioma escolhido
- Os papéis e estados aparecem com nomes legíveis (ex.: "Treinador Principal", e não "treinador_principal")
- Os botões têm o texto certo (ex.: "Cancelar", e não "Todos")

---

## E8F4 – Ambiente de testes separado (incluindo Stripe em modo de teste)

> Esta feature só tem uma user story técnica: **E8TU3** (ver `tech-user-stories.md`).

---

## E8F5 – Atualização das listas sem precisar de refresh

### E8F5U1 – Como utilizador, quero que as listas e os indicadores se atualizem depois de uma alteração e ao mudar de clube, para que não precise de recarregar a página nem veja dados de outro clube.

**Origem:** Auditoria – Listas não atualizam após alterações, só depois de atualizar a página (Baixa); Escalão novo não aparece sem refresh (Baixa) (13/10); Após mudar de clube, a página de Épocas mostra dados do clube anterior até atualizar (Média)

**Critérios de aceitação:**
- Depois de criar, editar ou aprovar algo, a lista mostra a alteração sem recarregar a página
- Os indicadores do Dashboard atualizam depois de mudar de papel
- Ao mudar de clube, todas as páginas mostram logo os dados do clube novo
