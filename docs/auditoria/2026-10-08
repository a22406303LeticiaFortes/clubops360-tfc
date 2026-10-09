# Auditoria de falhas – 08/10/2026

Exploração do site público e da plataforma com o perfil **Dirigente**, num clube de teste ("Clube Teste TFC", plano Free).
A descrição completa de cada falha (passos para reproduzir, o que acontece, o que devia acontecer) está no Notion.

## Site público

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 1 | Login na conta demo falha | Bug | Alta |
| 2 | Erro técnico mostrado ao utilizador na demo | Usabilidade | Baixa |
| 3 | Encarregados referidos como membros, mas sem papel na plataforma | Usabilidade | Média |
| 4 | Páginas internas do manual visíveis ao público | Segurança | Média |
| 5 | Exportar PDF do manual gera documento em branco | Bug | Média |

## Plataforma (Dirigente)

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 6 | Plano Free permite mais modalidades do que o limite (4/1) | Bug | Alta |
| 7 | Página de Equipas não carrega (erro na base de dados) | Bug | Alta |
| 8 | Planos na Subscrição não mostram os limites | Usabilidade | Média |
| 9 | Wizard aceita email e website inválidos | Bug | Baixa |
| 10 | Escalão aceita ano mínimo maior que o máximo | Bug | Baixa |
| 11 | Não é possível atribuir ou convidar o papel de Dirigente | Bug | Média |
| 12 | Notificações por email ativas, mas não funcionam | Bug | Média |
| 13 | Ferramenta interna de testes de notificações visível ao dirigente | Usabilidade | Baixa |
| 14 | Secções de pagamento duplicadas | Usabilidade | Baixa |
| 15 | Plano Free com renovação e cancelamento | Usabilidade | Baixa |
| 16 | Consentimento parental aceita email inválido | Bug | Média |
| 17 | Ficha do jogador aceita dados físicos e data de nascimento impossíveis | Bug | Média |
| 18 | Dois campos de posição diferentes geram dados incoerentes | Usabilidade | Média |
| 19 | Altura média apresentada com a unidade errada | Bug | Baixa |
| 20 | Importação de jogadores sem modelo de ficheiro | Usabilidade | Baixa |
| 21 | Local aceita email e telefone inválidos | Bug | Baixa |
| 22 | Espaço aceita capacidade negativa ou zero | Bug | Baixa |
| 23 | Gestão de slots de disponibilidade pouco prática | Usabilidade | Baixa |
| 24 | Disponibilidades e reservas aceitam horários impossíveis e duplicados | Bug | Baixa |
| 25 | Estado das reservas aparece em inglês | Usabilidade | Baixa |
| 26 | Regras de calendário sem validação de horários, disponibilidade e duplicados | Bug | Média |
| 27 | Uma regra com horário inválido bloqueia a geração de todos os treinos | Bug | Alta |
| 28 | Editar um treino altera o horário em +1 hora sem o utilizador mexer | Bug | Alta |
| 29 | Exercícios adicionados a um treino não ficam guardados | Bug | Alta |
| 30 | Plano de Treino guardado não pode ser consultado nem editado | Bug | Alta |
| 31 | Plano de Treino e Treino funcionam em separado | Usabilidade | Média |
| 32 | Plano de Treino não usa a biblioteca de exercícios | Usabilidade | Média |
| 33 | Plano de Treino aceita duração negativa nos exercícios | Bug | Baixa |
| 34 | Presenças mostram o jogador como "Sem nome" e não podem ser guardadas | Bug | Alta |

## Padrões identificados
- Falta de validação de dados em vários formulários
- Erros técnicos mostrados ao utilizador, em inglês
- Problemas de fuso horário nas horas dos treinos
- Funcionalidades separadas que deviam estar ligadas
- Ferramentas internas visíveis ao cliente
- Incoerências entre site, manual e plataforma
