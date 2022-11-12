# Desafio Big Data
## Explorando Dados Demográficos com Serviços de Big Data na AWS

Neste desafio foi explorado o poder do SQL em uma ferramenta de BigData totalmente gerenciada na Amazon Web Service (AWS), o Amazon Athena. Para isso, foram feitas consultas interativas com o objetivo de facilitar a análise de dados no Amazon S3 usando SQL padrão.

Serviços utilizados na AWS:
- Amazon S3;
- Amazon Glue;
- Amazon Athena;
- Amazon QuickSight

### Etapas para desenvolvimento

### Criar bucket no Amazon S3
- Amazon S3 Console -> Buckets -> Create bucket -> Bucket name [nome_do bucket] - Create bucket
- Create folder (Criar uma pasta chamada /output e outra com o nome do seu conjunto de dados. Este nome irá definir o nome da tabela criada no Glue)
- Upload dos arquivos de dados localizados na pasta /data

### Criar Glue Crawler
- Amazon Glue Console -> Crawlers -> Add Crawler
- Source type [Data Stores] -> Crawl all folders
- Data store [S3] -> Include path [caminho do diretório dos dados de entrada]
- Create IAM Role
- Frequency [Run on demand]
- Database name [seu_nome_de_db]
- Group behavior [Create a single schema for each S3 path]
- Finish
- Databases -> Tables -> Visualizar dados das tabelas criadas

### Criar aplicação no Amazon Athena
- Query editor -> Settings -> Manage settings -> Query result location and encryption -> Browse S3 -> selecionar o bucket criado
= Selecionar Database -> criar queries. Exemplos estão disponíveis na pasta querys
- Verificar queries não salvas no bucket criado no S3
- Salavar queries -> Executar novamente -> Verificar no bucket criado no S3

### Criando nova tabela
- Generate table DDL
- Copiar a query gerada
- Selecionar o DB e criar a nova tabela em uma nova query

### Visualizar dados no Amazon QuickSight
- Signup (caso não tenha conta) -> Escolher [Standard]
- Datasets -> Create new dataset -> Athena -> Name [NomeDoDataSet] -> Create
- Select database -> select table -> Edit or preview -> Save & visualize
- Criar visualizações selecionando colunas, criando filtros e parâmetros e selecionando Visual types para gráficos.

Conforme ANEXO 1, é demonstrado as 10 maiores cidades brasileiras da região sudeste por habitante. Uma outra análise pode ser observada no ANEXO 2, onde é demonstrado o número de habitantes e qual sua porcentagem para cada região do brasil.
