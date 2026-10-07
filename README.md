# M3TechLab

**Projetos, ferramentas e recursos de aprendizado em tecnologia para estudantes e entusiastas.**

O **M3TechLab** é um espaço de aprendizado prático em tecnologia, criado para aproximar **conceitos, ferramentas e experimentação**.

A proposta é reunir materiais que permitam aprender não apenas **como utilizar uma tecnologia**, mas também:

- qual problema ela resolve;
- por que esse problema existe;
- quais conceitos estão por trás dela;
- como utilizá-la na prática;
- como experimentar com segurança;
- onde continuar estudando.

---

## O que você encontrará aqui

O M3TechLab reúne diferentes tipos de materiais relacionados a tecnologia.

### Projetos

Projetos práticos para experimentar conceitos de desenvolvimento, infraestrutura, cloud, DevOps e segurança.

### Ferramentas

Guias de ferramentas que podem ser utilizadas por estudantes, desenvolvedores e entusiastas.

Sempre que possível, são priorizadas ferramentas que ofereçam:

- Free Tier;
- Community Edition;
- Open Source;
- acesso acadêmico;
- laboratórios gratuitos;
- recursos suficientes para aprendizado individual.

### Livros e referências

Guias de estudo baseados em livros importantes de tecnologia e engenharia.

A intenção não é simplesmente listar livros, mas conectar:

```text
Livro
  ↓
Conceito
  ↓
Ferramenta
  ↓
Laboratório
  ↓
Experimentação
```

### Laboratórios

Exercícios e ambientes para transformar conceitos em experiência prática.

### Recursos

Artigos, documentação, vídeos, cursos e outras referências úteis para aprofundamento.

---

# Para quem é

O M3TechLab foi pensado principalmente para:

- estudantes universitários;
- pessoas começando na área de tecnologia;
- desenvolvedores;
- profissionais de infraestrutura;
- pessoas interessadas em cibersegurança;
- profissionais iniciando em DevOps e DevSecOps;
- entusiastas que querem aprender construindo.

Não é necessário ter experiência prévia em cibersegurança para começar.

Os materiais procuram explicar os conceitos antes de assumir conhecimento sobre ferramentas ou terminologia específica.

---

# Como aprender no M3TechLab

A proposta é evitar o modelo:

```text
Ferramenta
    ↓
Clique aqui
    ↓
Configure isso
    ↓
Fim
```

Em vez disso:

```text
Problema
   ↓
Conceito
   ↓
Tecnologia
   ↓
Ferramenta
   ↓
Laboratório
   ↓
Experimento
   ↓
Aprendizado
```

Por exemplo:

```text
Problema:
Como entregar software com mais velocidade e segurança?

        ↓

Conceito:
DevOps e DevSecOps

        ↓

Tecnologia:
CI/CD

        ↓

Ferramenta:
GitHub Actions

        ↓

Segurança:
SAST, SCA, Secrets

        ↓

Ferramenta:
Aikido

        ↓

Experimentação:
Security Chaos Engineering
```

O objetivo é compreender o **sistema como um todo**, e não apenas decorar comandos ou interfaces.

---

# Conceitos antes das ferramentas

Uma ferramenta muda.

Um conceito tende a permanecer.

Por isso, o M3TechLab procura apresentar primeiro os fundamentos e depois mostrar como diferentes ferramentas implementam esses fundamentos.

Por exemplo:

```text
Application Security
       ↓
SAST
       ↓
Ferramentas de SAST
```

ou:

```text
Threat Modeling
       ↓
STRIDE / LINDDUN / Attack Paths
       ↓
Ferramentas de Threat Modeling
```

ou:

```text
DevOps
       ↓
CI/CD
       ↓
GitHub Actions / GitLab CI / Azure DevOps
```

Dessa forma, o conhecimento não fica preso a um único fabricante ou produto.

---

# Tecnologia e segurança

Cibersegurança não deve ser tratada como uma camada isolada colocada sobre sistemas prontos.

Ela faz parte do processo de engenharia.

Uma visão simplificada:

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
    ↓
Monitoramento
    ↓
Feedback
    ↓
Nova mudança
```

A segurança participa desse fluxo.

Por isso, o M3TechLab aborda temas como:

- Application Security;
- DevSecOps;
- Identity;
- Cloud Security;
- Network Security;
- Threat Modeling;
- CI/CD Security;
- Supply Chain Security;
- Security Monitoring;
- Incident Response;
- AI Security.

---

# Livros → ferramentas → prática

Uma das características do M3TechLab é conectar materiais teóricos com experimentação.

Um exemplo:

```text
O Projeto Fênix
        ↓
DevOps
        ↓
Manual de DevOps
        ↓
CI/CD
        ↓
GitHub Actions
        ↓
DevSecOps
        ↓
Aikido
        ↓
Security Chaos Engineering
```

Outro:

```text
Threat Modeling
        ↓
Devici
        ↓
Attack Paths
        ↓
Hipóteses de segurança
        ↓
