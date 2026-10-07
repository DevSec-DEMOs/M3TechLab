---
marp: true
theme: default
paginate: true
size: 16:9
title: "Workshop DevOps + Security"
description: "M3TechLab - Da entrega de software à experimentação de segurança"
---
# DevOps + Security

### Da entrega de software à experimentação de segurança

**M3TechLab**

---

# O que vamos entender?

**DevOps** → fluxo, feedback, aprendizado

**Security** → onde entra no fluxo

**Controles** → SAST, SCA, Secrets, Threat Modeling

**Experimentação** → Security Chaos Engineering

**Prática** → Devici + Aikido

---

# Como software chega ao usuário?

```text
Ideia → Código → Build → Teste → Deploy → Produção
                                      ↑
                                   Feedback
```

**Objetivo:** transformar mudanças em valor.

---

# Quando o sistema cresce

```text
Código + Dependências + Infraestrutura + Pessoas + Integrações
                           ↓
                       Complexidade
```

A pergunta muda para:

> Como continuar entregando rápido sem perder controle?

---

# O que é DevOps?

DevOps não é uma ferramenta ou produto.

É uma forma de **organizar o trabalho** para melhorar a entrega de software.

**Foco:** fluxo entre desenvolvimento, operações e demais áreas.

---

# O problema: silos

```text
Desenvolvimento
      ↓
   "Joga"
      ↓
   Operações
      ↓
  "Devolve"
      ↓
Desenvolvimento
```

Isso gera **fila, espera, retrabalho e feedback tardio**.

---

# As Três Maneiras

### 1. Fluxo

Fazer o trabalho fluir.

### 2. Feedback

Descobrir problemas rapidamente.

### 3. Aprendizado

Transformar experiência em melhoria.

---

# 1ª Maneira — Fluxo

```text
Código → Build → Teste → Deploy → Produção
```

Pergunte:

- Onde está o gargalo?
- Onde existe trabalho manual?
- Onde há filas?
- Onde há lotes grandes?

**Pare de começar. Comece a terminar.**

---

# 2ª Maneira — Feedback

Quanto mais tarde descobrimos um problema, maior tende a ser o custo.

```text
Código → Teste → Deploy → Produção
   ↑                         │
   └──────── Feedback ───────┘
```

**Security também precisa gerar feedback.**

---

# 3ª Maneira — Aprendizado

```text
Executar → Observar → Aprender → Melhorar
                         ↑          │
                         └──────────┘
```

Não basta detectar.

**Precisamos aprender com o resultado.**

---

# Security não começa no Deploy

```text
Requisitos → Arquitetura → Código → Build
                                      ↓
Tests → Deploy → Produção → Monitoramento
```

Security pode acompanhar todo o fluxo.

---

# Onde Security entra?

| Etapa          | Exemplos                       |
| -------------- | ------------------------------ |
| Arquitetura    | Threat Modeling                |
| Código        | SAST, Secrets                  |
| Dependências  | SCA                            |
| Infraestrutura | IaC, Container                 |
| Produção     | DAST, API Security, Monitoring |
| Operação     | Detection, Response, Testing   |

**Segurança vira feedback do fluxo.**

---

# Que problemas podemos encontrar?

| Problema                 | Exemplo             |
| ------------------------ | ------------------- |
| Código vulnerável      | SQL Injection       |
| Dependência vulnerável | CVE                 |
| Segredo exposto          | API Key no Git      |
| Configuração insegura  | Recurso público    |
| Arquitetura vulnerável  | Trust boundary      |
| Controle ineficaz        | Alerta não dispara |

Cada problema pede um controle diferente.

---

# SAST

**Static Application Security Testing**

Analisa o código sem executar a aplicação.

```text
Código → SAST → Possível vulnerabilidade
```

**Pergunta:** há padrões vulneráveis no código?

---

# SCA

**Software Composition Analysis**

Analisa bibliotecas e dependências.

```text
Aplicação → Dependências → SCA → Riscos conhecidos
```

