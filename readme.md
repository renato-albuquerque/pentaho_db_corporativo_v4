# Projeto Unidade 02 | PENTAHO | Data Analytics | Digital College Brasil

Desenvolvimento de Projeto utilizando a ferramenta PENTAHO. Populando tabelas no PostgreSQL (Arquivo csv para bd: corporativo_v4).<br>
Tecnologias utilizadas: SQL / PostgreSQL / Pentaho.<br>

Instituição: [Digital College Brasil](https://digitalcollege.com.br/) (Fortaleza/CE) <br>
Curso: Data Analytics (Turma 18) <br>
Instrutora: [Nayara Wakweski](https://github.com/NayaraWakewski) <br>

## Etapas de Desenvolvimento (Summary)
1. Entendimento do projeto. "Popular tabelas no banco de dados no PostgreSQL `(bd corporativo_v4)`".
2. Conectar o Pentaho com o PostgreSQL.
3. Importar arquivos `csv` no Pentaho.
4. Desenvolver fluxos para tratamento dos dados no Pentaho (Transformações, ktr's).
5. Dados inseridos nas tabelas do PostgreSQL. <br>

## Execução da sequência de STEPS no Pentaho

### `Step: CSV file input.` 
Importar arquivo csv (06 colunas). <br>
![screenshot](/images/importar_csv.png) <br>

### `Step: String operations.` 
Alterando o nome das colunas: bairro -> bairros / nomemunicipio -> cidade / uf -> estado. <br>
`Trim type: both` para todas as colunas. <br>
`Lower/Upper: upper` para todas as colunas. <br> 
![screenshot](/images/string_operations.png) <br>

### `Step: Get system info.` 
Obter informações detalhadas sobre o sistema em que a transformação está sendo executada. Obter a data e hora atual do sistema.<br>
![screenshot](/images/get_system_info.png) <br>

### `Step: Select values (1).` 
Modificar os dados de um fluxo, permitindo renomear, remover ou reordenar os campos (colunas). Nesta etapa será removido 3 colunas (bairro, nomemunicipio, uf).<br>
![screenshot](/images/select_values1.png) <br>

### `Step: Database lookup (1).` 
Pesquisar informações adicionais em um banco de dados (bd corporativo_v4, schema geral, tabela estado) e adicionar essas informações ao fluxo de dados em tempo real.<br>
![screenshot](/images/database_lookup_estado.png) <br>

### `Step: Database lookup (2).` 
Pesquisar informações adicionais em um banco de dados (bd corporativo_v4, schema geral, tabela cidade) e adicionar essas informações ao fluxo de dados em tempo real.<br>
![screenshot](/images/database_lookup_cidade.png) <br>

### `Step: Filter rows (1).` 
Filtrar os dados que estão sendo processados, com base em uma condição (id_cidade IS NOT NULL). <br>
![screenshot](/images/filter_rows_1.png) <br>

### `Step: Dummy do nothing (1).` 
Ponto de interrupção para verificar o fluxo de dados nesta etapas, sem realizar nenhuma transformação.<br>

### `Step: Select values (2).` 
Modificar os dados de um fluxo, permitindo renomear, remover ou reordenar os campos (colunas). Nesta etapa está recebendo as informações filtradas do step: Filter rows (1), id_cidade IS NOT NULL.<br>
![screenshot](/images/select_values_2.png) <br>

### `Step: Database lookup (3).` 
Pesquisar informações adicionais em um banco de dados (bd corporativo_v4, schema geral, tabela bairro) e adicionar essas informações ao fluxo de dados em tempo real.<br>
![screenshot](/images/database_lookup_bairro.png) <br>

### `Step: Filter rows (2).` 
Filtrar os dados que estão sendo processados, com base em uma condição (id_bairro IS NOT NULL). <br>
![screenshot](/images/filter_rows_2.png) <br>

### `Step: Select values (3).` 
Modificar os dados de um fluxo, permitindo renomear, remover ou reordenar os campos (colunas). Nesta etapa está recebendo as informações filtradas do step: Filter rows (2), id_bairro IS NOT NULL.<br>
![screenshot](/images/select_values_3.png) <br>

### `Step: Table output.` 
Escreve os dados processados diretamente em uma tabela de banco de dados (bd corporativo_v4, schema geral, tabela pessoa).<br>
![screenshot](/images/table_output_pessoa_1.png)
![screenshot](/images/table_output_pessoa_2.png) <br>

### `Pentaho Pipeline até o momento.` 
Popular a tabela pessoa, bd corporativo_v4, schema geral.<br>
![screenshot](/images/pentaho_pipeline_1.png) <br>

### `Dados inseridos na tabela pessoa (PostgreSQL).` 
![screenshot](/images/table_pessoa_data_insert.png) <br>