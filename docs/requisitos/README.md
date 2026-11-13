# Requisitos – ClubOps360

Os requisitos foram levantados a partir de quatro fontes:

1. **Auditoria da plataforma** – falhas encontradas nos testes (ver `docs/auditoria/`)
2. **Análise da concorrência** – funcionalidades que os concorrentes têm e o ClubOps360 não (ver `docs/benchmarking/`)
3. **Enunciado do TFC** – objetivos definidos pelo orientador
4. **Decisões do grupo** – propostas de melhoria discutidas pelo grupo

## Organização (Macro, Mezzo e micro)

| Nível | Nome | Código | Exemplo |
|---|---|---|---|
| Macro | Épico | E1 | E1 – Estrutura do Clube |
| Mezzo | Feature | E1F4 | E1F4 – Papéis dos utilizadores |
| micro | User story | E1F4U1 | Como dirigente, quero atribuir o papel de Encarregado… |

As user stories técnicas (que não são vistas pelos utilizadores) têm o código `ExTUy` (ex.: E8TU1).

Cada user story tem:
- **Origem** – de onde veio (falha da auditoria, concorrência, enunciado ou decisão do grupo)
- **Critérios de aceitação** – condições para a user story ser considerada concluída

## Ficheiros

| Ficheiro | Conteúdo |
|---|---|
| `epicos-e-features.md` | Lista dos 8 épicos e das 40 features |
| `user-stories/` | User stories de cada épico, com origem e critérios de aceitação |
| `tech-user-stories.md` | User stories técnicas |
| `matriz-rastreio.md` | Ligação entre cada falha da auditoria e a user story que a resolve |

## Totais

| Épicos | Features | User stories | Técnicas |
|---|---|---|---|
| 8 | 40 | 108 | 4 |

O planeamento e o estado de cada user story estão no Trello.