Pode revelar **vulnerabilidades, versões e licenças**.

---

# SAST ≠ SCA

|          | SAST             | SCA                 |
| -------- | ---------------- | ------------------- |
| Analisa  | Código          | Dependências       |
| Exemplo  | SQL Injection    | CVE                 |
| Pergunta | Como escrevemos? | O que incorporamos? |

Uma aplicação pode ter código próprio seguro e ainda usar uma dependência vulnerável.

---

# Secrets Detection

E se uma credencial estiver no código?

```text
Git → Secrets Detection
       ↓
API Key / Token / Credential
```

**Objetivo:** detectar segredos expostos antes que virem incidente.

---

# Threat Modeling

Antes de procurar vulnerabilidades, pergunte:

> **Como este sistema pode ser atacado?**

```text
Usuário → Aplicação → API → Banco
```

Procure **ameaças, trust boundaries e caminhos de ataque**.

---

# STRIDE

Uma forma de organizar ameaças:

- **S — Spoofing** — Falsificação de identidade
- **T — Tampering** — Adulteração
- **R — Repudiation** — Repúdio
- **I — Information Disclosure** — Divulgação de informações
- **D — Denial of Service** — Negação de serviço
- **E — Elevation of Privilege** — Elevação de privilégio

Threat Modeling acontece antes de depender apenas de scanners.

---

# Encontrar não é suficiente

```text
Threat Modeling
      ↓
SAST / SCA / Secrets
      ↓
    Corrigir
```

Nova pergunta:

> **Como sabemos que nossos controles funcionam?**

---

# Security Chaos Engineering

**Não assumir. Experimentar.**

Criamos uma hipótese, provocamos uma condição controlada e observamos o resultado.

**Objetivo:** descobrir falhas nos controles e aumentar a confiança na segurança do sistema.

---

# Teste × Experimento

### Teste

Valida um resultado conhecido.

### Experimento

Busca descobrir algo sobre o comportamento do sistema.

```text
Hipótese → Condição controlada → Observação → Aprendizado
```

---

# Exemplo de Security Chaos

**Hipótese:**

> Se ocorrer um evento suspeito, conseguiremos detectá-lo.

Verificamos:

**Log → Alerta → Detecção → Resposta**

Se algo falhar, temos um aprendizado concreto.

---

# Game Day

Uma forma controlada de experimentar.

**Antes:** hipótese, cenário e limites

**Durante:** executar, observar e registrar

**Depois:** comparar, corrigir e repetir

---

# Segurança também é um sistema

```text
Código → CI/CD → Artefato → Infra → Aplicação
                                      ↓
Monitoramento ← Detecção ← Resposta
```

A falha pode estar no **código, processo, configuração, integração ou detecção**.

---

# O pipeline também é superfície de ataque

```text
Developer → Git → CI → Artifact → Deploy → Production
```

O pipeline pode acessar:

**código · credenciais · artefatos · ambientes · infraestrutura**

Por isso, o próprio pipeline precisa de segurança.

---

# Nosso laboratório

```text
GitHub
  ↓
  CI
  ├── SAST
  ├── SCA
  └── Secrets
  ↓
Build → Deploy → Application
```

Agora conectamos **conceito → ferramenta → prática**.

---

# Demo 1 — Threat Modeling

**Problema:** como identificar ameaças antes de depender de scanners?

**Conceito:** Threat Modeling

**Ferramenta:** Devici

Vamos observar:

**arquitetura · trust boundaries · ameaças · mitigations**

---

# Demo 2 — Application Security

**Problema:** como encontrar problemas no software antes da produção?

**Conceitos:** SAST · SCA · Secrets

**Ferramenta:** Aikido

---

# Depois do scanner...

```text
Encontrar → Priorizar → Corrigir → Validar → Monitorar
```

E depois?

**Experimentar.**

Segurança não termina quando o scanner gera um resultado.

---

# A ideia central

```text
Conceito
   ↓
Ferramenta
   ↓
Experimento
   ↓
Aprendizado
   ↺
```

