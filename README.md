# Igor Rocha Lobato

**Automação e IA aplicada a dados.**

Construo agentes autônomos que leem uma demanda, consultam as fontes de verdade,
decidem e executam — com guarda de segurança e trilha de auditoria em cada passo.
Não são scripts que avisam: são agentes que resolvem.

---

### O que eu construo

**Agentes de service desk que fecham o ciclo.** O agente lê o chamado, extrai a
pessoa, confirma a identidade no diretório, cruza com o ERP de folha, executa a
ação (desabilitar acesso, liberar licença, abrir a demanda de devolução de
equipamento na fila certa), escreve a conclusão no chamado e encerra. Rodando
sozinho, em janela agendada, todo dia útil.

**Integração entre sistemas que não conversam.** ERP (TOTVS RM), ITSM
(Freshservice), diretório (Active Directory / Entra ID), BPM (Fluig), BI
(Power BI / Fabric, Smartrics). O trabalho difícil raramente é a API — é
reconciliar entidades que cada sistema identifica de um jeito diferente.

**Camada de dados e BI.** Modelagem, DAX, RLS, rateio de custo por centro de
custo, e os servidores MCP que dão a um agente acesso governado a essas bases.

---

### Como eu construo

A parte que me interessa não é fazer funcionar — é fazer **errar para o lado
reversível**.

| Princípio | Por quê |
|---|---|
| **Decisão separada da execução** | a regra é testável sem tocar em sistema nenhum |
| **Dry-run antes de confirmar** | o ensaio mostra o plano inteiro antes da primeira escrita |
| **Três sinais para identidade** | matrícula, empresa e nome — agir na pessoa errada é o pior erro possível |
| **Idempotência** | o agente roda 6× por dia; rodar duas vezes não pode duplicar nada |
| **Dúvida vira registro, não ação** | sem certeza, ele escreve o porquê e para |
| **Teste travando os dois lados** | se alguém ligar uma guarda que foi desligada por decisão, o teste cai |

Toda regra de negócio no código carrega, em comentário, **o caso real que a
originou** — a data, o número medido, o que teria acontecido sem ela. Código
conta o que faz; o comentário conta por que existe.

---

### Stack

`Python` `PowerShell` `SQL Server` `T-SQL` `DAX`
`Active Directory` `Microsoft Entra ID` `Microsoft Graph`
`TOTVS RM` `Fluig` `Freshservice` `Power BI` `Microsoft Fabric`
`APIs REST` `MCP (Model Context Protocol)` `Git`

---

### Números

**364 commits** em **15 projetos** — agentes de atendimento, clientes de API,
servidores MCP, automação de BI e um terminal embarcado de registro de presença
em C++.

---

<sub>TI & BI · Automação de processos · Agentes de IA em produção</sub>
