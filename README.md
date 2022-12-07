# Análise de dados (Pandas)
 Análise de dados em Python usando Pandas e Jupyter Notebook.

# Índice 

* [Descrição do Projeto](#descrição-do-projeto)
* [Desenvolvedor](#desenvolvedor)
* [Lista de comandos](#Lista-de-comandos)


# Descrição do projeto
 O intuito deste material é fazer uma análise didática de uma base de dados de uma empresa usando a biblioteca Pandas, que permite manipular,
 e analisar diversas fontes de dados (excel, csv, pdf etc).
 Neste tutorial iremos usar dados fictícios de uma empresa, para com base nessas informações extrair algumas perguntas que podem
 contribuir para o sucesso da organização.

# Desenvolvedor

| [<img src="https://user-images.githubusercontent.com/115194365/202005566-f6278b6c-4f75-416f-b01c-e79b8d04f02e.jpg" width=115><br><sub>Daniel de Souza Amorim</sub>](https://github.com/DaniellsamorimGit) |
| :---: | 

# Lista de comandos

Segue a lista e descrição dos comandos da biblioteca Pandas que iremos aprender neste tutorial:

#### Importando pandas:
    - import pandas as pd
#### Lendo um arquivo:
    - df = pd.read_csv(r'caminho do arquivo')
#### Ver informações de cada item da tabela (tipo de dados):
    - df.info()
#### Lendo colunas específicas:
    - df = df[['coluna 1', 'coluna 2' ...]]
#### Pegando valor max e min de uma coluna:
    - df = max(df['coluna x'])
    - df = min(df['coluna x'])
#### Comando .LOC[...] localiza item com base num parametro:
    - df.loc[df["coluna mes"] == "janeiro"]
#### Removendo colunas(axis=1) ou linhas(axis=0) específicas .DROP():
    - df = df.drop(['coluna 1', 'coluna 2' ...], axis=1)
#### Mesclando tabelas distintas .MERGE():
Podemos mesclar tabelas com o .merge(), porém para isso temos que ter em todas as 
tabelas a serem mescladas uma coluna com mesmo nome para todos (esse sera nosso ID):


    - new_df = df1.merge(df2, on="coluna") 
    ** onde coluna = nome da coluna comum às duas tabelas (ID)
    
#### Alterando nome de uma coluna .RENAME():
    - df = df.rename(columns={'nome_antigo': 'novo_nome'})
#### Contando quantas vezes um item aparece na tabela .VALUE_COUNTS()
No caso abaixo vai mostrar qntas vezes cada cliente comprou ja que cada compra de cada cliente  fica registrada.

    - compras_cada_cliente = df_vendas['compra cliente'].value_counts()
#### Podemos tambem agrupar cada item de uma DB e calcular seus valores:
Para agrupar usamos o GROUPBY():

    - db = db.groupby('nomedacoluna')
    
Para calcular os valores dos itens agrupados podemos somar .SUM()/ fazer a média .MEAN()/
max ou min (ja visto anteriormente). Abaixo exemplo de agrupamento com soma dos itens:

    - db = db.groupby('nomedacoluna').sum()
    
#### Ordenando colunas do maior para o menor:
    - df = df.sort_values('nome da coluna a ordenar', ascending=True) 
     *** ascending=False == ordem decrescente
    
#### Trabalhando com datas no pandas:

Datas geralmente não são recoinhecidas, pra isso temos que converter datas de uma tabela para 
datetime, o pandas faz isso com PD.TO_DATETIME():

    - df[nomedacoluna] = pd.to_datetime(df[nomedacoluna], format='%d/%m/%Y')
    
OBS: no format='%d/%m/%Y' temos que informar pro pandas qual formato esta na tabela
para mais informações com trabalhar com data veja no projeto.
    
    
    
