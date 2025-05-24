# Dicionário de Dados: European Soccer Database
Este banco de dados reúne informações detalhadas sobre o futebol europeu, ideal para análises e machine learning. Ele contém estatísticas de mais de 25.000 partidas e 10.000 jogadores, além de atributos retirados do jogo FIFA da EA Sports. Também inclui dados de apostas, eventos das partidas e formações dos times, cobrindo 11 países e as temporadas de 2008 a 2016.

## Camada Silver

## Descrição
A tabela `Team` contém informações sobre os times de futebol, incluindo identificadores únicos, nomes completos e curtos, além do código FIFA.

## Estrutura da Tabela

| Nome da Coluna     | Tipo      | Descrição |
|--------------------|----------|-----------|
| `id`              | INTEGER  | Identificador único do time na base de dados |
| `team_api_id`     | INTEGER  | ID do time utilizado na API do banco de dados |
| `team_long_name`  | STRING   | Nome completo do time |
| `team_short_name` | STRING   | Nome curto ou abreviação do time |
| `team_fifa_api_id`| INTEGER  | ID do time utilizado na base de dados FIFA |

---

##  Descrição
A tabela `Team_attributes` armazena informações detalhadas sobre características táticas e atributos dos times de futebol ao longo das temporadas. Ela contém indicadores de construção de jogadas, criação de oportunidades e eficiência defensiva.

## Estrutura da Tabela

| Nome da Coluna                | Tipo      | Descrição |
|--------------------------------|----------|-----------|
| `id`                           | INTEGER  | Identificador único do registro |
| `date`                         | DATE     | Data da coleta do atributo |
| `team_api_id`                  | INTEGER  | Identificador do time na API |
| `team_fifa_api_id`              | INTEGER  | Identificador do time na base FIFA |
| `defencePressure`               | INTEGER  | Pressão defensiva aplicada pelo time |
| `defenceAggression`             | INTEGER  | Intensidade da agressividade na defesa |
| `defenceTeamWidth`              | INTEGER  | Largura da linha defensiva do time |
| `defencePressureClass`          | STRING   | Classificação qualitativa da pressão defensiva |
| `defenceAggressionClass`        | STRING   | Classificação qualitativa da agressividade defensiva |
| `defenceTeamWidthClass`         | STRING   | Classificação qualitativa da largura defensiva |
| `defenceDefenderLineClass`      | STRING   | Estratégia defensiva da linha de defensores |
| `buildUpPlaySpeed`              | INTEGER  | Velocidade na construção de jogadas |
| `buildUpPlayPassing`            | INTEGER  | Qualidade dos passes na construção de jogadas |
| `buildUpPlayDribbling`          | INTEGER  | Uso de dribles na construção de jogadas |
| `buildUpPlaySpeedClass`         | STRING   | Classificação qualitativa da velocidade de construção |
| `buildUpPlayPassingClass`       | STRING   | Classificação qualitativa do passe na construção |
| `buildUpPlayDribblingClass`     | STRING   | Classificação qualitativa do drible na construção |
| `buildUpPlayPositioningClass`   | STRING   | Posicionamento dos jogadores na construção de jogadas |
| `chanceCreationPassing`         | INTEGER  | Qualidade dos passes na criação de oportunidades |
| `chanceCreationCrossing`        | INTEGER  | Eficiência nos cruzamentos ofensivos |
| `chanceCreationShooting`        | INTEGER  | Precisão nos chutes para finalização |
| `chanceCreationPassingClass`    | STRING   | Classificação qualitativa dos passes ofensivos |
| `chanceCreationCrossingClass`   | STRING   | Classificação qualitativa dos cruzamentos ofensivos |
| `chanceCreationShootingClass`   | STRING   | Classificação qualitativa das finalizações ofensivas |
| `chanceCreationPositioningClass`| STRING   | Posicionamento dos jogadores na criação de oportunidades |

---
 

## Descrição
A tabela `Match` contém informações detalhadas sobre partidas de futebol, incluindo estatísticas do jogo, escalação dos times e dados de apostas. Essa tabela permite análises sobre desempenho de equipes, jogadores e padrões táticos ao longo das temporadas.

## 📊 Estrutura da Tabela

| Nome da Coluna         | Tipo      | Descrição |
|------------------------|----------|-----------|
| `_airbyte_raw_id`      | STRING   | Identificador interno do sistema Airbyte |
| `_airbyte_extracted_at`| TIMESTAMP| Data e hora da extração dos dados |
| `_airbyte_meta`        | STRUCT   | Metadados da sincronização Airbyte |
| `_airbyte_generation_id` | BIGINT  | Identificador da geração dos dados |
| `id`                   | INTEGER  | Identificador único da partida |
| `match_api_id`         | INTEGER  | Identificador da partida na API do banco de dados |
| `league_id`            | INTEGER  | Liga à qual a partida pertence |
| `country_id`           | INTEGER  | País no qual a partida ocorreu |
| `season`               | STRING   | Ano da temporada |
| `stage`                | INTEGER  | Fase da competição |
| `date`                 | DATE     | Data da partida |
| `home_team_api_id`     | INTEGER  | Identificador do time mandante |
| `away_team_api_id`     | INTEGER  | Identificador do time visitante |
| `home_team_goal`       | INTEGER  | Número de gols do time mandante |
| `away_team_goal`       | INTEGER  | Número de gols do time visitante |
| `possession`           | INTEGER  | Porcentagem de posse de bola do time mandante |
| `foulcommit`           | INTEGER  | Número de faltas cometidas pelo time mandante |
| `corner`              | INTEGER  | Número de escanteios no jogo |
| `card`                 | INTEGER  | Número de cartões recebidos na partida |
| `shoton`               | INTEGER  | Total de finalizações certas na partida |
| `shotoff`              | INTEGER  | Total de finalizações erradas na partida |
| `cross`                | INTEGER  | Número de cruzamentos realizados |
| `goal`                 | INTEGER  | Total de gols marcados na partida |
| `home_player_1` - `home_player_11` | INTEGER | Identificadores dos jogadores titulares do time mandante |
| `away_player_1` - `away_player_11` | INTEGER | Identificadores dos jogadores titulares do time visitante |
| `home_player_X1` - `home_player_X11` | FLOAT | Coordenadas X dos jogadores mandantes no posicionamento tático |
| `home_player_Y1` - `home_player_Y11` | FLOAT | Coordenadas Y dos jogadores mandantes no posicionamento tático |
| `away_player_X10` - `away_player_X11` | FLOAT | Coordenadas X dos jogadores visitantes no posicionamento tático |
| `away_player_Y10` - `away_player_Y11` | FLOAT | Coordenadas Y dos jogadores visitantes no posicionamento tático |
| `B365A`, `B365D`, `B365H` | FLOAT | Odds de apostas da Bet365 para vitória, empate ou derrota |
| `PSA`, `PSD`, `PSH`       | FLOAT | Odds de apostas da Pinnacle Sports |
| `BWA`, `BWD`, `BWH`       | FLOAT | Odds de apostas da Bet & Win |
| `SJA`, `SJD`, `SJH`       | FLOAT | Odds de apostas da SJ |
| `VCA`, `VCD`, `VCH`       | FLOAT | Odds de apostas da VC |
| `WHA`, `WHD`, `WHH`       | FLOAT | Odds de apostas da William Hill |

---

 