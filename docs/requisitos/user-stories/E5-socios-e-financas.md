# E5 – Sócios e Finanças – User Stories

Sócios, quotas, pagamentos ao clube e receitas/despesas.

**4 features · 8 user stories**

> Este épico ainda não existe na plataforma. Os requisitos vêm do enunciado do TFC e da análise da concorrência.

---

## E5F1 – Sócios (uma ficha por pessoa, independente da modalidade)

### E5F1U1 – Como dirigente, quero registar os sócios do clube, para que saiba quem pertence ao clube além dos atletas.

**Origem:** Sobre o TFC – gestão de sócios e quotas; objetivo do orientador (100% das necessidades)

**Critérios de aceitação:**
- É possível criar, editar e desativar sócios
- Cada sócio tem número de sócio, dados de contacto e tipo de sócio

### E5F1U2 – Como dirigente, quero que cada sócio tenha uma só ficha no clube, mesmo que esteja em várias modalidades, para que não haja dados repetidos.

**Origem:** Concorrência – ClubePT ("um sócio é do clube, não da modalidade")

**Critérios de aceitação:**
- Uma pessoa tem uma só ficha de sócio, mesmo ligada a várias modalidades
- Não é possível criar dois sócios para a mesma pessoa

---

## E5F2 – Quotas e mensalidades por tipo de sócio e modalidade

### E5F2U1 – Como dirigente, quero definir o valor das quotas por tipo de sócio, para que cada sócio pague o valor correto.

**Origem:** Sobre o TFC – gestão de sócios e quotas

**Critérios de aceitação:**
- É possível definir tipos de sócio com valor e periodicidade da quota
- Cada sócio paga o valor do seu tipo

### E5F2U2 – Como dirigente, quero ver que sócios têm quotas em atraso, para que os possa contactar.

**Origem:** Sobre o TFC – gestão de sócios e quotas

**Critérios de aceitação:**
- Existe uma lista ou filtro de sócios com quotas em atraso
- Para cada sócio é indicado o valor e o período em atraso

### E5F2U3 – Como encarregado, quero ver as quotas em dívida do meu educando, para que saiba o que tenho de pagar.

**Origem:** Sobre o TFC – gestão de quotas e pagamentos

**Critérios de aceitação:**
- O encarregado vê as quotas pagas e em dívida do educando
- Não vê as quotas de outros atletas

---

## E5F3 – Pagamentos ao clube (MB Way, Multibanco, cartão)

### E5F3U1 – Como sócio ou encarregado, quero pagar as quotas pela app (MB Way, Multibanco ou cartão), para que não tenha de pagar em mão.

**Origem:** Concorrência – ClubePT e Adjunto aceitam MB Way e Multibanco; Spond e 360Player aceitam pagamentos na app

**Critérios de aceitação:**
- É possível pagar uma quota por MB Way, referência Multibanco ou cartão
- Depois do pagamento, a quota passa a "Paga" automaticamente

### E5F3U2 – Como sócio ou encarregado, quero receber o recibo automaticamente depois de pagar, para que tenha comprovativo.

**Origem:** Concorrência – Adjunto envia recibos automáticos; ClubePT emite faturas automáticas

**Critérios de aceitação:**
- Depois de cada pagamento é gerado um recibo
- O recibo fica disponível na conta de quem pagou

---

## E5F4 – Receitas e despesas do clube

### E5F4U1 – Como dirigente, quero registar as receitas e despesas do clube, para que saiba quanto o clube tem.

**Origem:** Concorrência – EMJOGO, Adjunto e ClubePT têm gestão financeira

**Critérios de aceitação:**
- É possível registar receitas e despesas, com data, valor e categoria
- As quotas pagas entram automaticamente nas receitas
- O dirigente vê o saldo do clube
