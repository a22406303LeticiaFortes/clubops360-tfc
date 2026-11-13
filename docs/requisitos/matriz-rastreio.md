# Matriz de Rastreio

Liga cada falha da auditoria (e cada requisito de outras fontes) à user story que a resolve. Serve para garantir que nenhuma falha ficou sem resposta e que todas as user stories têm uma origem.

## Resumo

| | Total |
|---|---|
| Falhas da auditoria ligadas a user stories | 117 (18 Alta · 44 Média · 55 Baixa) |
| Melhorias propostas | 3 |
| Requisitos de outras fontes (enunciado, concorrência, decisões do grupo) | ver secção 2 |
| Falhas sem user story | 0 |
| Falhas excluídas por decisão do grupo | 1 (ver secção 3) |

Notas:
- Uma falha pode dar origem a mais do que uma user story, e uma user story pode resolver várias falhas.
- *(13/10)* – falha encontrada nos testes de 13/10/2026.
- A user story técnica **E8TU1** (validação na interface e na base de dados) cobre de forma transversal todas as falhas de validação de dados (ex.: n.º 1, 2, 11, 13, 35, 41, 48, 52–56, 81, 82 e 89).
- A descrição completa de cada falha (passos, evidências, o que devia acontecer) está no Notion ("Auditoria – Falhas") e em `docs/auditoria/`.

---

## 1. Falhas da auditoria → User stories

### E1 – Estrutura do Clube

| # | Falha | Gravidade | User story |
|---|---|---|---|
| 1 | Wizard aceita email e website inválidos | Baixa | E1F1U1 |
| 2 | Criação de clube aceita telefone, NIF, morada inválidos | Baixa | E1F1U1 |
| 3 | Validação dos dados do clube só acontece no último passo da criação | Baixa | E1F1U2 |
| 4 | Campo Website só existe no wizard de criação *(13/10)* | Baixa | E1F1U3 |
| 5 | Criação de clube tem dois assistentes que repetem os mesmos dados | Baixa | E1F1U4 |
| 6 | Assistente IA e wizard manual não pedem os mesmos dados na criação de clube | Baixa | E1F1U5 |
| 7 | Wizard manual e Assistente IA tratam de forma diferente o criador do clube | Média | E1F1U5 |
| 8 | É possível criar dois clubes com o mesmo nome | Média | E1F1U6 |
| 9 | Botão "Gerar a partir do nome" gera o subdomínio a partir da sigla | Baixa | E1F1U7 |
| 10 | Época inicial por defeito no "Novo Clube" está desatualizada | Baixa | E1F2U1 |
| 11 | Época inicial aceita data de fim anterior à data de início | Média | E1F2U1 |
| 12 | Página de Equipas não carrega | Alta | E1F3U1, E8TU2 |
| 13 | Escalão aceita ano mínimo maior que o máximo | Baixa | E1F3U1 |
| 14 | Escalões listados por ordem alfabética e não por idade | Baixa | E1F3U2 |
| 15 | Escalões sugeridos pelo Assistente IA sobrepõem-se | Baixa | E1F3U3 |
| 16 | Encarregados referidos como membros, mas sem papel na plataforma | Média | E1F4U1, E2F2U1, E2F2U6 |
| 17 | Dirigente não pode atribuir-se o papel de Treinador *(13/10)* | Média | E1F4U2 |
| 18 | Regra que impede atribuir papéis a si próprio pode ser contornada pelo pedido de adesão | Média | E1F4U2 |
| 19 | Qualquer dirigente pode remover ou despromover o dirigente que criou o clube | Média | E1F4U3 |
| 20 | Lista de utilizadores mostra uma linha por papel, parecendo pessoas duplicadas | Baixa | E1F4U4 |
| 21 | Remover um papel de um utilizador não pede confirmação | Média | E1F4U5 |
| 22 | Atribuir um papel que o utilizador já tem mostra mensagem de sucesso | Baixa | E1F4U6 |
| 23 | Não é possível atribuir ou convidar o papel de Dirigente | Média | E1F5U1 |
| 24 | Convites expirados aparecem no filtro "Pendente" e não no filtro "Expirado" | Baixa | E1F5U2 |
| 25 | Título "Convites pendentes" não muda com o filtro de estado | Baixa | E1F5U2 |
| 26 | Aviso de validação aparece antes de submeter *(13/10)* | Baixa | E1F5U3 |
| 27 | Importação de roles não explica porque é que as linhas foram ignoradas | Baixa | E1F5U4 |
| 28 | Pedido de adesão sem sessão iniciada falha em silêncio | Alta | E1F6U1 |
| 29 | Utilizador já membro de um clube consegue pedir adesão ao mesmo clube | Baixa | E1F6U2 |
| 30 | Aprovar pedido de adesão não permite escolher a equipa | Média | E1F6U3 |
| 31 | Botão "Entrar" na página pública de um clube abre outro clube | Média | E1F6U4 |
| 32 | "Entrar" na página de um clube não propõe adesão a quem não é membro *(melhoria)* | Baixa | E1F6U5 |
| 33 | Utilizador sem clube aprovado só tem acesso ao ecrã de espera *(melhoria)* | Baixa | E1F6U6 |
| 34 | Pedido de adesão não pede modalidade nem escalão *(melhoria)* | Média | E1F6U7 |