**DevOps melhora o fluxo.**

**Security adiciona feedback.**

**Experimentação testa nossas premissas.**

---

# Agora vamos para as demos

## DevOps + Security

**M3TechLa**

---
marp: true
theme: default
paginate: true
size: 16:9
title: "Workshop DevOps + Security"
description: "M3TechLab - Da entrega de software à experimentação de segurança"
---
# DevOps + Security

## Da entrega de software à experimentação de segurança

**M3TechLab**

---

# O que vamos fazer?

Entender como software é entregue

↓

Entender como DevOps melhora esse fluxo

↓

Entender onde Security entra

↓

Conhecer os principais controles

↓

Ver como podemos validar se eles funcionam

↓

**Partir para as demos**

---

# Como software chega ao usuário?

```text
Ideia
  ↓
Código
  ↓
Build
  ↓
Testes
  ↓
Deploy
  ↓
Produção
  ↓
Feedback
  ↺
```

O objetivo é transformar uma mudança em valor para o usuário.

---

# Quando o sistema cresce...

```text
Mais código
Mais dependências
Mais infraestrutura
Mais pessoas
Mais automação
Mais integrações
        ↓
     Mais complexidade
```

A pergunta passa a ser:

> Como continuar entregando rápido sem perder controle?

---

# O que é DevOps?

DevOps não é:

- uma ferramenta
- um produto
- uma equipe
- simplesmente CI/CD

DevOps é uma forma de organizar o trabalho para melhorar o fluxo entre desenvolvimento, operações e as demais áreas envolvidas na entrega de software.

---

# O problema que DevOps tenta resolver

Um fluxo baseado em silos pode se parecer com:

```text
Desenvolvimento
      ↓
    "Joga"
      ↓
Operações
      ↓
   "Devolve"
      ↓
Desenvolvimento
```

Cada transferência pode criar:

- filas
- espera
- retrabalho
- perda de contexto
- feedback tardio

---

# As Três Maneiras

## 1. Fluxo

Fazer o trabalho fluir pelo sistema.

## 2. Feedback

Obter informações rapidamente sobre o que está acontecendo.

## 3. Aprendizado contínuo

Transformar experiência e experimentação em melhoria.

---

# 1ª Maneira: Fluxo

```text
Código
  ↓
Build
  ↓
Teste
  ↓
Deploy
  ↓
Produção
```

Perguntas importantes:

- Onde o trabalho está parado?
- Onde existem gargalos?
- Quanto trabalho está em andamento?
- Onde existe trabalho manual?
- Onde existem lotes grandes?

**Pare de começar e comece a terminar.**

---

# 2ª Maneira: Feedback

Quanto mais tarde descobrimos um problema:

- mais contexto pode ser perdido
- mais mudanças podem depender dele
- mais caro pode ser corrigi-lo

```text
Código → Teste → Deploy → Produção
   ↑                         │
   └──────── Feedback ───────┘
```

E se o feedback de segurança também fizer parte desse fluxo?

---

# 3ª Maneira: Aprendizado contínuo

Não basta detectar problemas.

```text
Executar
   ↓
Observar
   ↓
Aprender
   ↓
Melhorar
   ↓
Experimentar novamente
```

O sistema melhora quando o conhecimento volta para o próprio fluxo de trabalho.

---

# Segurança não começa depois do Deploy

```text
Requisitos
    ↓
Arquitetura
    ↓
Código
    ↓
Build
    ↓
Testes
    ↓
Deploy
    ↓
Produção
```

Segurança pode acompanhar todo esse fluxo.

---

# Onde Security entra?

```text
Threat Modeling
      ↓
SAST / SCA / Secrets
      ↓
Container / IaC
      ↓
DAST / API Security
      ↓
Monitoring / Detection
      ↓
Security Testing
```

A ideia não é criar uma etapa isolada de segurança.

É criar **feedback de segurança dentro do fluxo de engenharia**.

---

# Que tipos de problemas podemos encontrar?

