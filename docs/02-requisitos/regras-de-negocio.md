# Regras de negócio



| ID | Regra | Estado |
| --- | --- | --- |
| RN01 | Cada mensalista escolhe uma vaga fixa | Confirmada |
| RN02 | Mensalista A: box coberto convencional; mensalista B: cobertura de placas solares | Confirmada |
| RN03 | Vagas mensalistas não são usadas por horistas ou diaristas, ainda que desocupadas | Confirmada |
| RN04 | Horista: R$ 5 por hora, em frações iniciadas de 30 minutos, com arredondamento para cima | Confirmada |
| RN05 | Diária: R$ 28; período de validade não definido | Parcial |
| RN06 | Mensalistas pagam até a data de vencimento combinada | Confirmada |
| RN07 | Diaristas pagam antecipadamente | Confirmada |
| RN08 | Cada mensalista tem seu próprio dia de vencimento | Confirmada |
| RN09 | Cobranças mensais são geradas automaticamente | Confirmada |
| RN10 | Cobranças não pagas após vencimento são identificadas como atrasadas | Confirmada; acordos excepcionais precisam de regra |
| RN11 | Não são aplicados descontos nem alterações individuais de preço | Confirmada |
| RN12 | Tarifas de todas as modalidades são configuráveis e podem ser reajustadas com vigência e preservação do histórico | Confirmada |
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


## Política de tarifas e competência


- Tarifas de mensalistas A/B, horistas e diaristas podem ser alteradas.
- Cada alteração deve possuir valor e início de vigência.
- Cobranças já emitidas devem preservar o valor registrado para a competência, salvo correção auditada.
- Exemplo: mensalidade A de outubro R$ 150 e de novembro R$ 170; outubro permanece R$ 150.
- Reajustes individuais não foram autorizados; confirmar se o reajuste por modalidade se aplica a todos os contratos.
- A tarifa vigente deve ser capturada no momento da geração da cobrança/permanência, sem recalcular histórico.