### E2 – Atletas e Plantel

| # | Falha | Gravidade | User story |
|---|---|---|---|
| 35 | Ficha do jogador aceita dados físicos e data de nascimento impossíveis | Média | E2F1U1, E2F2U5 |
| 36 | Altura média apresentada com a unidade errada | Baixa | E2F1U1 |
| 37 | Estatísticas com idade negativa *(13/10)* | Baixa | E2F1U1 |
| 38 | Não é possível adicionar ao plantel um utilizador que já é membro do clube | Alta | E2F1U2 |
| 39 | Dois campos de posição diferentes geram dados incoerentes | Média | E2F1U3 |
| 40 | Importação de jogadores sem modelo de ficheiro | Baixa | E2F1U4 |
| 41 | Consentimento parental aceita email inválido | Média | E2F3U1, E2F3U2 |
| 42 | Consentimento parental "Válido" com email inválido *(13/10)* | Média | E2F3U2 |

### E3 – Treinos

| # | Falha | Gravidade | User story |
|---|---|---|---|
| 43 | Impossível criar exercícios na biblioteca *(13/10)* | Alta | E3F1U1 |
| 44 | Exercícios adicionados a um treino não ficam guardados | Alta | E3F2U1 |
| 45 | Plano de Treino guardado não pode ser consultado nem editado | Alta | E3F2U2 |
| 46 | Plano de Treino não usa a biblioteca de exercícios | Média | E3F2U3 |
| 47 | Plano de Treino e Treino funcionam em separado, com informação duplicada | Média | E3F2U4, E3F3U4 |
| 48 | Plano de Treino aceita duração negativa nos exercícios | Baixa | E3F2U5 |
| 49 | "Volume (min)" do Plano de Treino não é calculado *(13/10)* | Baixa | E3F2U5 |
| 50 | Editar um treino altera o horário em +1 hora | Alta | E3F3U1 |
| 51 | Uma regra com horário inválido bloqueia a geração de todos os treinos | Alta | E3F3U2 |
| 52 | Regras de calendário sem validação de horários, disponibilidade e duplicados | Média | E3F3U3 |
| 53 | Disponibilidades e reservas aceitam horários impossíveis e duplicados | Baixa | E3F4U1 |
| 54 | Reservas não respeitam a disponibilidade do espaço *(13/10)* | Média | E3F4U1 |
| 55 | Local aceita email e telefone inválidos | Baixa | E3F4U2 |
| 56 | Espaço aceita capacidade negativa ou zero | Baixa | E3F4U2 |
| 57 | Gestão de slots de disponibilidade pouco prática | Baixa | E3F4U3 |
| 58 | Presenças mostram o jogador como "Sem nome" e não podem ser guardadas | Alta | E3F5U1 |
| 59 | Mensagem "Presença guardada" enganadora *(13/10)* | Média | E3F5U1, E8F2U2 |
| 60 | Botões de presenças incoerentes *(13/10)* | Baixa | E3F5U2 |

### E4 – Jogos e Competições

| # | Falha | Gravidade | User story |
|---|---|---|---|
| 61 | Criar Jogo pede equipa mas o formulário não tem esse campo | Baixa | E4F1U1 |

### E6 – Comunicação

| # | Falha | Gravidade | User story |
|---|---|---|---|
| 62 | Notificações por email ativas, mas não funcionam | Média | E6F1U1, E6F1U2 |

### E7 – Gestão da Plataforma

