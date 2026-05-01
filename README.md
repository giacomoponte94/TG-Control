# TG Control

Painel web para controle de estoque, receita e despesas, com autenticação via Firebase.

## Funcionalidades

- Login com email e senha (Firebase Auth)
- Dashboard com Estoque (mg), Receita, Despesa e Lucro em tempo real
- Operações atômicas via Firestore Transaction:
  - **Venda** — desconta estoque e registra receita
  - **Compra** — adiciona estoque e registra despesa
  - **Despesa** — registra despesa sem movimentar estoque

## Estrutura do Firestore

```
app/dados
  ├── estoque_mg:    number
  ├── receita_total: number
  └── despesa_total: number
```

## Como usar

Abra o `index.html` diretamente no navegador ou sirva via qualquer servidor HTTP estático.

> **Atenção:** as credenciais do Firebase estão embutidas no HTML porque esta é uma aplicação client-side. Proteja o acesso configurando as [regras de segurança do Firestore](https://firebase.google.com/docs/firestore/security/get-started) para permitir leitura/escrita apenas a usuários autenticados.
