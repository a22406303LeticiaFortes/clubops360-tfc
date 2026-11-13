# User Stories Técnicas

User stories que não são vistas diretamente pelos utilizadores, mas que são necessárias para a plataforma ser segura, fiável e testável.

**4 user stories técnicas**

| Código | Feature | Resumo |
|---|---|---|
| E7TU1 | E7F10 – Site público, demo e manual | Páginas internas do manual não públicas |
| E8TU1 | E8F1 – Validação de dados em todos os formulários e na base de dados | Validação na interface e na base de dados |
| E8TU2 | E8F2 – Registo de erros e mensagens claras ao utilizador | Registo de erros e mensagens claras |
| E8TU3 | E8F4 – Ambiente de testes separado (incluindo Stripe em modo de teste) | Ambiente de testes com a Stripe em modo de teste |

---

### E7TU1 – Como plataforma, preciso que as páginas internas do manual não sejam públicas, para que ferramentas internas não fiquem expostas.

**Feature:** E7F10 – Site público, demo e manual

**Origem:** Auditoria – Páginas internas do manual visíveis ao público (Média)

**Critérios de aceitação:**
- As páginas "Validação" e "Imagens pendentes" só abrem para administradores
- Um visitante sem sessão que abra estes links não vê o conteúdo

---

### E8TU1 – Como plataforma, preciso que todos os formulários validem os dados na interface e na base de dados, para que nunca sejam guardados dados inválidos.

**Feature:** E8F1 – Validação de dados em todos os formulários e na base de dados

**Origem:** Auditoria – falhas de validação em vários formulários (Wizard, Local, Espaço, Escalão, Ficha do jogador, Consentimento, duração negativa, disponibilidades, regras de calendário, faturas, pagamentos, cupões)

**Critérios de aceitação:**
- Cada formulário valida os dados antes de enviar
- A base de dados recusa dados inválidos, mesmo que a interface falhe
- O utilizador vê qual é o campo errado e porquê

---

### E8TU2 – Como plataforma, preciso que os erros do servidor fiquem registados e sejam mostrados ao utilizador com mensagens claras, para que as falhas sejam detetadas rapidamente.

**Feature:** E8F2 – Registo de erros e mensagens claras ao utilizador

**Origem:** Auditoria – Login na conta demo falha (Alta); Erro técnico mostrado ao utilizador (Baixa); Página de Equipas não carrega (Alta); Erro na edição de um clube diz "Não foi possível criar o clube" (Baixa)

**Critérios de aceitação:**
- Nenhum erro técnico (códigos, mensagens da base de dados) aparece ao utilizador
- As mensagens de erro dizem o que aconteceu e o que fazer
- Os erros ficam registados para a equipa os analisar

---

### E8TU3 – Como equipa de desenvolvimento, precisamos de um ambiente de testes separado, com a Stripe em modo de teste, para que os testes não afetem clubes nem pagamentos reais.

**Feature:** E8F4 – Ambiente de testes separado (incluindo Stripe em modo de teste)

**Origem:** Auditoria – Stripe em modo real (live) e sandbox nunca sincronizado (nota da área de administração); dados de teste não apagáveis (faturas e pagamentos)

**Critérios de aceitação:**
- Existe um ambiente de testes separado do ambiente real
- No ambiente de testes, a Stripe está em modo de teste
- Os dados criados nos testes não aparecem no ambiente real
