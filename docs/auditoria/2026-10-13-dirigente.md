# Auditoria de falhas – 13/10/2026

Testes feitos com o perfil **Dirigente**, num clube de teste (plano Enterprise).
Objetivos: (1) reproduzir a auditoria de 08/10 e (2) encontrar falhas novas.
A descrição completa de cada falha (passos para reproduzir, o que acontece, o que devia acontecer) está no Notion.

## Falhas novas

### Site público e traduções

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 1 | Traduções incompletas na demo | Usabilidade | Baixa |

### Configuração do clube

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 2 | Campo Website só existe no wizard de criação | Usabilidade | Baixa |

### Plano e pagamentos

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 3 | Subscrição "Cancelado" continua com renovação e acesso total | Bug | Média |
| 4 | Histórico da subscrição vazio | Bug | Baixa |
| 5 | Impossível mudar para o plano Free | Bug | Média |
| 6 | Lista de planos confusa (ciclo anual mostra preço mensal) | Usabilidade | Baixa |

### Utilizadores e papéis

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 7 | Dirigente não pode atribuir-se o papel de Treinador | Usabilidade | Média |
| 8 | Aviso de validação aparece antes de submeter | Usabilidade | Baixa |

### Equipas e plantel

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 9 | Escalão novo não aparece sem refresh | Bug | Baixa |
| 10 | Consentimento parental "Válido" com email inválido | Bug | Média |
| 11 | Estatísticas com idade negativa | Bug | Baixa |
| 12 | Texto em inglês na ficha do jogador | Usabilidade | Baixa |

### Locais e reservas

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 13 | Reservas não respeitam a disponibilidade do espaço | Bug | Média |

### Exercícios, treinos e presenças

| # | Falha | Tipo | Gravidade |
|---|---|---|---|
| 14 | Impossível criar exercícios na biblioteca (erro de permissões) | Bug | Alta |
| 15 | "Volume (min)" do Plano de Treino não é calculado | Usabilidade | Baixa |
| 16 | Mensagem "Presença guardada" enganadora | Bug | Média |
| 17 | Botões de presenças incoerentes | Usabilidade | Baixa |

## Reprodução da auditoria de 08/10

### Novos detalhes sobre falhas já registadas
- **Página de Equipas não carrega:** a equipa é criada, só a tabela falha. Causa provável: duas ligações entre as tabelas de equipas e modalidades, e a base de dados não sabe qual usar.
- **Regra inválida bloqueia a geração de treinos:** o erro aparece em inglês e não diz qual é a regra. A validação só acontece na geração, não na criação da regra.
- **Editar treino +1 hora:** só acontece quando se preenchem todos os campos do treino (testado antes e depois da mudança de hora).
- **Plano de Treino guardado:** abre no editor de Treino e perde formato dos campos, objetivos, microciclo e exercícios (confirmado 2 vezes).
- **Presenças "Sem nome":** o jogador não fica ligado à presença (erro técnico de identificador vazio).
- **Gestão de slots:** além de ser um dia de cada vez, os slots não podem ser editados, só apagados.
- **Exportar PDF do manual:** gera uma única página A4 sem texto nem imagens.
- **Manual público:** as páginas internas mostram problemas de validação e chaves técnicas em vez do texto.

### Não reproduzidas ou reclassificadas

| Falha de 08/10 | Resultado a 13/10 |
|---|---|
| Não é possível convidar o papel de Dirigente | Não reproduzida – convite criado sem erro (provavelmente corrigida) |
| Dois campos de posição diferentes | Não reproduzida em Futebol (reproduzida pela Letícia em Futsal) |
| Altura média com a unidade errada | Reclassificada – o campo pede metros e mostra bem; o problema real é aceitar alturas impossíveis (falta de validação) |
| Plano Free permite mais modalidades / Free com renovação | Não testável nesta conta (plano Enterprise) |

## O que funciona
- Reservas sobrepostas no mesmo espaço são bloqueadas ("Conflito de horário")
- A regra que impede um utilizador de se atribuir papéis a si próprio funciona (bom do ponto de vista de segurança)

## Padrões identificados
- Falta de validação de dados (consentimento, datas de nascimento, reservas)
- Mensagens de sucesso que não correspondem ao que ficou guardado
- Erros técnicos mostrados ao utilizador, em inglês
- Algumas falhas de 08/10 já não se reproduzem: outras pessoas estão a alterar a plataforma
