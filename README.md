# Estacionamento Central 🚗

**Sistema web de gestão de estacionamento — projeto em fase de análise e prototipação.**

> Projeto de portfólio elaborado a partir de necessidades de um **estabelecimento real**, o Estacionamento Central, em **Itatiaiuçu, Minas Gerais**. **José** (operador) e **Marcos** (proprietário do lote) são pseudônimos para preservar a identidade das pessoas envolvidas.

## Contexto

O estabelecimento utiliza registros manuais em papel para organizar vagas, mensalistas, horistas, diaristas e a prestação de contas. A proposta é criar uma aplicação web responsiva, simples e legível, adequada a um operador com pouca familiaridade digital.

## Funcionalidades planejadas

- Cadastro de mensalistas e vínculo com vagas fixas.
- Separação entre vagas de mensalistas e vagas para horistas/diaristas.
- Entrada e saída de horistas, com cálculo por frações de 30 minutos.
- Registro de diárias com pagamento antecipado.
- Geração de mensalidades, acompanhamento de vencimentos e registro de pagamentos.
- Tarifas **configuráveis para todas as modalidades**, com histórico de reajustes.
- Fechamento financeiro, registro de repasses e relatórios PDF/Excel/impressão.
- Operação offline com sincronização posterior (**requisito; não implementado**).
- Autenticação (**método ainda não definido**).

## Regras de cobrança

| Modalidade | Regra identificada |
| --- | --- |
| Mensalista A | Vaga fixa em box coberto; tarifa configurável |
| Mensalista B | Vaga fixa sob cobertura de placas solares; tarifa configurável |
| Horista | Tarifa atual R$ 5/h, cobrada em frações iniciadas de 30 minutos; tarifa configurável |
| Diarista | Tarifa atual R$ 28/diária, configurável; duração da diária pendente de confirmação |

Mensalistas pagam **até a data de vencimento combinada**; diaristas pagam antecipadamente. Vagas destinadas a mensalistas **não** podem ser usadas por horistas ou diaristas, mesmo sem contrato ativo. O momento do pagamento de horistas ainda não foi confirmado.

**Reajustes:** o valor de cada cobrança deve ser preservado por competência. Exemplo: outubro R$ 150 e novembro R$ 170, sem alterar outubro.

## Prestação de contas

O operador presta contas mensalmente ao proprietário do lote. A regra informada é o repasse de **50% do valor previsto** das mensalidades A/B e horistas, inclusive em caso de inadimplência. A inclusão de diárias, a definição da base prevista dos avulsos e a conciliação de pagamentos atrasados permanecem **pendentes de validação**. Os repasses são realizados por PIX e devem ser registrados.

## Status

| Etapa | Estado |
| --- | --- |
| Levantamento inicial | Concluído com pendências |
| Requisitos e regras de negócio | Especificação inicial |
| Modelagem e processos | Propostas preliminares |
| Interface e arquitetura | Em definição |
| Implementação e testes | Não iniciados |

## Documentação

Consulte o [índice completo da documentação](docs/README.md).

## Tecnologias

**A definir.** O produto deverá ser web responsivo, com armazenamento persistente e sincronização offline. Não há framework, banco de dados nem método de login formalmente selecionado.

## Diretrizes de UX

Botões amplos, textos claros, bom contraste, poucas etapas e indicadores de situação por texto e cor. A tela inicial e a navegação ainda serão validadas com o operador.

## Próximos passos

Validar pendências de cobrança e capacidade; produzir wireframes; testar fluxos com o usuário; escolher a stack; implementar e testar um MVP.

> Esta documentação descreve necessidades e propostas. **Não representa funcionalidades já implementadas.**
