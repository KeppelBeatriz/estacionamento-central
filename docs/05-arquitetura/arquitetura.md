# Arquitetura da solução — proposta preliminar

**Estado:** a definir. Não há stack, banco de dados, provedor ou método de autenticação selecionado.

## Requisitos arquiteturais

- Aplicação web responsiva.
- Persistência e proteção de dados pessoais.
- Funcionamento offline com sincronização posterior.
- Controle de conflitos ao registrar a mesma vaga em dispositivos distintos.
- Histórico de alterações financeiras e de tarifas.
- Exportação de relatórios PDF, Excel e impressão.

## Questões técnicas abertas

1. Qual tecnologia de frontend e backend atende melhor à equipe?
2. Qual banco de dados e estratégia de backup?
3. Como autenticar e recuperar acesso com segurança?
4. Quais operações podem ser feitas offline e como conciliar conflitos?
5. Como garantir idempotência na geração mensal de cobranças?

As escolhas deverão ser justificadas por registros de decisão arquitetural (ADR).
