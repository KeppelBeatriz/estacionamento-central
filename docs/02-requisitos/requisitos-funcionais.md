# Requisitos funcionais e critérios de aceitação



Status **Confirmado** significa que a necessidade foi informada; não significa funcionalidade implementada. **Proposto** indica detalhamento sugerido e sujeito a validação.

| ID | Requisito | Status |
| --- | --- | --- |
| RF01 | Cadastrar mensalista com nome, CPF, telefone/WhatsApp, data de cadastro e observações | Confirmado |
| RF02 | Buscar cliente por nome ou CPF | Confirmado |
| RF03 | Editar e inativar cliente preservando histórico | Confirmado |
| RF04 | Registrar contratos com vaga fixa, modalidade A/B, preço e dia de vencimento | Confirmado |
| RF05 | Manter histórico de alterações cadastrais e contratuais | Confirmado |
| RF06 | Cadastrar vagas numeradas e classificá-las por modalidade e cobertura | Confirmado |
| RF07 | Exibir vagas disponíveis para contratação mensal e para utilização avulsa separadamente | Confirmado |
| RF08 | Impedir alocação avulsa em vagas destinadas a mensalistas | Confirmado |
| RF09 | Registrar entrada de horista com placa, data/hora e vaga | Confirmado |
| RF10 | Registrar saída selecionando o veículo e calcular tempo de permanência | Confirmado |
| RF11 | Calcular cobrança horista em frações iniciadas de 30 minutos | Confirmado |
| RF12 | Atualizar ocupação das vagas com entradas e saídas | Confirmado |
| RF13 | Registrar utilização por diária de R$ 28, com pagamento antecipado | Confirmado; duração pendente |
| RF14 | Gerar cobranças mensais automaticamente | Confirmado |
| RF15 | Registrar pagamento selecionando o cliente | Confirmado |
| RF16 | Registrar PIX, dinheiro, débito, crédito e transferência bancária | Confirmado |
| RF17 | Identificar cobranças vencidas automaticamente | Confirmado |
| RF18 | Permitir data de pagamento excepcionalmente combinada | Confirmado; efeitos no atraso pendentes |
| RF19 | Exibir competência e status de cobrança no histórico do cliente | Confirmado |
| RF20 | Exibir totais e indicadores financeiros | Confirmado |
| RF21 | Gerar fechamento mensal com mensalistas A/B, horistas, pendências e valor de Marcos | Confirmado |
| RF22 | Calcular repasse de Marcos como 50% do valor previsto | Confirmado; base de avulsos pendente |
| RF23 | Registrar repasse a Marcos com data, valor e meio de pagamento (PIX) | Confirmado |
| RF24 | Exportar prestação de contas em PDF, Excel e formato para impressão | Confirmado |
| RF25 | Comparar meses por gráficos e indicadores | Confirmado |
| RF26 | Permitir correções em fechamento mantendo auditoria | Confirmado |
| RF27 | Disponibilizar autenticação para acesso do operador; método ainda a definir | Confirmado quanto à necessidade; método pendente |
| RF28 | Disponibilizar operação offline com sincronização posterior | Confirmado; estratégia técnica a definir |
| RF29 | Oferecer tela de registro com seleção de modalidade e vaga elegível | Proposto a partir do fluxo descrito |
| RF30 | Permitir ajuste de tarifas de todas as modalidades ao longo do tempo preservando histórico | Confirmado |


## Critérios de aceitação preliminares


1. Uma vaga reservada para mensalista não aparece como elegível para registro de horista ou diarista.
2. Para um horista com permanência de 70 minutos, a cobrança-base calculada é R$ 7,50.
3. Ao registrar uma entrada avulsa, a vaga passa a aparecer como ocupada; não é possível alocar outro veículo nela simultaneamente.
4. Ao registrar uma saída, o sistema calcula o valor e atualiza a disponibilidade da vaga, respeitando a regra de confirmação de pagamento ainda pendente.
5. Uma mensalidade ativa é gerada para sua competência sem duplicidade.
6. Um pagamento pode ser associado à competência correta, inclusive quando recebido em mês posterior.
7. O relatório mensal diferencia valores previstos, recebidos, atrasados e repasses a Marcos.
8. Uma alteração posterior ao fechamento conserva quem alterou, quando e o que mudou.