| Problema                 | Exemplo                   |
| ------------------------ | ------------------------- |
| Código vulnerável      | SQL Injection             |
| Dependência vulnerável | Biblioteca com CVE        |
| Segredo exposto          | API Key no Git            |
| Configuração insegura  | Recurso público          |
| Arquitetura vulnerável  | Trust boundary inadequada |
| Controle que falha       | Alerta que não dispara   |

Cada problema pode exigir um tipo diferente de controle.

---

# SAST

## Static Application Security Testing

Analisa o código sem precisar executar a aplicação.

```text
Código
  ↓
 SAST
  ↓
Possível vulnerabilidade
```

### Pergunta que SAST ajuda a responder

> Existe um padrão vulnerável no código que podemos identificar antes da execução?

---

# SCA

## Software Composition Analysis

Analisa os componentes e dependências utilizados pela aplicação.

```text
Minha aplicação

├── Framework
├── Biblioteca A
├── Biblioteca B
├── Biblioteca C
└── outras dependências
          ↓
         SCA
          ↓
Vulnerabilidades
Versões
Licenças
Dependências
```

### Pergunta

> O software que estamos incorporando possui riscos conhecidos?

---

# SAST ≠ SCA

|                        | SAST             | SCA                |
| ---------------------- | ---------------- | ------------------ |
| Analisa                | Código próprio | Dependências      |
| Execução necessária | Não             | Não               |
| Exemplo                | SQL Injection    | CVE em biblioteca  |
| Foco                   | Como escrevemos  | O que incorporamos |

Uma aplicação pode ter código próprio seguro e ainda depender de componentes vulneráveis.

---

# Secrets Detection

E se o problema estiver em uma credencial dentro do código?

```text
Git Repository
      ↓
API_KEY = "..."
AWS_SECRET = "..."
TOKEN = "..."
      ↓
Secrets Detection
```

O objetivo é encontrar credenciais ou outros segredos expostos antes que eles se tornem um incidente.

---

# Threat Modeling

Antes de procurar vulnerabilidades no código, podemos perguntar:

> Como esse sistema pode ser atacado?

```text
Usuário
   ↓
Web Application
   ↓
API
   ↓
Database
```

Perguntas:

- Quem pode acessar?
- O que pode ser alterado?
- Que dados podem vazar?
- Onde estão as fronteiras de confiança?
- Quais são os caminhos de ataque?

---

# STRIDE

Uma forma conhecida de organizar ameaças:

- **S**poofing — falsificação de identidade
- **T**ampering — adulteração
- **R**epudiation — repúdio
- **I**nformation Disclosure — exposição de informação
- **D**enial of Service — negação de serviço
- **E**levation of Privilege — elevação de privilégio

Threat Modeling ajuda a pensar sobre segurança antes de depender exclusivamente de scanners.

---

# Encontrar problemas não é suficiente

Até agora:

```text
Threat Modeling
      ↓
SAST
      ↓
SCA
      ↓
Secrets
      ↓
Corrigir
```

Mas surge outra pergunta:

> **Como sabemos que nossos controles realmente funcionam?**

---

# Security Chaos Engineering

Uma ideia central:

> Identificar falhas em controles de segurança por meio de experimentação proativa, aumentando a confiança de que o sistema consegue se defender sob condições adversas.

Em vez de assumir que um controle funciona:

**criamos uma hipótese e experimentamos.**

---

# "Assumimos que funciona"

```text
"Temos um firewall."
        ↓
"Temos logs."
        ↓
"Temos alertas."
        ↓
"Temos MFA."
        ↓
"Temos um scanner."
```

Mas:

# Como você sabe?

---

# Teste vs. Experimento

## Teste

> Eu sei o que estou procurando.

Validamos um resultado esperado.

## Experimento

> Quero descobrir algo sobre o comportamento do sistema.

Criamos uma hipótese, provocamos uma condição e observamos o resultado.

---

# Security Chaos na prática

### Hipótese

> Se um evento suspeito acontecer, nosso sistema irá detectá-lo.