Experimentos
```

Essa relação permite que o estudante veja como uma ideia apresentada em um livro aparece em uma arquitetura, em uma ferramenta e finalmente em um laboratório.

---

# Aprender fazendo

O M3TechLab prioriza experimentação.

Sempre que possível, um conceito deve poder ser transformado em uma atividade prática.

Por exemplo:

**Conceito**

> Um pipeline pode representar uma superfície de ataque.

**Pergunta**

> O que aconteceria se alguém obtivesse acesso ao pipeline?

**Laboratório**

Construir um pipeline simples.

**Experimento**

Analisar:

- permissões;
- secrets;
- tokens;
- artefatos;
- scripts;
- integrações;
- logs.

**Aprendizado**

Entender por que CI/CD também precisa ser protegido.

Esse ciclo é mais importante do que simplesmente conhecer o nome de uma ferramenta.

---

# Segurança de forma responsável

Os laboratórios do M3TechLab devem ser realizados em ambientes controlados e autorizados.

Nunca utilize técnicas ou ferramentas apresentadas aqui contra sistemas de terceiros sem autorização.

Para experimentação:

- utilize ambientes próprios;
- prefira ambientes isolados;
- utilize dados fictícios quando possível;
- evite credenciais reais;
- tenha mecanismos de rollback;
- entenda o impacto antes de executar um teste;
- não execute experimentos destrutivos em produção.

O objetivo é **aprender engenharia e segurança**, não causar impacto em sistemas reais.

---

# Princípios do M3TechLab

## 1. Fundamentos antes de ferramentas

Entender o problema é mais importante do que decorar uma ferramenta.

## 2. Teoria e prática devem estar conectadas

Um conceito deve, sempre que possível, poder ser observado em um projeto ou laboratório.

## 3. Ferramentas são meios

O objetivo não é aprender o maior número possível de produtos.

O objetivo é aprender conceitos que possam ser aplicados utilizando diferentes tecnologias.

## 4. Experimentação

Aprender fazendo, medindo e observando.

## 5. Conhecimento acessível

Priorizar materiais e ferramentas que possam ser utilizados por estudantes e pessoas com recursos limitados.

## 6. Pensamento sistêmico

Tecnologia não é uma coleção de componentes independentes.

Código, infraestrutura, pessoas, processos, segurança e operação fazem parte do mesmo sistema.

## 7. Aprendizado contínuo

Tecnologia muda rapidamente. O objetivo é desenvolver a capacidade de aprender novas tecnologias, e não apenas conhecer as atuais.

---

# Um possível caminho

Não existe uma única sequência obrigatória, mas uma progressão natural pode ser:

```text
Fundamentos
    ↓
Desenvolvimento
    ↓
Git e GitHub
    ↓
Cloud e infraestrutura
    ↓
DevOps
    ↓
CI/CD
    ↓
DevSecOps
    ↓
Cibersegurança
    ↓
Arquitetura
    ↓
Observabilidade e confiabilidade
    ↓
Experimentação
```

A partir daí, o estudante pode aprofundar-se em áreas específicas.

---

# Explore por área

O M3TechLab pode ser explorado a partir de diferentes interesses:

### Desenvolvimento

Código, engenharia de software, Git, testes e arquitetura.

### DevOps

CI/CD, automação, infraestrutura, containers e cloud.

### DevSecOps

Integração de segurança ao ciclo de desenvolvimento.

### Cibersegurança

Application Security, Identity, Network Security, Cloud Security e outras áreas.

### Arquitetura

Arquitetura de software, sistemas distribuídos, escalabilidade e decisões arquiteturais.

### Confiabilidade

Observabilidade, resiliência, incident response e engenharia de confiabilidade.

### Inteligência Artificial

Fundamentos e aplicações de IA, além dos desafios relacionados à segurança de sistemas de IA.

---

# Como os conteúdos se relacionam

O objetivo é construir uma rede de conhecimento, e não uma coleção de páginas independentes.

```text
                    FUNDAMENTOS
                         │
          ┌──────────────┼──────────────┐
          ↓              ↓              ↓
   Desenvolvimento     Cloud          Redes
          │              │              │
          └──────────────┼──────────────┘
                         ↓
                       DevOps
                         ↓
                       CI/CD
                         ↓
                     DevSecOps
                         ↓
                  Cibersegurança
                         ↓
             Observabilidade / SRE
                         ↓
                 Experimentação
```

Cada área pode levar a outras.

O estudante não precisa conhecer tudo antes de começar.

---

# Documentação e fontes

Sempre que possível, os materiais devem apontar para:

- documentação oficial;
- projetos Open Source;
- artigos técnicos;
- papers;
- livros;
- cursos;
- laboratórios;
- referências acadêmicas.

Quando uma ferramenta comercial for apresentada, o foco é educacional: entender o conceito, experimentar a tecnologia disponível e conhecer suas aplicações.

O M3TechLab não pretende substituir a documentação oficial dos projetos.

---

# Contribuições

Contribuições são bem-vindas quando ajudam a melhorar o material educacional.

Podem incluir:

- correções;
- novos exemplos;
- novos laboratórios;
- melhorias na documentação;
- referências relevantes;
- projetos educacionais;
- sugestões de ferramentas;
- melhorias nos exercícios.

Ao adicionar um novo conteúdo, procure responder:

1. Qual problema ele resolve?
2. Qual conceito ele ensina?
3. Para quem é útil?
4. Existe uma forma prática de experimentar?
5. Quais são as referências para aprofundamento?

---

# Objetivo

O objetivo do M3TechLab não é formar especialistas em uma ferramenta específica.

É ajudar estudantes e profissionais iniciantes a desenvolver uma base que permita:

```text
Entender
   ↓
Experimentar
   ↓
Construir
   ↓
Medir
   ↓
Aprender
   ↓
Evoluir
```

Tecnologia muda.

Ferramentas mudam.

Produtos desaparecem.

Os fundamentos, a capacidade de raciocinar sobre sistemas e a capacidade de aprender continuamente permanecem.

---

## M3TechLab

**Projetos, ferramentas e recursos de aprendizado em tecnologia para estudantes e entusiastas.**
