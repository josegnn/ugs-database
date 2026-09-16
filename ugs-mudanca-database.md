## MUDANÇA

- Quando executada no final de semana, deve ser encerrada até as 06h da segunda-feira.
- Caso não concluída dentro da janela, rollback é a regra:
	- A extensão da janela de mudança só é permitida em algumas exceções:
		- Já foi definido que o sistema ficará fora do ar por mais um tempo;
		- O problema é simples de ser resolvido, de forma que extrapolar um pouco a janela é a decisão mais sensata.
	- Lembrando que as decisões fora do fluxo sempre devem ser tomadas após ouvidos o time da CISE.
	- A UGS dá a palavra final sobre seguir ou não o fluxo, mas sempre após ouvidos os colegas técnicos (SEOP, Terceirizada, SINF).

# Gerenciamento de Mudanças (DTI/PF)

## Objetivo

Controlar todo o ciclo de vida das mudanças, garantindo que sejam registradas, analisadas, autorizadas, planejadas, testadas, implementadas, documentadas e revisadas, minimizando riscos, impactos e indisponibilidades dos serviços. 【1-347911】【2-4b43b8】

---

# Tipos de Mudança

## Mudança Padrão

Características:

- Baixo risco e baixo impacto.
- Procedimento previamente definido.
- Pré-aprovada.
- Normalmente utilizada para atividades rotineiras e recorrentes. 【2-4b43b8】

### Janelas

- Segunda a sexta:
  - 12h às 14h
  - 19h às 21h 【2-4b43b8】

### Regras

- Solicitações abertas até 11h entram na janela das 12h.
- Solicitações abertas entre 11h e 17h entram na janela das 19h.
- Se falhar 3 vezes consecutivas, passa a ser tratada como mudança normal.
- Não exige controle no módulo de Gerenciamento de Mudanças do ITSM. 【2-4b43b8】

---

## Mudança Normal

Características:

- Pode causar impacto aos serviços.
- Exige planejamento detalhado.
- Depende de reunião de alinhamento.
- Exige aprovação do CCM (Comitê Consultivo de Mudanças). 【2-4b43b8】

### Janelas

- Terças e quintas:
  - 22h às 06h
- Eventualmente em finais de semana e feriados. 【2-4b43b8】

### Prazos para abertura da RDM

| Execução | Prazo de abertura |
|-----------|------------------|
| Terça-feira | Segunda até 12h |
| Quinta-feira | Quarta até 12h |
| Final de semana | Quinta até 12h |

【2-4b43b8】

### Reuniões de alinhamento

- Segundas e quartas às 14h.
- Quintas às 14h quando houver mudança em final de semana. 【2-4b43b8】

### Aprovação

- Necessário mínimo de **50% + 1** dos membros do CCM.
- Aprovação deve ocorrer até 12h do dia da execução.
- Caso contrário, a mudança é suspensa e reagendada. 【2-4b43b8】【1-347911】

### Produção

- Deve existir homologação prévia.
- A RDM de produção deve referenciar a RDM executada em homologação.
- Produção e homologação não podem ocorrer na mesma janela.
- Exceção: GitLab, Jenkins e Sonar. 【2-4b43b8】

---

## Mudança Emergencial

Características:

- Obrigatoriamente vinculada a um incidente.
- Utilizada apenas para incidentes críticos com impacto ao negócio.
- Aprovação pelo CCME (Comitê Consultivo de Mudanças Emergenciais). 【2-4b43b8】

### Prazo

- Deve ser executada em até 2 horas após abertura da RDM. 【2-4b43b8】

### Aprovação

- Basta a aprovação de um membro do CCME.
- Mudanças originadas pelo Redmine ou solicitadas por membros do CCME já são consideradas aprovadas. 【1-347911】【2-4b43b8】

---

# Regras Gerais

## Registro

Toda mudança deve ser aberta via Portal de Atendimento (RDM). 【2-4b43b8】

## Informações obrigatórias

A RDM deve conter:

- Sistema afetado.
- Ambiente.
- Tipo da mudança.
- Mudanças relacionadas.
- Justificativa.
- Atividades planejadas.
- Equipes envolvidas.
- Análise de impacto.
- Análise de risco.
- Plano de rollback. 【2-4b43b8】

## Homologação

- Toda mudança em produção exige homologação prévia. 【2-4b43b8】

## Rollback

