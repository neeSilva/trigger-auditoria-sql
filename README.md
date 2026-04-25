# Sistema de Auditoria com Triggers
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=oracle&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-003B57?style=for-the-badge&logo=ql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-success?style=for-the-badge)

> Implementação prática de um sistema de auditoria (Change Data Capture) utilizando PL/SQL. O projeto automatiza o rastreamento de operações DML (`INSERT`, `UPDATE`, `DELETE`) garantindo o histórico e a governança dos dados.
Projeto FIAP.

## Funcionalidades Desenvolvidas

- [x] Criação de tabelas transacionais e tabelas de log/auditoria (DDL).
- [x] Desenvolvimento de Trigger `FOR EACH ROW`.
- [x] Captura automatizada de estado (`:OLD` e `:NEW`).
- [x] Rastreabilidade por tipo de operação DML.

## Tecnologias Utilizadas
* **Banco de Dados:** Oracle Database
* **Linguagem:** PL/SQL

## Estrutura dos Scripts

O projeto foi dividido em etapas lógicas para facilitar a execução e o entendimento:

1. `01_DDL_Criacao_Tabelas.sql`: Cria a tabela principal e a tabela de log de auditoria no esquema apropriado (ex: `AUDMC`).
2. `02_Trigger_Auditoria.sql`: Contém a lógica PL/SQL da trigger que monitora as alterações em tempo real.
3. `03_DML_Testes_Operacionais.sql`: Bateria de testes contendo 3 Inserts, 3 Updates e 1 Delete.
4. `04_DQL_Validacao.sql`: Query (`SELECT`) para visualização do histórico gerado na tabela de log.

## Como testar no seu ambiente

Para executar este projeto, rode os scripts na ordem numérica no seu cliente Oracle (como o Oracle SQL Developer ou DBeaver). 

Exemplo da saída esperada ao rodar a query de validação final:

```sql
-- Consultando os logs gerados automaticamente pela Trigger
SELECT * FROM T_MC_CARTAO_CREDITO_CLI_LOG ORDER BY ID_LOG;
```
<img width="1911" height="416" alt="Captura de tela 2026-04-10 020042" src="https://github.com/user-attachments/assets/e7623e1b-bdf2-44c0-8f91-84e84d2fec34" />
