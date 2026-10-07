# Livros

Esta pasta reúne livros e guias de estudo selecionados pelo **M3TechLab** para apoiar a formação em tecnologia, engenharia de software, DevOps e cibersegurança.

A proposta não é criar uma biblioteca de arquivos, mas um conjunto de **referências para estudo** que ajudem a entender os conceitos por trás das ferramentas e práticas apresentadas no projeto.

Cada livro possui um material complementar em Markdown com:

- principais conceitos;
- explicação dos termos relevantes;
- relação com tecnologia e segurança;
- exemplos práticos;
- exercícios;
- relação com outros conteúdos do M3TechLab;
- referências para aprofundamento.

> Os livros originais não são redistribuídos pelo projeto quando sujeitos a direitos autorais. Os materiais deste diretório são guias educacionais e referências para estudo.

---

## Livros disponíveis

### 1. O Projeto Fênix

**Autores:** Gene Kim, Kevin Behr e George Spafford

**Tema principal:** DevOps, fluxo de trabalho e melhoria organizacional.

**Nível:** Iniciante

**Por que estudar:**

*O Projeto Fênix* apresenta, por meio de uma história fictícia, problemas comuns em organizações de tecnologia: gargalos, excesso de trabalho, filas, trabalho não planejado, falta de feedback e dificuldade de coordenação entre equipes.

O livro é utilizado como uma introdução aos problemas que deram origem a muitas das práticas associadas ao DevOps.

**Principais conceitos:**

- Fluxo de trabalho
- Work in Progress
- Gargalos
- Theory of Constraints
- Feedback
- Trabalho não planejado
- As Três Maneiras
- Melhoria contínua
- Automação
- Projeto Unicórnio
- Débito técnico

**Relação com o M3TechLab:**

É o ponto de partida conceitual para entender **por que** organizações de tecnologia precisam melhorar seus processos e sistemas de trabalho.

[Guia de estudo](./O_Projeto_Fenix.md)

---

### 2. Manual de DevOps

**Autores:** Gene Kim, Jez Humble, Patrick Debois e John Willis

**Tema principal:** DevOps, automação, fluxo, feedback e aprendizado contínuo.

**Nível:** Iniciante

**Por que estudar:**

O *Manual de DevOps* transforma muitos dos problemas apresentados em *O Projeto Fênix* em princípios e práticas para melhorar o sistema de trabalho de tecnologia.

O livro ajuda a compreender que DevOps não é uma ferramenta específica, mas uma abordagem para melhorar o fluxo entre desenvolvimento, operações, segurança, qualidade e negócio.

**Principais conceitos:**

- DevOps
- As Três Maneiras
- Fluxo
- Feedback
- Aprendizado contínuo
- Automação
- Continuous Integration
- Continuous Delivery
- CI/CD
- Segurança integrada ao fluxo
- DevSecOps
- Trabalho em pequenos lotes

**Relação com o M3TechLab:**

É a ponte entre os conceitos apresentados em *O Projeto Fênix* e a aplicação prática desses conceitos utilizando ferramentas como GitHub, CI/CD e ferramentas de segurança.

[Guia de estudo](./Manual_de_DevOps.md)

---

### 3. Security Chaos Engineering

**Autores:** Aaron Rinehart e Kelly Shortridge

**Tema principal:** Segurança, resiliência e experimentação.

**Nível:** Intermediário

**Por que estudar:**

*Security Chaos Engineering* aplica os princípios de Chaos Engineering à segurança da informação.

A ideia central é testar deliberadamente hipóteses sobre a segurança de um sistema para descobrir se os controles realmente funcionam como esperado.

Em vez de simplesmente perguntar:

> "Temos este controle?"

A abordagem pergunta:

> "O que acontece quando este controle falha?"

**Principais conceitos:**

- Security Chaos Engineering
- Resiliência
- Experimentação
- Failure Injection
- Decision Trees
- Attacker Math
- Attack Paths
- Threat Modeling
- Security Theater
- Security Champions
- Game Days
- Security Monitoring
- Incident Response
- Build Security
- CI/CD Security
- Feedback Loops

**Relação com o M3TechLab:**

É a conexão entre **DevOps, DevSecOps e engenharia de segurança**, mostrando como transformar hipóteses de segurança em experimentos e aprendizado.

Também possui uma relação direta com ferramentas estudadas no projeto, como Threat Modeling e ferramentas de Application Security.

[Guia de estudo](./Security_Chaos_Engineering.md)

---

# Como os livros se conectam

Os três livros foram escolhidos para formar uma sequência conceitual:

```text
O Projeto Fênix
       │
       │ Entender o problema
       ▼
Manual de DevOps
       │
       │ Melhorar fluxo, feedback e aprendizado
       ▼
Security Chaos Engineering
       │
       │ Aplicar experimentação à segurança
       ▼
DevSecOps
```

Ou, de forma ainda mais simples:

```text
Por que precisamos mudar?
        ↓
Como podemos trabalhar melhor?
        ↓
Como sabemos que nossa segurança funciona?
```

### O Projeto Fênix

Explica os **problemas do sistema de trabalho**.

### Manual de DevOps

Apresenta princípios para **melhorar o sistema de trabalho**.

### Security Chaos Engineering

Apresenta uma abordagem para **testar e aprender sobre a segurança do sistema**.

---

# Livros e ferramentas

Os livros não devem ser estudados isoladamente.

Uma das propostas do M3TechLab é conectar:

```text
Livro
  ↓
Conceito
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
      ↓
Experimentos de segurança
```

Da mesma forma:

```text
Threat Modeling
      ↓
Devici
      ↓
Attack Paths
      ↓
Hipóteses de segurança
      ↓
Security Chaos Engineering
```

O objetivo é evitar que o estudante aprenda apenas **como utilizar uma ferramenta**, sem entender **qual problema ela resolve e por que ela existe**.

---

# Como utilizar esta pasta

A recomendação é:

1. Escolha um dos livros.
2. Leia o guia correspondente em Markdown.
3. Identifique os conceitos apresentados.
4. Consulte as ferramentas relacionadas no M3TechLab.
5. Execute os laboratórios disponíveis.
6. Tente relacionar o resultado do laboratório com os conceitos do livro.
7. Continue para o próximo material.

Os guias não têm como objetivo substituir os livros originais.

Eles funcionam como **material de orientação e conexão entre teoria e prática**.

---

# Critério de seleção

Os livros desta pasta são selecionados principalmente pela capacidade de contribuir para uma formação prática em tecnologia.

São priorizadas obras que:

- apresentam conceitos fundamentais;
- continuam relevantes independentemente de uma ferramenta específica;
- ajudam a compreender como sistemas de tecnologia funcionam;
- conectam teoria e prática;
- podem ser aplicadas em projetos reais;
- ajudam a desenvolver raciocínio de engenharia;
- possuem relação com os laboratórios e ferramentas do M3TechLab.

O objetivo não é montar uma lista dos "melhores livros de tecnologia", mas selecionar materiais que **complementem o restante do projeto**.

---

# Próximos livros

Novos materiais podem ser adicionados conforme o projeto evoluir.

A intenção é manter a coleção relativamente pequena e relevante, priorizando **qualidade e complementaridade**, em vez de simplesmente aumentar a quantidade de livros.
