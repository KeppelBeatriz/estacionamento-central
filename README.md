# Estacionamento Central 🚗

**Sistema web de gestão de estacionamento — projeto em fase de análise e prototipação.**

> Projeto de portfólio de desenvolvimento de software, elaborado a partir do levantamento de necessidades de um estacionamento de pequeno porte. Os nomes **José** (operador) e **Marcos** (proprietário do lote) são fictícios.

## Visão geral

O Estacionamento Central busca substituir registros manuais em papel por uma aplicação simples para gerenciar vagas, mensalistas, horistas, diaristas, cobranças e prestação de contas. A experiência deve atender a um operador com pouca familiaridade com computadores e celulares.

### Problema

A operação manual dificulta localizar informações, acompanhar pagamentos atrasados, identificar vagas disponíveis e consolidar o fechamento mensal.

### Solução proposta

Uma **aplicação web responsiva**, com interface minimalista e legível, que centraliza as operações diárias e automatiza cálculos e relatórios. O funcionamento offline com sincronização posterior é um requisito identificado, ainda não implementado.

## Funcionalidades planejadas

- Cadastro e consulta de clientes mensalistas, com CPF, telefone e histórico.
- Vínculo de mensalistas a **vagas fixas** de categorias distintas.
- Gestão de vagas reservadas para mensalistas e vagas destinadas a uso avulso.
- Registro de entrada e saída de horistas e cálculo por frações de 30 minutos.
- Registro de diaristas com pagamento antecipado.
- Geração de mensalidades, acompanhamento de vencimentos e registro de pagamentos.
- Fechamento mensal e prestação de contas com divisão financeira entre operador e proprietário do lote.
- Exportação de relatórios em PDF, Excel e formato para impressão.
- Login por CNPJ e PIN de seis dígitos, com proteções adicionais a definir.

## Regras de cobrança identificadas

| Modalidade | Regra |
| --- | --- |
| Mensalista A | Vaga fixa em box coberto; referência de R$ 150/mês, valor vigente a confirmar |
| Mensalista B | Vaga fixa sob cobertura de placas solares; referência de R$ 100/mês |
| Horista | R$ 5/hora, arredondando para cima em frações de 30 minutos |
| Diarista | R$ 28/diária; duração exata a confirmar |

Mensalistas pagam antes do vencimento combinado; diaristas pagam antecipadamente. Vagas destinadas a mensalistas **não** podem ser utilizadas por horistas ou diaristas, mesmo quando não há contrato ativo.

## Prestação de contas

O operador (José) presta contas mensalmente ao proprietário do lote (Marcos). A regra informada é repassar **50% do valor previsto** das modalidades mensalistas A/B e horistas, inclusive quando houver inadimplência. A inclusão e a base de cálculo das diárias, bem como o tratamento de recebimentos tardios, precisam de validação para evitar inconsistências. O repasse é feito por PIX e deve ser registrado.

## Status do projeto

**Em andamento — levantamento inicial concluído, com pendências de validação.** Não há implementação, protótipo final, banco de dados ou integrações concluídas nesta versão da documentação.

| Etapa | Status |
| --- | --- |
| Entrevistas e levantamento inicial | Concluído com pendências |
| Especificação de requisitos | Versão inicial |
| Modelagem de dados | Proposta preliminar |
| Fluxos e arquitetura de telas | Proposta preliminar |
| Protótipo de alta fidelidade | Não iniciado |
| Desenvolvimento e testes | Não iniciado |

## Documentação

- [Requisitos e regras de negócio](docs/REQUISITOS.md)
- [Modelagem preliminar de dados](docs/MODELAGEM.md)
- [Fluxos e mapa de telas](docs/FLUXOS.md)
- [Pendências e decisões em aberto](docs/PENDENCIAS.md)

## Tecnologias

**A definir.** Requisitos técnicos identificados: aplicação web responsiva, autenticação, armazenamento persistente, operação offline e sincronização posterior. Nenhum framework ou banco de dados foi selecionado formalmente.

## Princípios de UX

- Botões grandes, rótulos claros e boa legibilidade.
- Poucas etapas por tarefa; mensagens diretas e confirmação de ações críticas.
- Indicação de status por **texto e cor**, não somente por cor.
- Interface consistente entre celular e computador.

## Próximas etapas

Validar pendências de cobrança e operação; elaborar wireframes; testar os fluxos com o usuário; escolher a stack; implementar um MVP e documentar os testes.

---

**Nota de privacidade:** este repositório não deve conter CPFs, telefones, dados bancários ou registros reais de clientes. Exemplos e capturas devem usar dados fictícios.