```text
Hipótese
   ↓
Experimento controlado
   ↓
Evento simulado
   ↓
Log?
Alerta?
Detecção?
Resposta?
   ↓
Aprendizado
```

O objetivo não é causar dano.

O objetivo é descobrir se nossa expectativa corresponde à realidade.

---

# Game Day

Uma forma de começar com experimentação controlada.

### Antes

- definir o sistema
- definir a hipótese
- definir o cenário
- definir impacto esperado

### Durante

- executar o experimento
- observar
- registrar resultados

### Depois

- comparar expectativa e realidade
- identificar falhas
- corrigir
- repetir o experimento

---

# Segurança também é um sistema

Não devemos olhar apenas para uma ferramenta.

```text
Código
  ↓
CI/CD
  ↓
Artefatos
  ↓
Infraestrutura
  ↓
Aplicação
  ↓
Monitoramento
  ↓
Resposta
```

Uma falha pode estar na tecnologia, configuração, processo, integração ou na própria capacidade de detectar o problema.

---

# O pipeline também é uma superfície de ataque

```text
Developer
    ↓
Repository
    ↓
CI Server
    ↓
Build
    ↓
Artifact Registry
    ↓
Deploy
    ↓
Production
```

O pipeline pode ter acesso a:

- código
- credenciais
- artefatos
- ambientes
- infraestrutura
- serviços externos

Por isso, **o pipeline também precisa de segurança**.

---

# Nosso laboratório

```text
                    GitHub
                       │
                       ▼
                  ┌─────────┐
                  │  Code   │
                  └────┬────┘
                       │
                  ┌────▼────┐
                  │   CI    │
                  └────┬────┘
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
        SAST          SCA        Secrets
          │            │            │
          └────────────┼────────────┘
                       ▼
                     Build
                       │
                       ▼
                    Deploy
                       │
                       ▼
                  Application
```

Agora podemos conectar os conceitos às ferramentas.

---

# Conceito → Ferramenta → Demo

```text
Threat Modeling
       ↓
     Devici
       ↓
   Arquitetura
```

```text
Código / Dependências / Secrets
       ↓
     Aikido
       ↓
SAST / SCA / Secrets / outros controles
```

A ferramenta é o meio.

O conceito e o problema vêm primeiro.

---

# Demo 1 — Threat Modeling

## Problema

> Como podemos identificar ameaças antes de depender apenas de testes e scanners?

## Conceito

**Threat Modeling**

## Ferramenta

**Devici**

## Vamos observar

- arquitetura
- componentes
- trust boundaries
- ameaças
- mitigations

---

# Demo 2 — Application Security

## Problema

> Como encontramos problemas no software antes de chegar à produção?

## Conceitos

- SAST
- SCA
- Secrets
- outros controles de Application Security

## Ferramenta

**Aikido**

---

# Depois do scanner...

Encontramos uma vulnerabilidade.

E agora?

```text
Encontrar
   ↓
Priorizar
   ↓
Corrigir
   ↓
Validar
   ↓
Monitorar
   ↓
Experimentar
```

Segurança não termina quando o scanner gera um resultado.

---

# Segurança como feedback

```text
              ┌─────────────────────┐
              │   Threat Modeling   │
              └──────────┬──────────┘
                         ↓
Código → SAST/SCA → CI/CD → Deploy
  ↑                         ↓
  │                     Produção
  │                         ↓
  └────── Feedback ← Monitoring
                         ↓
                Security Experiments
                         ↓
                      Aprender
```

---

# O que levar daqui?

### 1.

**DevOps é sobre fluxo, feedback e aprendizado.**

### 2.

**Security precisa fazer parte desse fluxo.**

### 3.

**Ferramentas encontram problemas, mas não garantem segurança.**

### 4.

**Precisamos experimentar para descobrir se nossas premissas são verdadeiras.**

---

# Conceito

↓

# Ferramenta

↓

# Experimento

↓

# Aprendizado

---

# Agora vamos para as demos

## DevOps + Security

**M3TechLab**
