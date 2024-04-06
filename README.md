# Construa-um-Projeto-L-gico-de-Banco-de-Dados-do-Zero
**Projeto de Banco de Dados para Oficina Automotiva**

Como protagonista deste projeto, vou criar o esquema lógico para uma oficina automotiva. Seguirei as etapas desde o esquema conceitual até a implementação do banco de dados. Utilizarei o modelo relacional para modelar o esquema.

### Esquema Conceitual (Modelo ER)

Antes de criarmos o esquema lógico, vamos relembrar o esquema conceitual que desenvolvemos no desafio anterior. O modelo ER representa as entidades, relacionamentos e atributos relevantes para nossa oficina. Certifique-se de que seu esquema conceitual esteja completo e bem definido.

### Esquema Lógico

Agora, traduziremos o esquema conceitual em um esquema lógico. Definiremos as tabelas, seus atributos e relacionamentos. Aqui estão algumas tabelas que podem fazer parte do nosso esquema:

1. **Clientes**: Armazenará informações sobre os clientes da oficina, como nome, endereço, telefone, etc.
2. **Veículos**: Contém detalhes sobre os veículos atendidos na oficina, como marca, modelo, ano, placa, etc.
3. **Ordens de Serviço**: Registra os serviços solicitados pelos clientes para seus veículos. Pode incluir data, descrição do serviço, peças necessárias, etc.
4. **Mecânicos**: Mantém informações sobre os mecânicos da oficina, como nome, especialização, experiência, etc.
5. **Peças**: Armazena dados sobre as peças de reposição disponíveis na oficina.

### Script SQL para Criação do Esquema

Agora, criaremos o script SQL para criar as tabelas do nosso esquema. Certifique-se de definir as chaves primárias, chaves estrangeiras e restrições necessárias. Aqui está um exemplo simplificado:

```sql
CREATE TABLE Clientes (
    ClienteID INT PRIMARY KEY,
    Nome VARCHAR(100),
    Endereco VARCHAR(200),
    Telefone VARCHAR(20)
);

CREATE TABLE Veiculos (
    VeiculoID INT PRIMARY KEY,
    Marca VARCHAR(50),
    Modelo VARCHAR(50),
    Ano INT,
    Placa VARCHAR(10)
);

-- Continue criando outras tabelas...

-- Exemplo de junção entre tabelas:
SELECT c.Nome, v.Marca
FROM Clientes c
JOIN Veiculos v ON c.ClienteID = v.ClienteID
WHERE v.Ano >= 2010;
```

### Queries SQL

Agora, vamos elaborar algumas queries SQL com as cláusulas solicitadas:

1. **Recuperações Simples com SELECT Statement**:
   - Recupere todos os clientes cadastrados na oficina.
   - Liste os veículos atendidos pela oficina.

2. **Filtros com WHERE Statement**:
   - Encontre os veículos fabricados após 2015.
   - Identifique os clientes que residem na cidade de Tóquio.

3. **Expressões para Gerar Atributos Derivados**:
   - Calcule a idade média dos veículos atendidos.

4. **Ordenações dos Dados com ORDER BY**:
   - Ordene os clientes por ordem alfabética de nome.
   - Liste os veículos em ordem decrescente de ano de fabricação.

5. **Condições de Filtros aos Grupos – HAVING Statement**:
   - Encontre os mecânicos que realizaram mais de 10 serviços.

6. **Junções entre Tabelas para Perspectiva Complexa dos Dados**:
   - Liste os serviços realizados para cada veículo, incluindo detalhes do cliente e mecânico responsável.
