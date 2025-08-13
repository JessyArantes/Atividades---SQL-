## Conceitos de banco de dados (tabelas, colunas, linhas, PK, FK

### 1️⃣ **Tabelas**

- Pense numa **planilha do Excel**: cada aba é uma **tabela**.
- É onde os dados ficam armazenados de forma estruturada.
- Exemplo: `clientes`, `produtos`, `vendas`.

### 2️⃣ **Colunas** (ou campos / atributos)

- Cada coluna representa **um tipo de informação** que será guardada.
- Definem o que pode ser armazenado em cada registro.
- Exemplo na tabela `clientes`:
    - `id_cliente`
    - `nome`
    - `email`
    - `data_nascimento`

### 3️⃣ **Linhas** (ou registros / tuplas)

- Cada linha é **uma entrada específica** na tabela.
- Corresponde a um conjunto de valores para as colunas.
- Exemplo na tabela `clientes`:

### 4️⃣ **Chave Primária (PK — Primary Key)**

- É uma **coluna (ou conjunto de colunas)** que identifica **de forma única** cada linha da tabela.
- Não pode se repetir e não pode ser nula.
- Exemplo: `id_cliente` na tabela `clientes`.

### 5️⃣ **Chave Estrangeira (FK — Foreign Key)**

- É uma coluna que cria **um vínculo entre duas tabelas**.
- Faz referência à **PK** de outra tabela.
- Serve para manter a **integridade referencial** (não deixar dados “órfãos”).
- Exemplo: na tabela `vendas`, a coluna `id_cliente` é **FK** que aponta para `clientes.id_cliente`.

# Tipos de dados (INT, VARCHAR, DATE, DECIMAL, TEXT, etc.)

## **1. Numéricos**

| Tipo | Descrição | Exemplo |
| --- | --- | --- |
| **INT** | Número inteiro (positivo ou negativo) até ~±2 bilhões. | `25`, `-300` |
| **BIGINT** | Inteiro maior que o `INT` (±9 quintilhões). | `9876543210` |
| **SMALLINT** | Inteiro menor (±32 mil) para economizar espaço. | `2500` |
| **TINYINT** | Inteiro muito pequeno (±128) — útil para flags (0/1). | `1` |
| **DECIMAL(p,s)** ou **NUMERIC** | Número exato com casas decimais. `p` = total de dígitos, `s` = casas decimais. | `DECIMAL(10,2)` → `12345.67` |
| **FLOAT** | Número com ponto flutuante (aproximado, menos preciso). | `3.1416` |
| **DOUBLE** / **REAL** | Similar ao FLOAT, mas com mais precisão. | `123456.789012` |

## **2. Texto**

| Tipo | Descrição | Exemplo |
| --- | --- | --- |
| **CHAR(n)** | Texto de tamanho fixo, completa com espaços. | `CHAR(5)` → `'AB   '` |
| **VARCHAR(n)** | Texto de tamanho variável (mais comum). | `'Maria'` |
| **TEXT** | Texto longo (até 65.535 caracteres). | Texto de descrição de produto |
| **MEDIUMTEXT** | Texto ainda maior (até 16 milhões de caracteres). | Artigo completo |
| **LONGTEXT** | Texto gigantesco (até 4 bilhões de caracteres). | Livro inteiro |

## **3. Data e Hora**

| Tipo | Descrição | Exemplo |
| --- | --- | --- |
| **DATE** | Apenas data (`YYYY-MM-DD`). | `2025-08-12` |
| **DATETIME** | Data + hora (`YYYY-MM-DD HH:MM:SS`). | `2025-08-12 19:42:00` |
| **TIMESTAMP** | Data/hora com fuso horário, atualiza automático se configurado. | `2025-08-12 22:00:00` |
| **TIME** | Apenas hora (`HH:MM:SS`). | `15:30:00` |
| **YEAR** | Apenas ano (`YYYY`). | `2025` |

## **4. Outros tipos úteis**

| Tipo | Descrição | Exemplo |
| --- | --- | --- |
| **BOOLEAN** / **BOOL** | Armazena verdadeiro/falso (na prática é `TINYINT(1)`). | `TRUE`, `FALSE` |
| **ENUM** | Lista de valores pré-definidos (só aceita o que estiver na lista). | `ENUM('Pequeno', 'Médio', 'Grande')` |
| **SET** | Lista de valores pré-definidos que pode aceitar múltiplos. | `SET('A', 'B', 'C')` → `'A,B'` |
| **BLOB** | Dados binários (imagens, arquivos). | Arquivo `.jpg` armazenado no banco |

# Comandos aprendidos até o momento

 **Criando banco de dados**

- Comandos: `CREATE DATABASE`, `USE`
- Criar um novo banco e selecionar para uso.

**Criando tabelas**

- Comando: `CREATE TABLE`
- Definir colunas, tipos de dados e chaves primárias.

 **Inserindo dados**

- Comando: `INSERT INTO`
- Adicionar registros nas tabelas.

**Alterando tabelas**

- Comando: `ALTER TABLE`
- Adicionar, remover ou modificar colunas e chaves.

**Removendo dados e tabelas**

- Comandos: `DELETE`, `DROP`
- Excluir registros de uma tabela ou apagar uma tabela inteira.

# Entendendo NULL, NOT NULL, DEFAULT, AUTO_INCREMENT

## **NULL**

- Significa **ausência de valor** (não é zero, nem string vazia).
- Uma coluna que permite `NULL` pode ficar sem valor definido na inserção.

## **NOT NULL**

- Obriga que a coluna **sempre tenha um valor**.
- Usado para evitar campos em branco.

## **DEFAULT**

- Define um **valor padrão** para a coluna, caso não seja informado na inserção.

## **AUTO_INCREMENT**

- Faz com que o valor da coluna seja **gerado automaticamente** e aumente a cada novo registro.
- Normalmente usado para chaves primárias (`PRIMARY KEY`).
