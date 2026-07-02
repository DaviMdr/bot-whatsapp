# Bot de Envio Automático de Mensagens via WhatsApp

## Descrição

Este projeto automatiza o envio de mensagens de agradecimento para clientes que visitaram o estabelecimento no dia anterior.

O envio é realizado automaticamente através do WhatsApp Web utilizando Python e a biblioteca `pywhatkit`.

---

# Funcionalidades

- Leitura automática dos contatos em arquivo JSON.
- Conversão dos dados para DataFrame utilizando Pandas.
- Validação do arquivo de entrada.
- Filtragem dos clientes que visitaram no dia anterior.
- Mensagens diferentes para dias úteis e finais de semana.
- Agendamento automático utilizando Schedule.
- Envio das mensagens pelo WhatsApp Web.
- Tratamento de erros durante todo o processo.

---

# Estrutura

```
Projeto
│
├── bot.py
└── contatos.json
```

---

# Estrutura do JSON

```json
[
    {
        "Nome": "João",
        "Telefone": "+5511999999999",
        "Data_Visita": "2026-07-01"
    },
    {
        "Nome": "Maria",
        "Telefone": "+5511988888888",
        "Data_Visita": "2026-07-01"
    }
]
```

---

# Fluxo da Aplicação

```
Inicialização
      │
      ▼
Inicia Scheduler
      │
      ▼
Aguarda horário configurado
      │
      ▼
Lê contatos.json
      │
      ▼
Valida arquivo
      │
      ▼
Filtra visitantes de ontem
      │
      ▼
Seleciona mensagem
      │
      ▼
Abre WhatsApp Web
      │
      ▼
Envia mensagens
      │
      ▼
Aguarda próximo agendamento
```

---

# Tecnologias Utilizadas

- Python
- Pandas
- Schedule
- PyWhatKit
- JSON
- Threading
- Datetime

---

# Regras de Negócio

## Dias úteis

- Executa apenas de segunda a sexta.
- Envia somente durante o horário comercial.
- Utiliza a mensagem padrão para dias úteis.

## Final de semana

- Executa apenas aos sábados e domingos.
- Utiliza mensagem personalizada para finais de semana.

---

# Tratamento de Erros

O sistema valida:

- Existência do arquivo JSON.
- Leitura correta do JSON.
- Estrutura do DataFrame.
- Colunas obrigatórias.
- Conversão das datas.
- Falhas durante o envio das mensagens.

---

# Objetivo

Automatizar o envio de mensagens de agradecimento aos clientes, reduzindo atividades manuais e garantindo que o contato seja realizado de forma consistente e programada.
