![Logo](https://github.com/adriellison/Reposit-rio-de-SQL/blob/main/cover.png)

# O que é SQL?

> SQL, ou Standard Query Language, é uma linguagem padrão declarativa utilizada para a manipulação de bancos de dados relacionais.

> O SQL é um conhecimento fundamental para quem precisa fazer consultas, pedidos e escrever queries em bancos de dados.

## Para que serve esse documento?

> Serve para ajudar você que ainda aprendeu os comandos SQL ou não sabe alguma funcionalidade do mesmo.

## Comandos básicos

- **CREAT**
    Cria uma `TABLE`, `DATABASE`, `INDEX` ou `VIEW`.
- **SELECT**
    Usado para listar os campos desejados no resultado de uma consulta.
- **UPDATE**
    Altera valores de um campo de um determinado registro.
- **DELETE**
    Remove registros de uma tabela.
- **DROP**
    Excluir `TABLE`, `DATABASE`, `INDEX` OU `VIEW`.
- **ALTER TABLE**
    Adicionar/Remover colunas da tabela.
- **INSERT INTO**
    Insere valores de registro em um campo da tabela.
---
- **AS**
    Renomeia uma coluna temporariamente.
- **FROM**
    Especifica todas as tabelas que a serem utilizadas na consulta.
- **WHERE**
    Consiste em uma condição que filtra a consulta com elementos correspondentes que aparecem na cláusula `FROM`.
- **JOIN**
    Combina colunas de uma ou mais tabelas.
- **AND**
    Condição em uma consulta, significa 'E'.
- **OR**
    Condição em uma consulta, significa 'Ou'.
- **LIKE**
    Procura padrões em uma coluna, significa 'Parecido'.
- **IN**
    Especifica vários valores ao usar `WHERE`, significa 'Em'.
- **IS NULL**
    Retorna apenas linhas com valor nulo.
- **LIMIT**
    Limita as linhas que serão exibidas no resultado.
- **CASE**
    Permite a criação de estruturas de controle complexas para testar condições.
---
- **GROUP BY**
    Agrupa registros semelhantes em uma tabela.
- **ORDER BY**
    Organiza os resultados com uma ou mais colunas, podendo definir a ordem como crescente ou decrescente.
- **HAVING**
    Usado para especificar condições de filtragem em grupos, filtra as colunas agrupadas.
- **SUM**
    Retorna a soma da coluna.
- **MIN**
    Retorna o valor mínimo da coluna.
- **MAX**
    Retorna o valor máximo da coluna.
- **AVG**
    Retorna a média das colunas.
- **COUNT**
    Conta o número de linhas.

## 📋 Exemplos de comandos

#### Criar um banco de dados
```sql
    CREAT DATABASE meuBanco;
```

#### Mostrar todos os bancos de dados
```sql
    SHOW DATABASES;
```

#### Selecionar o banco de dados que queremos usar
```sql
    USE meuBanco;
```

#### Criar uma tabela 
```sql
    CREAT TABLE teste (codigo int(5) PRIMARY KEY AUTOINCREMENT, nome(255));
```
> _PRIMARY KEY - É um identificador de valor único de registro na tabela, pode ser constituída de um campo (chave simples) ou pela combinação de dois ou mais campos (chave composta), de maneira que não existam dois registros com o mesmo valor de chave primária(PK)._

> _AUTOINCREMENT - O auto incremento permite criar um número automaticamente toda vez que um registro é inserido na tabela._

#### Mostrar todas as tabales do banco em uso
```sql
    SHOW TABLES;
```

#### Modificar uma tabela já criada
```sql
    ALTER TABLE teste ADD descricao VARCHAR(255) AFTER nome;
```

> No exemplo, estamos adicionando a coluna `descricao` depois do `nome` na tabela `teste`.

#### Inserir valor na tabela
```sql
    INSERT INTO teste VALUES("Fernando", "Descrição aleatória até 255 caracteres");
```
> Vale ressaltar que o `id` não é para ser adicionado manualmente, poís na criação da tabela, o campo `id` foi definido como `AUTOINCREMENT`, ou seja, toda vez que inserir um valor na tabela o id vai ser gerado automaticamente.

```sql
    INSERT INTO teste(nome, descricao) VALUES ("Bruno", "Descrição para o teste");
```
> Para inserção de valores específicos ou deixando algum campo em branco, é necessário descrever o nome da coluna e o valor a ser inserido.

#### Selecionar todos os registros
```sql
    SELECT * FROM teste;
```

```sql
    SELECT nome FROM teste;
```
> Seleciona todos os registro de apenas uma coluna

#### Selecionar especificando o registro com WHERE
```sql
    SELECT * FROM teste WHERE id = 1;
```
> Seleciona todos os registro onde o `id` é igual a 1.

```sql
    SELECT nome FROM teste WHERE id >= 1;
```
> Seleciona todos os nomes onde o `id` é maior ou igual a 1.

#### Selecionar registros usando LIMIT 
```sql
    SELECT * FROM teste LIMIT 5;
```
> Seleciona apenas 5 linhas da consulta

```sql
    SELECT * FROM teste LIMIT 0, 5;
```
> No segundo exemplo estamos retornando 5 registros, começando do índice 0(No caso, todos os 5 registros começando do `ID` 1 que é a `PK`, pois não temos o índice 0).

#### Selecionar registros usando JOIN

**Usuarios:**
| Usuario | Senha | Setor |
| --- | --- | --- |
| Alice | 665785 | A |
| Antonio | 123456 | C |
| Felipe | 456558| B |
| Leticia | 545613| A |

**Setores:**
| Setor | Cargo |
| --- | --- |
| A | RH |
| B | Desenvolvimento |
| C | Suporte |

> Combinaremos registros de duas tabelas diferentes, Usuarios e Setores

```sql
    SELECT Usuario, Cargo FROM Usuarios JOIN Setores ON Usuarios.Setor = Setores.Setor WHERE Setores.Cargo = "RH";
```
> Na consulta acima queremos o nome dos `Usuários` e o `Cargo` de todos os que tiverem o `cargo` de `RH`.

#### Atualizar uma tabela
```sql
    UPDATE teste SET nome = "Alice" WHERE id = 2;
```
> Vai trocar o nome de `Bruno` para `Alice`, pois o `ID` é referente ao segundo registro na tabela.

#### Remover um registro da tabela
```sql
    DELETE FROM teste WHERE id = 2;
```
> Remove os valores na linha onde o `ID` é igual a 2.

## 📑 Referências

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)
 - [Chave Primária (PK)](https://datasus.saude.gov.br/glossario/chave-primaria-pk/#:~:text=A%20chave%20prim%C3%A1ria%2C%20ou%20Primary,mesmo%20valor%20de%20chave%20prim%C3%A1ria.)
 - [Os 10 comandos SQL que você não pode viver sem!](https://becode.com.br/comandos-sql-nao-pode-viver-sem/)
 - [10 comandos SQL que todo programador tem que conhecer!](https://kenzie.com.br/blog/comandos-sql/)
 - [MySQL – Auto Incremento de valores em colunas – 08](http://www.bosontreinamentos.com.br/mysql/mysql-auto-incremento-de-valores-em-colunas-08/#:~:text=O%20auto%20incremento%20permite%20que,incrementa%20de%201%20em%201.)
 
## 🚀 Outros links

[GitHub Adriellison](https://github.com/adriellison)

[Repositorio do Documento de SQL](https://github.com/adriellison/Reposit-rio-de-SQL)

[Convite para o servidor de estudos LAG](https://discord.gg/Z4RcfxtPYE)
