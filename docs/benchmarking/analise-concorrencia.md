# Análise da Concorrência

> Versão apresentada ao orientador na reunião de 09/11/2026 (Notion). A análise inicial de 08/10 está em [`analise-inicial.md`](analise-inicial.md).

## Resumo

O ClubOps360 tem hoje a parte desportiva ao nível dos concorrentes, mas falta-lhe quase toda a parte administrativa e financeira que um clube pequeno ou médio precisa. É aí que os concorrentes portugueses são mais fortes.

- O concorrente mais próximo do objetivo "100% do clube" é o **ClubePT**: já faz quase tudo o que falta ao ClubOps360 na parte administrativa. Gere os sócios e as quotas, recebe pagamentos pela app (MB, MB Way ou cartão), passa as faturas sozinho, faz inscrições online, guarda os documentos dos atletas e dá acesso aos pais. Serve para 23 modalidades.
- **EMJOGO** e **Adjunto** dominam o mercado português: o EMJOGO tem mais de 600 clubes, incluindo praticamente metade da I Liga; o Adjunto aposta num preço único com tudo incluído.
- A **IA** é o principal fator de diferenciação do ClubOps360: nenhum concorrente tem um assistente de IA confirmado no site oficial. O Adjunto só é referido em diretórios como tendo IA para gerar exercícios.
- Os nossos testes mostram que a diferença não está só nas funcionalidades, mas na **fiabilidade**: várias funcionalidades existem no ClubOps360 mas falham (presenças, plano de treino, faturação, comunicação).
- Dois concorrentes não publicam preços (360Player e ClubePT). O ClubOps360 tem preços públicos e um plano grátis, o que é uma vantagem para clubes pequenos.

## Concorrentes analisados

Analisámos cinco plataformas: duas internacionais muito usadas e três portuguesas, que são a concorrência direta no mercado onde o ClubOps360 vai entrar.

| Plataforma | Origem | Foco | Público principal | Modelo de negócio | Preço |
|---|---|---|---|---|---|
| Spond | Noruega | Comunicação, quotas e pagamentos | Clubes amadores e equipas de formação | Grátis; ganha com uma taxa sobre cada pagamento que os membros fazem ao clube | App grátis; taxa por pagamento (ex.: Reino Unido 2,5% + 0,20 £); site do clube 15 €/mês (12 meses grátis na zona euro) |
| 360Player | Suécia | Gestão do clube + desenvolvimento desportivo | Clubes com formação estruturada | Subscrição por proposta | Sob consulta: depende do n.º de membros e dos módulos, mais taxas de pagamento |
| EMJOGO | Portugal | Gestão desportiva, sócios e site | Clubes portugueses de várias modalidades | Subscrição por módulos | Desportiva 30–60 €/mês + Sócios 10–15 € + Clube 0–10 € + Site 5–39 € (+IVA) |
| Adjunto | Portugal/Espanha | Clubes de futebol | Treinadores e clubes de futebol | Subscrição única, tudo incluído | Desde 5 €/mês (treinador); plano Clube 45 €/mês ou 450 €/ano (+IVA) |
| ClubePT | Portugal | Secretaria virtual + app para atletas e pais | Clubes e associações multimodalidade | Subscrição por proposta | Sob consulta (não publicado) |
| **ClubOps360** | Portugal | Gestão desportiva com IA (protótipo) | Clubes pequenos e médios | Subscrição por planos | Free · Basic 29,99 € · Pro 99,99 € · Enterprise 169,99 € por mês |

## Fichas por concorrente

### Spond
App gratuita muito usada em clubes amadores, forte em comunicação e cobranças, fraca na parte técnica.
- **Pontos fortes:** grátis para o clube; chat, publicações e sondagens; cobrança de quotas e eventos com lembretes; contas para crianças geridas pelos pais; app em 24 línguas, incluindo português.
- **Limitações:** quase nada para o treinador (não planeia treinos, não tem biblioteca de exercícios, vídeo nem scouting); o modelo de negócio tira uma percentagem de cada pagamento, o que sai caro a clubes com muitas quotas.
- **Relação com o ClubOps360:** é o oposto do ClubOps360 — tem a parte administrativa e de comunicação que nos falta e não tem a parte técnica que temos.

### 360Player
Plataforma sueca completa, que junta gestão do clube com desenvolvimento dos jogadores.
- **Pontos fortes:** inscrições e pagamentos (incluindo preços por datas e gestão de disputas); análise de vídeo de jogos e treinos; planos de desenvolvimento individual; estatísticas de jogo e minutos jogados; contas de pais; app com 4,5 de avaliação (372 avaliações) e em português.
- **Limitações:** preço só por proposta; sem IA referida nas últimas atualizações.
- **Relação com o ClubOps360:** é o modelo do que o ClubOps360 quer ser na parte desportiva, já com pagamentos e a parte dos pais já resolvidos.

### EMJOGO
Líder português: mais de 600 clubes e metade das equipas da I Liga (Moreirense, Famalicão, Santa Clara, Rio Ave, entre outras), fundado em 2015.
- **Pontos fortes:** gestão desportiva completa (treinos, competições, convocatórias, estatísticas); acompanhamento médico, escolar e psicológico; faz os cartões de sócio para os sócios; receitas, despesas e contas bancárias; referências Multibanco; site do clube; app para encarregados com horários, convocatórias e recibos.
- **Limitações:** para ter tudo, é preciso juntar vários módulos, o que fica mais caro (~124 €/mês + IVA); sem IA nem análise de vídeo referidas; scouting só no plano Standard.
- **Relação com o ClubOps360:** é o concorrente a bater em Portugal, pela base de clientes e pela cobertura administrativa.

### Adjunto
Software português para clubes de futebol, com um preço único que inclui tudo.
- **Pontos fortes:** planeamento semanal de treinos, biblioteca de exercícios com quadro tático animado, presenças, convocatórias em PDF; áreas próprias para staff médico e psicólogo; quotas por MB WAY e Multibanco com recibos automáticos; importação de plantéis da FPF; teste grátis de 30 dias sem cartão.
- **Limitações:** só futebol; sem acesso para pais referido; IA só referida em diretórios (Capterra, GetApp), não no site oficial.
- **Relação com o ClubOps360:** mostra que um preço único e simples atrai clubes que não querem montar pacotes de módulos.

### ClubePT
Secretaria virtual para clubes e associações, com app para atletas e pais (desenvolvida pela Saturno.net).
- **Pontos fortes:** 23 modalidades; pagamentos por MB, MB Way e cartão, processados automaticamente; faturação automática; inscrições e renovações online; documentos centralizados (atestados, fichas, autorizações); ciclos de treino partilháveis; site com loja online.
- **Limitações:** preço não publicado (só por reunião); pouca informação pública sobre scouting, vídeo ou IA; app com poucas avaliações (4,2, 6 avaliações).
- **Relação com o ClubOps360:** é o mais próximo do objetivo de cobrir 100% de um clube pequeno ou médio.

## Comparação de funcionalidades

Legenda: ✓ tem · ~ parcial · ✗ não tem · ? não confirmado

| Funcionalidade | ClubOps360 | Spond | 360Player | EMJOGO | Adjunto | ClubePT |
|---|---|---|---|---|---|---|
| Várias modalidades | ✓ | ✓ | ✓ | ✓ | ✗ (só futebol) | ✓ |
| Treinos e exercícios | ✓ | ~ | ✓ | ✓ | ✓ | ✓ |
| Análise de
