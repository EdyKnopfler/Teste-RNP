# Teste RNP

## Diagrama ER

Criado com o web app Lucid Chart. Base de dados inspecionada através do aplicativo DBeaver Community.

## Caderno Python `Teste RNP.ipynb`

Criado com o Databricks Community Edition. Como pedido, as tabelas da base de dados são lidas e salvas em arquivos `.parquet`, que representarão o estado corrente da base de dados.

Numa primeira execução são criados os arquivos no formato Delta correspondentes às tabelas.

Execuções posteriores apenas realizam o `merge` dos Parquets para os Delta. Como todo o conteúdo deve ser mesclado (não há atualizações incrementais), foi possível especificar de forma direta usando a API do Delta Lake como executar os INSERTs, UPDATEs e DELETEs.

Para as consultas foi escolhido o uso de SQL diretamente, embora seja possível através da API Python `spark.sql.*`.
