# Especificação de requisitos — Estacionamento Central

**Versão:** 0.1 | **Status:** análise inicial | **Fonte:** entrevistas e esclarecimentos fornecidos durante o levantamento.

## 1. Escopo e atores

- **José (nome fictício):** único usuário operacional previsto; cadastra, consulta, cobra e presta contas.
- **Marcos (nome fictício):** proprietário do lote e destinatário da prestação de contas; não há acesso próprio ao sistema previsto.
- **Mensalista:** cliente com vaga fixa e cobrança recorrente.
- **Horista:** usuário avulso cobrado pelo tempo estacionado.
- **Diarista:** usuário avulso com tarifa por diária.

## 2. Requisitos funcionais

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
| RF27 | Autenticar operador por CNPJ e PIN de seis dígitos | Confirmado; medidas de proteção a definir |
| RF28 | Disponibilizar operação offline com sincronização posterior | Confirmado; estratégia técnica a definir |
| RF29 | Oferecer tela de registro com seleção de modalidade e vaga elegível | Proposto a partir do fluxo descrito |
| RF30 | Permitir ajuste de tarifas gerais ao longo do tempo preservando histórico | Confirmado |

## 3. Regras de negócio

| ID | Regra | Estado |
| --- | --- | --- |
| RN01 | Cada mensalista escolhe uma vaga fixa | Confirmada |
| RN02 | Mensalista A: box coberto convencional; mensalista B: cobertura de placas solares | Confirmada |
| RN03 | Vagas mensalistas não são usadas por horistas ou diaristas, ainda que desocupadas | Confirmada |
| RN04 | Horista: R$ 5 por hora, em frações iniciadas de 30 minutos, com arredondamento para cima | Confirmada |
| RN05 | Diária: R$ 28; período de validade não definido | Parcial |
| RN06 | Mensalistas pagam antes do vencimento combinado | Confirmada |
| RN07 | Diaristas pagam antecipadamente | Confirmada |
| RN08 | Cada mensalista tem seu próprio dia de vencimento | Confirmada |
| RN09 | Cobranças mensais são geradas automaticamente | Confirmada |
| RN10 | Cobranças não pagas após vencimento são identificadas como atrasadas | Confirmada; acordos excepcionais precisam de regra |
| RN11 | Não são aplicados descontos nem alterações individuais de preço | Confirmada |
| RN12 | Reajustes gerais de tarifa são possíveis | Confirmada |
| RN13 | Marcos recebe 50% do valor previsto de mensalistas A/B e horistas, mesmo com inadimplência | Confirmada como intenção; composição exata a validar |
| RN14 | Prestação de contas é mensal; repasses por PIX | Confirmada |
| RN15 | Pagamentos atrasados são vinculados ao mês de competência original | Confirmada; conciliação de caixa a definir |
| RN16 | Não haverá controle de despesas operacionais nesta versão | Confirmada |
| RN17 | Alterações em fechamentos devem manter trilha de auditoria | Confirmada |

### 3.1 Fórmula horista

Para permanência positiva, **valor = teto(minutos / 30) × R$ 2,50**.

Exemplo confirmado: 1h10 = 70 minutos → 3 frações → **R$ 7,50**.

**Atenção:** tolerância, arredondamento em casos especiais e interação com a tarifa diária não foram definidos.

### 3.2 Prestação de contas

- Valor previsto, valor recebido e saldo pendente são métricas diferentes.
- **Repasse devido a Marcos = 50% × base prevista validada.**
- **Saldo a repassar = repasse devido − repasses registrados**, sujeito a ajustes auditados.
- Não se deve presumir que toda entrada de caixa do mês pertença à competência do mês.
- A composição da base prevista dos horistas/diaristas e o tratamento de pagamentos tardios ainda exigem decisão formal.

## 4. Requisitos não funcionais

| ID | Requisito | Status |
| --- | --- | --- |
| RNF01 | Aplicação web responsiva para computador e celular | Confirmado |
| RNF02 | Interface minimalista, elegante, legível e autoexplicativa | Confirmado |
| RNF03 | Ações com botões grandes, rótulos claros e poucos passos | Proposto para atender perfil do operador |
| RNF04 | Indicadores de situação por texto e cor | Confirmado |
| RNF05 | Autenticação protegida contra tentativas excessivas e exposição do PIN | Proposto; necessário validar solução |
| RNF06 | Proteção de dados pessoais e controle de acesso | Necessidade técnica/legal |
| RNF07 | Operação offline com sincronização e tratamento de conflitos | Confirmado; arquitetura pendente |
| RNF08 | Preservação do histórico financeiro e trilha de alterações | Confirmado |
| RNF09 | Cópias de segurança e recuperação de dados | Recomendado; pendente de decisão |

## 5. Critérios de aceitação preliminares

1. Uma vaga reservada para mensalista não aparece como elegível para registro de horista ou diarista.
2. Para um horista com permanência de 70 minutos, a cobrança-base calculada é R$ 7,50.
3. Ao registrar uma entrada avulsa, a vaga passa a aparecer como ocupada; não é possível alocar outro veículo nela simultaneamente.
4. Ao registrar uma saída, o sistema calcula o valor e atualiza a disponibilidade da vaga, respeitando a regra de confirmação de pagamento ainda pendente.
5. Uma mensalidade ativa é gerada para sua competência sem duplicidade.
6. Um pagamento pode ser associado à competência correta, inclusive quando recebido em mês posterior.
7. O relatório mensal diferencia valores previstos, recebidos, atrasados e repasses a Marcos.
8. Uma alteração posterior ao fechamento conserva quem alterou, quando e o que mudou.

## 6. Fora do escopo confirmado

- Controle de despesas operacionais.
- Portal ou login separado para Marcos.
- Cadastro obrigatório e detalhado de todos os veículos dos mensalistas.
- Emissão de nota fiscal, integração bancária e envio automático de cobrança por WhatsApp.

Itens não confirmados não devem ser tratados como funcionalidades entregues.
