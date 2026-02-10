# Fluxo Certificação — Sankhya ABC Paulista

**Versão:** 1.0  
**Atualizado em:** 10/02/2026  
**Objetivo:** Padronizar como **solicitar, validar e agendar** certificações (Usuário-chave, Gerenciais e Usuário Técnico/TI), garantindo **aderência ao contrato** e o requisito obrigatório de **base de testes replicada do Produção**.

---

## Fatos rápidos

- **Novo projeto:** solicitação via **Experience** (vinculação do projeto/gestões ocorre por lá).
- **Projeto de base / troca de usuário-chave / Usuário Técnico (TI):** solicitação via **Sanqueon** → tela **“Solicitação de Matrículas Universidade”**.
- **SLA Universidade:** até **5 dias úteis** para tratar/validar a solicitação.
- **Requisito mais crítico para agendar:** **base de testes replicada do Produção** (sem isso, não agenda).
- **Agendamento:** Universidade agenda **direto com o cliente**; se não houver retorno, a unidade faz a ponte.
- **Elegibilidade:** só vale para clientes que **possuem a Plataforma da Universidade no contrato** (contratos muito antigos podem não ter).

---

## 1) Pré-check (antes de abrir solicitação)

1. **Conferir contrato**
   - Cliente possui **Plataforma da Universidade**?
   - Quais **processos/gestões/módulos** estão incluídos?
2. **Definir o tipo**
   - Usuário-chave (por processo/área)
   - Gerenciais
   - Usuário Técnico / Certificação de TI (equivale ao usuário técnico)
3. **Garantir contatos**
   - Nome, e-mail e principalmente **telefone do líder do projeto**.
4. **Base de teste**
   - Alinhar desde já com o cliente: **precisa ser replicada do Produção**.

---

## 2) Decisão: por onde abrir a solicitação

| Cenário | Onde abrir | Observações |
|---|---|---|
| **Novo projeto** | **Experience** | Vinculação ocorre por lá. Gerenciais normalmente já entram via Experience. |
| **Projeto de base / troca de usuário-chave** | **Sanqueon → Solicitação de Matrículas Universidade** | Universidade valida e trata em até 5 dias úteis. |
| **Usuário Técnico / Certificação de TI** | **Sanqueon → Solicitação de Matrículas Universidade** | Em geral, **1 técnico por empresa** (salvo compra adicional). Certifica tudo do contrato. |

---

## 3) Sanqueon — como preencher “Solicitação de Matrículas Universidade”

> Baseado no manual interno “Solicitação de Matrículas Universidade (V03)”.

### Passo a passo
1. Acessar a tela **Solicitação de Matrículas Universidade** e clicar em **Novo Registro**.
2. Preencher **Dados do Parceiro** e **Salvar**.
3. Após salvar, **anexar** o documento **“1.3 - Definição da Equipe do Projeto (Versão 01)”** (quando aplicável).
4. Aba **Contatos**: incluir os usuários a habilitar:
   - **Cód. Contato** (precisa estar **Ativo** em Parceiros)
   - **Perfil Contato**: *Dono do Processo* (acompanhado pela unidade) ou *Usuário Adicional* (habilitado pela Universidade)
   - **Tipo Usuário Adicional**: *Chave* ou *Líder*
   - **Qtd. Área Gestão**
5. Regra operacional: **2 habilitações por área de gestão**
   - Ex.: 1 *Dono do Processo* + 1 *Usuário Adicional*  
   **ou**
   - 1 *Chave* por área + 1 *Líder* para todas as áreas do contrato
6. Aba **Áreas de Gestão**: registrar a área de gestão por usuário:
   - **Tipo de Habilitação**:
     - *Análise de aprendizagem* (usuários do projeto)
     - *Quiz* (cliente de base que já tem conhecimento)
     - *Unidade* (para *Dono do Processo*)
   - **Sequência de Habilitações** (quando for Líder)
7. Aguardar validação da Universidade; depois disso, usuários recebem (via B.I.) link/instruções para criar ID e acessar.

### Atenções (evitam retrabalho)
- A tela é de **inclusão**: **não dá para editar** após salvar. Validar tudo antes.
- Não é possível registrar o **mesmo contato 2 vezes**; se a mesma pessoa precisar “papéis” diferentes, abrir **duas solicitações** independentes.
- Sempre conferir contrato para **não incluir gestões** que o cliente não possui.

---

## 4) Agendamento e execução (Universidade)

### Checklist para agendar
1. Confirmar **base de testes replicada do Produção**.
2. Enviar para Universidade: **cliente + tipo (chave/gerencial/técnico) + link e credenciais da base + contato do líder do projeto**.
3. Universidade valida e agenda com o cliente (data/horário).
4. Se não houver retorno do cliente, Universidade volta para a unidade pedindo **ponte**.

---

## Templates (copiar e colar)

### Para o cliente (base de testes)
Olá! Para iniciarmos a certificação, precisamos de uma **base de testes replicada do seu ambiente de produção**.  
Quando estiver pronta, me envie **link de acesso e senha (ou usuário/senha)** e o **telefone/e-mail do líder do projeto** para agendamento.

### Para a Universidade (agendamento)
Olá, time Universidade. Solicito agendamento de certificação para o cliente **[NOME]**.  
Solicitação já tratada/aprovada. Seguem acesso da base de testes replicada: **[LINK] | [USUÁRIO] | [SENHA]**.  
Contato do líder do projeto: **[NOME/TELEFONE]**. Tipo: **[Chave/Gerencial/Técnico]**. Obrigado.

---

## Fluxo em diagrama (Mermaid)

```mermaid
flowchart TD
A[Início] --> B[Pré-check: contrato + tipo + contatos]
B --> C{Cenário?}
C -->|Novo projeto| D[Solicitar via Experience]
C -->|Base / Troca / Técnico| E[Solicitar via Sanqueon: Solicitação de Matrículas]
D --> F[Universidade trata/vincula]
E --> F[Universidade trata (até 5 dias úteis)]
F --> G{Base teste replicada do Produção?}
G -->|Não| H[Orientar cliente a preparar base]
H --> G
G -->|Sim| I[Enviar link + credenciais à Universidade]
I --> J[Universidade valida e agenda com cliente]
J --> K{Cliente responde?}
K -->|Sim| L[Agenda confirmada]
K -->|Não| M[Universidade pede ponte à unidade]
M --> L
L --> N[Fim]
