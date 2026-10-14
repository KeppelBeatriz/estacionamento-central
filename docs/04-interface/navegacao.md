# Navegação proposta



```mermaid
flowchart TD
    A[Autenticação: método a definir] --> B[Início]
    B --> C[Vagas]
    B --> D[Registrar vaga]
    B --> E[Mensalistas]
    B --> F[Horistas e diaristas]
    B --> G[Pagamentos]
    B --> H[Financeiro]
    B --> I[Configurações]
    D --> J{Modalidade?}
    J --> K[Mensalista]
    J --> L[Horista]
    J --> M[Diarista]
    K --> N[Selecionar vaga elegível]
    L --> N
    M --> N
    N --> O[Preencher dados e confirmar]
    H --> P[Fechamento e prestação de contas]
```

> **A tela inicial ainda não foi escolhida.** Alternativas em avaliação: lista de vagas em destaque, painel misto ou ações rápidas em destaque. O menu também não está definido.


## Estado

Navegação e tela inicial ainda não foram aprovadas pelo cliente.
