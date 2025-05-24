# Análise de Desempenho de Times por Temporada - MBA BI & Big Data
### Wandeilson Ferreira

## Sobre o Projeto
Este projeto tem como objetivo a análise estatística do desempenho de times ao longo de diferentes temporadas, utilizando ETL e ELT para a transformação e armazenamento dos dados. Através da modelagem e processamento eficiente, buscamos identificar qual time possui o melhor desempenho com base em métricas como:
- Média de gols por partida
- Eficiência ofensiva (total de finalizações certas)
- Eficiência defensiva (média de gols sofridos)
- Ranking dos times baseado no desempenho calculado
 
### Arquitetura do Projeto
🔹 ETL (Extract, Transform, Load)
- Extração de dados de arquivos brutos
- Transformação e limpeza dos dados
- Carregamento dos dados para um armazenamento estruturado
  
🔹 ELT (Extract, Load, Transform)

- Armazenamento dos dados brutos no MinIO (S3-compatible storage)
- Processamento dos dados diretamente no Jupyter Notebook utilizando PySpark
- Transformações como agregação, cálculo de métricas e ranking diretamente no ambiente analítico

#### Fluxo de Dados
1 -  Coleta de dados: Arquivos de partidas e estatísticas fornecidos pelo professor.
2 - Carregamento no ambiente analítico: Jupyter Notebook acessa os dados e inicia o processamento
3️ -  Transformação dos dados: Limpeza, cálculos estatísticos e ranking dos times são aplicados usando PySpark
4 -  Visualização e insights: Os resultados são exibidos no Jupyter Notebook 

 #### Tecnologias Utilizadas
🔹 Docker 
🔹 MinIO S3 
🔹 Jupyter Notebook
🔹 PySpark 
🔹 Git 
 

### Contribuições
Caso queira contribuir com melhorias, fique à vontade para enviar um Pull Request ou abrir uma Issue!
 
