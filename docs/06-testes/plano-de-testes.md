# Plano de testes — rascunho

**Estado:** planejado; testes ainda não executados.

| Caso | Pré-condição | Ação | Resultado esperado |
| --- | --- | --- | --- |
| CT01 | Vaga mensalista livre de contrato | Tentar registrar horista | Vaga não aparece como elegível |
| CT02 | Tarifa horista R$ 5/h | Registrar saída após 70 min | Valor de R$ 7,50 |
| CT03 | Mensalidade outubro R$ 150 | Reajustar para R$ 170 em novembro | Outubro continua R$ 150 |
| CT04 | Vaga avulsa ocupada | Tentar segunda entrada na mesma vaga | Registro impedido |
| CT05 | Mensalidade já gerada | Executar geração novamente | Sem cobrança duplicada |
| CT06 | Fechamento concluído | Corrigir lançamento | Alteração auditada |

**Atenção:** casos envolvendo diária, tolerância e repasses dependem de validação de regras.
