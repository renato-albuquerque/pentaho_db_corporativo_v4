# Projeto Unidade 02 | PENTAHO | Data Analytics | Digital College Brasil

Desenvolvimento de Projeto utilizando a ferramenta PENTAHO. Populando tabelas no PostgreSQL (Arquivo csv para bd: corporativo_v4).<br>
Tecnologias utilizadas: SQL / PostgreSQL / Pentaho.<br>

Instituição: [Digital College Brasil](https://digitalcollege.com.br/) (Fortaleza/CE) <br>
Curso: Data Analytics (Turma 18) <br>
Instrutora: [Nayara Wakweski](https://github.com/NayaraWakewski) <br>

## Etapas de Desenvolvimento (Summary)
1. Entendimento do projeto. "Popular tabelas no banco de dados no PostgreSQL (bd corporativo_v4)".
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