| # | Falha | Gravidade | User story |
|---|---|---|---|
| 63 | Clubes podem existir sem plano atribuído | Média | E7F1U1 |
| 64 | Clubes podem ficar sem link de acesso | Baixa | E7F1U1 |
| 65 | Sigla do clube aceita valores inválidos ou vazios | Baixa | E7F1U2 |
| 66 | Admin volta sempre a um clube de que não é membro ao atualizar a página e o seletor de clube pode ficar bloqueado | Média | E7F1U3 |
| 67 | Planos na Subscrição não mostram os limites | Média | E7F2U1 |
| 68 | Plano Free permite mais modalidades do que o limite | Alta | E7F2U2 |
| 69 | Funcionalidades dos planos não são aplicadas (são apenas texto descritivo) | Média | E7F2U3 |
| 70 | Lista de planos confusa *(13/10)* | Baixa | E7F2U4 |
| 71 | Secções de pagamento duplicadas | Baixa | E7F3U1 |
| 72 | Plano Free com renovação e cancelamento | Baixa | E7F3U2 |
| 73 | Ferramenta interna de testes de notificações visível ao dirigente | Baixa | E7F3U2 |
| 74 | Botão "Confirmar" da janela de subscrição não tem efeito | Baixa | E7F3U2 |
| 75 | Subscrição cancelada continua a indicar "Próxima renovação" | Média | E7F3U3 |
| 76 | Impossível mudar para o plano Free *(13/10)* | Média | E7F3U3 |
| 77 | Histórico da subscrição vazio *(13/10)* | Baixa | E7F3U4 |
| 78 | Preços dos planos Pro e Enterprise na plataforma não coincidem com os preços na Stripe | Alta | E7F4U1 |
| 79 | Teste da conta Stripe indica "Problema" sem explicar a causa | Média | E7F4U2 |
| 80 | Subscrições pagas não geram faturas | Média | E7F5U1 |
| 81 | Faturas aceitam valores e datas impossíveis (total negativo) | Alta | E7F5U2 |
| 82 | Pagamentos aceitam valores negativos e ficam logo "Concluídos" | Alta | E7F5U2 |
| 83 | Um pagamento de qualquer valor marca a fatura como totalmente paga | Alta | E7F5U2 |
| 84 | Valor do pagamento não é verificado contra o total da fatura | Alta | E7F5U2 |
| 85 | Marcar uma fatura como paga não cria o pagamento correspondente | Média | E7F5U3 |
| 86 | Faturas anuladas continuam a contar no "Total emitido" | Média | E7F5U3 |
| 87 | Ações das faturas não pedem confirmação e uma fatura "Falhada" ou "Paga" não pode ser corrigida nem anulada | Média | E7F5U4 |
| 88 | Faturas não têm PDF nem dados fiscais do cliente e do emitente | Média | E7F5U5 |
| 89 | Cupões aceitam valores impossíveis e cupões expirados aparecem como "Ativo" | Média | E7F6U1 |
| 90 | Utilizador bloqueado continua a conseguir fazer login e aceder à plataforma | Alta | E7F7U1 |
| 91 | Papel de plataforma atribuído em duplicado ao mesmo utilizador | Média | E7F7U2 |
| 92 | Página de Administração do clube acessível a qualquer membro através do link direto | Baixa | E7F7U3 |
| 93 | Jogador vê e pode preencher formulários de criação que não tem permissão para submeter | Baixa | E7F7U3 |
| 94 | Jogador vê o mesmo menu que o Dirigente | Média | E7F7U3 |
| 95 | Jogador vê todas as modalidades do clube no seletor | Média | E7F7U3 |
| 96 | Ações sobre faturas, pagamentos e cupões não ficam registadas na auditoria | Alta | E7F8U1 |
| 97 | Auditoria regista a mesma ação duas vezes com nomes diferentes | Baixa | E7F8U2 |
| 98 | Detalhes da auditoria mostram "[object Object]" em vez da informação | Baixa | E7F8U2 |
| 99 | Ações feitas pelo Assistente IA ficam registadas com o utilizador "00000000" | Média | E7F8U3 |
| 100 | Não é possível atribuir tickets a nenhum responsável | Média | E7F9U1 |
| 101 | Autor dos tickets aparece como ID técnico ou vazio em vez do nome | Baixa | E7F9U2 |
| 102 | Mudanças de estado dos tickets não ficam no histórico | Baixa | E7F9U3 |
| 103 | Utilizador não consegue consultar os seus tickets nem ler as respostas | Média | E7F9U4 |
| 104 | Botão "Reportar / Pedir" tapa a navegação entre páginas das listas | Baixa | E7F9U5 |
| 105 | Login na conta demo falha | Alta | E7F10U1, E8TU2 |
| 106 | Erro técnico mostrado ao utilizador | Baixa | E7F10U1, E8TU2 |
| 107 | Exportar PDF do manual gera documento em branco | Média | E7F10U2 |
| 108 | Páginas internas do manual visíveis ao público | Média | E7TU1 |

