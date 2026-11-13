# Auditoria da plataforma ClubOps360

Antes de propor melhorias, a plataforma foi testada à mão para perceber o que funciona, o que falha e o que falta. Cada falha encontrada foi registada no Notion ("Auditoria – Falhas") com:

- **Falha** – título curto e geral
- **Perfil** – quem é afetado (Visitante, Atleta, Dirigente, Admin, Geral)
- **Tipo** – Bug, Usabilidade ou Segurança
- **Gravidade** – Alta, Média ou Baixa
- **Onde** – ecrã ou caminho na plataforma
- **Evidência** – capturas de ecrã
- **Estado** – Por analisar, Em curso, Resolvido

Nesta pasta está o resumo de cada sessão. A descrição completa de cada falha (passos para reproduzir, o que acontece e o que devia acontecer) está no Notion.

## Sessões de testes

| Data | Ficheiro | Âmbito | Falhas | Alta | Média | Baixa |
|---|---|---|---|---|---|---|
| 08/10/2026 | [`2026-10-08-dirigente.md`](2026-10-08-dirigente.md) | Site público e plataforma com o perfil Dirigente | 34 | 8 | 12 | 14 |
| 13/10/2026 | [`2026-10-13-dirigente.md`](2026-10-13-dirigente.md) | Reprodução da sessão de 08/10 e falhas novas (Dirigente) | 17 | 1 | 6 | 10 |
| 23/10/2026 | [`2026-10-23-admin.md`](2026-10-23-admin.md) | Gestão de clubes, sessão, pedidos de adesão, utilizadores e permissões | 22 (+2 melhorias) | 2 | 8 | 12 |
| 05/11/2026 | [`2026-11-05-admin.md`](2026-11-05-admin.md) | Área de administração completa (clubes, IA, planos, faturação, Stripe, auditoria, tickets) | 43 | 7 | 17 | 19 |
| 06/11/2026 | [`2026-11-06-jogador.md`](2026-11-06-jogador.md) | Permissões do perfil Jogador | 2 (+1 melhoria) | 0 | 2 | 0 |
| **Total** | | | **118** | **18** | **45** | **55** |

Uma falha aparece em duas sessões (subscrição cancelada que continua a indicar renovação: 13/10 n.º 3 e 05/11 n.º 16). Sem a repetição:

| | Total | Alta | Média | Baixa |
|---|---|---|---|---|
| **Falhas únicas** | **117** | **18** | **44** | **55** |
| Melhorias propostas | 3 | – | – | – |

### Por tipo (falhas únicas)

| Bug | Usabilidade | Segurança |
|---|---|---|
| 67 | 41 | 9 |

## Padrões encontrados
- **Falta de validação de dados** – formulários aceitam emails, datas, valores e quantidades impossíveis (incluindo faturas e pagamentos)
- **Mensagens enganadoras** – mensagens de sucesso quando nada foi guardado e erros técnicos em inglês mostrados ao utilizador
- **Permissões incoerentes** – o servidor bloqueia, mas a interface mostra páginas e botões a quem não os pode usar; algumas regras de segurança podem ser contornadas
- **Funcionalidades separadas que deviam estar ligadas** – Plano de Treino e Treino, plataforma e Stripe, faturas e pagamentos
- **Dados que só atualizam depois de recarregar a página**
- **Ferramentas internas visíveis ao cliente**

## Áreas não testadas
- **Jogos, convocatórias, resultados e scouting** – por testar (features E4F2 a E4F4 por levantar)
- **Templates de Landing, Agente IA de Teste, Pedidos RGPD, Verificação DNS, Conteúdos e Identidade & Email** – por decisão do grupo, por exigirem perfil técnico ou autorização

## Ligação aos requisitos
Cada falha deu origem a pelo menos uma user story. A ligação entre falhas e user stories está na [matriz de rastreio](../requisitos/matriz-rastreio.md).