- Deve existir para toda mudança.
- Deve caber dentro da janela prevista.
- Deve ser executado caso a continuidade da mudança seja inviável ou ocorra falha. 【2-4b43b8】【1-347911】

## Solicitantes autorizados

Mudanças em homologação, treinamento ou produção só podem ser solicitadas por integrantes do grupo **"Solicitantes de mudança"**. 【2-4b43b8】

---

# Jenkins

## Obrigatoriedade

Toda mudança via Jenkins deve gerar RDM no ITSM. 【2-4b43b8】

## Execução

- Produção: executada pela DISE.
- Homologação sem necessidade de infraestrutura: executada pela DDS.
- Homologação sem atuação da infraestrutura não precisa respeitar janelas. 【2-4b43b8】

## Produção

Mudança via Jenkins em produção é tratada como mudança padrão, desde que:

- Não gere indisponibilidade.
- Respeite a janela disponível.
- Observe exceções de horário dos sistemas críticos. 【2-4b43b8】

---

# Implantação de Novo Serviço

## Abertura

Criar uma RP (Requisição Planejada):

```
Implantação de novo serviço - <nome do serviço>
```

Anexar obrigatoriamente o Plano de Implantação. 【2-4b43b8】

## Execução

- Cada atividade do plano deve possuir sua própria RDM vinculada à RP.
- Essas RDMs são do tipo padrão e consideradas pré-aprovadas.
- Não precisam obedecer às janelas desde que sigam o cronograma de implantação e não causem impacto aos serviços. 【2-4b43b8】

## Pós-implantação

- Ajustes durante a primeira semana continuam sendo tratados como padrão.
- Após esse prazo, aplicam-se as regras normais da política de mudanças. 【2-4b43b8】

---

# Sistemas com Horários Preferenciais

| Sistema | Horário preferencial |
|----------|--------------------|
| ePol | Segunda a quinta, a partir de 19h |
| Corporativo | Segunda a quinta, a partir de 19h |
| Corporativo-Rest | Segunda a quinta, a partir de 19h |
| PROMASP | A partir de 23h |
| SINPA | A partir de 23h |
| SIS Placas | A partir de 02h |
| CINTEPOL | Quintas, 18h às 22h |

【2-4b43b8】

---

# Papéis e Responsabilidades

## Gerente de Mudanças

- Coordenar o processo.
- Registrar mudanças normais e emergenciais.
- Convocar CCM e CCME.
- Monitorar indicadores.
- Garantir documentação.
- Acompanhar execução e qualidade.
- Comunicar mudanças e aprovações. 【1-347911】

## Equipe Técnica / Executor

- Planejar e executar a mudança.
- Informar riscos e impactos.
- Executar rollback quando necessário.
- Participar de reuniões de planejamento. 【1-347911】

## CCM

- Avaliar e aprovar mudanças normais.
- Definir prioridades quando necessário. 【1-347911】

## CCME

- Avaliar e aprovar mudanças emergenciais.
- Assumir os riscos da execução emergencial. 【1-347911】

---

# Fluxo Resumido

## Padrão

1. Abrir RDM.
2. Validar informações.
3. Agendar.
4. Executar.
5. Validar.
6. Rollback (se necessário).
7. Encerrar. 【1-347911】

## Normal

1. Abrir RDM.
2. Validar informações.
3. Planejar.
4. Reunião de alinhamento.
5. Aprovação do CCM.
6. Comunicação aos envolvidos.
7. Execução.
8. Validação.
9. Rollback (se necessário).
10. Encerramento. 【1-347911】

## Emergencial

1. Abrir RDM vinculada a incidente.
2. Avaliar risco e impacto.
3. Registrar e aprovar via CCME.
4. Comunicação.
5. Execução.
6. Validação.
7. Rollback (se necessário).
8. Encerramento. 【1-347911】

---

# Métricas do Processo

- % de mudanças emergenciais.
- % de mudanças padrão.
- % de mudanças normais.
- % de mudanças não autorizadas.
- % de mudanças que exigiram rollback.
- Mudanças por solicitante.
- Mudanças por sistema/serviço.
- Mudanças canceladas. 【1-347911】

---

# Ferramentas Utilizadas

- ITSM (registro, aprovação, acompanhamento e relatórios).
- Microsoft Teams (comunicações operacionais).
- Jenkins (integração de implantações).
- Redmine (origem de algumas mudanças emergenciais). 【1-347911】【2-4b43b8】