### E8 – Qualidade e Fiabilidade da Plataforma

| # | Falha | Gravidade | User story |
|---|---|---|---|
| 109 | Erro na edição de um clube diz "Não foi possível criar o clube" | Baixa | E8TU2 |
| 110 | Mensagem de sucesso aparece mesmo quando a alteração é bloqueada | Média | E8F2U2 |
| 111 | Mensagens do Assistente IA mostram a formatação em bruto (asteriscos) | Baixa | E8F2U3 |
| 112 | Estado das reservas aparece em inglês | Baixa | E8F3U1 |
| 113 | Textos da área de administração em inglês | Baixa | E8F3U1 |
| 114 | Funções no "Aprovar pedido" aparecem com o nome técnico | Baixa | E8F3U1 |
| 115 | Botão de cancelar no "Aprovar pedido" tem o texto "Todos" | Baixa | E8F3U1 |
| 116 | Traduções incompletas na demo *(13/10)* | Baixa | E8F3U1 |
| 117 | Texto em inglês na ficha do jogador *(13/10)* | Baixa | E8F3U1 |
| 118 | Listas não atualizam após alterações, só depois de atualizar a página | Baixa | E8F5U1 |
| 119 | Escalão novo não aparece sem refresh *(13/10)* | Baixa | E8F5U1 |
| 120 | Após mudar de clube, a página de Épocas mostra dados do clube anterior até atualizar | Média | E8F5U1 |

---

## 2. Requisitos de outras fontes → User stories

| Fonte | Requisito | User story |
|---|---|---|
| Enunciado do TFC | Perfis de dirigentes, atletas e pais (encarregados) | E1F4U1, E2F2U1, E2F2U2 |
| Enunciado do TFC | Gestão de sócios e quotas | E5F1U1, E5F2U1, E5F2U2, E5F2U3 |
| Enunciado do TFC | Informação e comunicação dispersas em grupos de chat | E2F2U4, E3F5U3 |
| Orientador | Cobrir 100% das necessidades de um clube de pequena/média dimensão | E5F1U1 |
| Concorrência (ClubePT, EMJOGO, Adjunto) | Documentos do atleta com validades | E2F4U1, E2F4U2 |
| Concorrência (ClubePT) | Uma ficha de sócio por pessoa, independente da modalidade | E5F1U2 |
| Concorrência (ClubePT, Adjunto, Spond, 360Player) | Pagamentos na app (MB Way, Multibanco, cartão) | E5F3U1 |
| Concorrência (Adjunto, ClubePT) | Recibos automáticos | E5F3U2 |
| Concorrência (EMJOGO, Adjunto, ClubePT) | Gestão financeira (receitas e despesas) | E5F4U1 |
| Concorrência (Spond, 360Player, ClubePT) | Avisos para equipas e para todo o clube | E6F2U1 |
| Decisão do grupo | O encarregado pode avisar e justificar faltas | E3F5U3, E3F5U4, E3F5U5 |
| Hipótese a validar com o orientador | Encarregado com vários educandos no mesmo clube | E2F2U3 |
| Regra legal (menores de 16) | Consentimento parental obrigatório | E2F2U6 |
| Notas da área de administração | Stripe em modo real (live), sandbox nunca sincronizado e dados de teste que não se podem apagar | E8TU3 |

---

## 3. Falhas excluídas

| Falha | Motivo |
|---|---|
| Campos de data e hora parecem preenchidos mas estão vazios (placeholder) | Decisão do grupo: falha de aspeto sem impacto no funcionamento |

---

## 4. Áreas ainda por levantar

| Feature | Situação |
|---|---|
| E4F2 – Convocatórias | Área ainda não testada |
| E4F3 – Resultados e estatísticas de jogo | Área ainda não testada |
| E4F4 – Scouting de jogadores | Área ainda não testada |
