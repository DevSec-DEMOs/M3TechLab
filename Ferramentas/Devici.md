
# Devici

O **Devici**, da Security Compass, é uma plataforma de **Threat Modeling** que ajuda equipes de desenvolvimento, arquitetura e segurança a identificar riscos em sistemas de software antes e durante seu desenvolvimento.

Em vez de esperar que uma aplicação esteja pronta para procurar vulnerabilidades, o Threat Modeling começa olhando para o próprio sistema:

- O que estamos construindo?
- Quais são seus componentes?
- Como eles se comunicam?
- Quais dados são movimentados?
- O que aconteceria se uma parte do sistema fosse comprometida?
- Quais ameaças precisamos considerar?
- O que podemos fazer para reduzir esses riscos?

O Devici transforma essas informações em um modelo visual do sistema e utiliza frameworks e bibliotecas de ameaças para ajudar a identificar riscos e possíveis mitigações.

---

## O que é Threat Modeling?

**Threat Modeling**, ou Modelagem de Ameaças, é uma técnica utilizada para identificar possíveis ameaças a um sistema antes que elas se transformem em problemas.

Imagine que você está desenvolvendo uma aplicação de uma universidade.

Ela possui:

```text
                    Usuário
                       |
                       v
                  Aplicação Web
                       |
              +--------+--------+
              |                 |
              v                 v
          Banco de Dados    API Externa
```

Esse desenho já permite fazer algumas perguntas:

- O usuário pode acessar diretamente o banco de dados?
- A aplicação valida corretamente as informações recebidas?
- O que acontece se a API externa estiver comprometida?
- Quais informações ficam armazenadas no banco?
- Quem pode acessar essas informações?
- Existe alguma comunicação que deveria ser protegida?

Essas perguntas são parte do processo de Threat Modeling.

O objetivo não é prever todos os ataques possíveis.

O objetivo é **identificar os riscos relevantes para o sistema enquanto ainda existe oportunidade de tomar decisões de arquitetura e desenvolvimento para reduzi-los**.

---

## Por que fazer Threat Modeling?

Um problema de segurança pode ser muito mais fácil de corrigir quando é descoberto durante o desenho de um sistema do que depois que o sistema já está desenvolvido e em produção.

Por exemplo, imagine que uma equipe decida armazenar informações sensíveis em um serviço externo.

Durante o desenho da arquitetura, alguém percebe que:

```text
Aplicação
    |
    v
Serviço externo
    |
    v
Dados sensíveis
```

possui riscos que não foram considerados.

É possível então discutir autenticação, autorização, criptografia, segregação de dados e outros controles antes de implementar a solução.

Se o mesmo problema for descoberto somente depois que a aplicação estiver pronta, a correção pode exigir alterações no código, infraestrutura, banco de dados e processos de operação.

Por isso, Threat Modeling está relacionado ao conceito de **Security by Design**: considerar segurança como parte do desenho do sistema, e não como uma atividade realizada somente depois.

---

# O que o Devici faz?

O Devici utiliza uma abordagem baseada em diagramas.

Você pode representar:

- componentes;
- sistemas;
- usuários;
- bancos de dados;
- APIs;
- fluxos de dados;
- integrações;
- limites de confiança.

A partir dessas informações, a plataforma ajuda a identificar ameaças e possíveis mitigações.

De forma simplificada:

```text
Arquitetura
     |
     v
Modelo do sistema
     |
     v
Identificação de ameaças
     |
     v
Análise dos riscos
     |
     v
Mitigações
     |
     v
Decisões de segurança
```

A plataforma utiliza bibliotecas de ameaças e frameworks como **STRIDE** e **LINDDUN** para auxiliar nesse processo.

O Devici também possui recursos de IA que podem ajudar a identificar atributos e ameaças relacionadas ao sistema.

---

# Plano gratuito

O Devici possui um plano **Free**, sem limite de tempo e sem necessidade de cartão de crédito.

O plano gratuito permite:

| Recurso                               | Plano gratuito |
| ------------------------------------- | -------------: |
| Threat Models                         |         Até 3 |
| Usuários                             |         Até 3 |
| Frameworks                            |            10+ |
| Biblioteca de ameaças e mitigações |            Sim |
| Canvas visual                         |            Sim |
| Colaboração em tempo real           |       Limitada |
| Histórico e versionamento            |            Sim |
| AI Diagram Assistant                  |       Limitado |
| AI-assisted attributes                |       Limitado |
| CodeGenius                            |           Não |

O plano gratuito é suficiente para estudantes experimentarem o conceito de Threat Modeling e criarem modelos de sistemas próprios.

Um ponto importante é que o **CodeGenius não faz parte do plano gratuito**. Ele está disponível no plano Enterprise.

O CodeGenius é o recurso que permite analisar um repositório de código e gerar automaticamente um primeiro Threat Model a partir do que foi encontrado no projeto.

> Os recursos e limites dos planos podem mudar. Consulte a página oficial do Devici antes de utilizar a ferramenta em um projeto real.

---

# Por que utilizar o Devici para estudar?

Para quem está começando em cibersegurança, o Devici é interessante porque apresenta uma forma diferente de pensar sobre segurança.

Em vez de começar perguntando:

> "Qual vulnerabilidade existe no meu código?"

podemos começar perguntando:

> "Como esse sistema funciona e o que pode dar errado?"

Essa mudança de perspectiva é importante para quem pretende trabalhar com desenvolvimento, arquitetura ou segurança.

Um estudante pode, por exemplo, pegar um projeto simples de faculdade e tentar modelá-lo:

```text
                     Usuário
                        |
                        v
                  Front-end Web
                        |
                        v
                   Back-end API
                    /       \
                   /         \
                  v           v
             Banco de      Serviço
              Dados        Externo
```

Depois, pode começar a fazer perguntas sobre cada componente e cada comunicação.

Esse exercício ajuda a desenvolver uma habilidade importante: **pensar em segurança antes de procurar uma ferramenta específica para encontrar vulnerabilidades**.

---

# Como começar

## 1. Criar uma conta

Acesse:

https://www.devici.com/

ou utilize a opção de acesso disponível no site da Security Compass.

O plano gratuito não exige cartão de crédito.

---

## 2. Criar um Threat Model

Depois de entrar na plataforma, crie um novo **Threat Model**.

Um Threat Model é simplesmente uma representação estruturada de um sistema e das ameaças que podem afetá-lo.

Para o primeiro exercício, não tente modelar uma aplicação grande.

Comece com algo simples.

Por exemplo:

```text
Usuário
   |
   v
Aplicação Web
   |
   v
Banco de Dados
```

---

## 3. Desenhar os componentes

Comece adicionando os principais componentes do sistema.

Por exemplo:

- usuário;
- aplicação web;
- API;
- banco de dados.

Depois, represente como eles se comunicam.

O objetivo neste momento não é produzir um diagrama perfeito.

O objetivo é entender a arquitetura do sistema.

---

## 4. Pensar nos dados

Depois de representar os componentes, pergunte:

**Que dados passam por cada conexão?**

Por exemplo:

```text
Usuário
   |
   | Credenciais
   v
Aplicação
   |
   | Dados pessoais
   v
Banco de Dados
```

Isso é importante porque diferentes tipos de dados podem gerar diferentes riscos.

Uma aplicação que processa apenas informações públicas não possui exatamente os mesmos riscos de uma aplicação que processa:

- senhas;
- dados financeiros;
- informações pessoais;
- dados médicos;
- informações corporativas.

---

## 5. Identificar ameaças

Depois de representar o sistema, comece a pensar no que poderia dar errado.

Pergunte, por exemplo:

- Alguém pode se passar por outro usuário?
- Alguém pode modificar informações?
- Alguém pode acessar dados que não deveria?
- Alguma informação sensível pode ser exposta?
- Algum componente pode ficar indisponível?
- Podemos confiar em todas as partes do sistema?

O Devici utiliza frameworks como **STRIDE** e **LINDDUN** para ajudar nessa identificação.

---

# Primeiro exercício

Para o primeiro exercício, recomendamos utilizar um sistema que você já conheça.

Pode ser:

- um projeto da faculdade;
- um trabalho de conclusão de curso;
- uma aplicação desenvolvida em um curso;
- um pequeno projeto pessoal;
- uma aplicação web simples.

### Exercício

1. Escolha uma aplicação.
2. Liste os principais componentes.
3. Desenhe esses componentes no Devici.
4. Identifique como eles se comunicam.
5. Identifique quais tipos de dados são movimentados.
6. Identifique onde existem limites entre componentes que não possuem o mesmo nível de confiança.
7. Utilize o Devici para identificar ameaças.
8. Escolha três ameaças encontradas.
9. Para cada uma, pense em uma possível mitigação.
10. Registre as decisões no Threat Model.

O objetivo não é criar um modelo perfeito.

O objetivo é aprender a olhar para uma aplicação e perguntar:

> **"O que pode dar errado?"**

---

# Exemplo prático

Imagine uma aplicação universitária para consulta de notas.

A arquitetura poderia ser:

```text
                    Aluno
                      |
                      v
                Portal Web
                      |
                      v
                   API
                  /   \
                 /     \
                v       v
          Banco de    Sistema
           Dados      Acadêmico
```

O banco de dados contém:

```text
- Nome
- Matrícula
- Disciplinas
- Notas
```

Agora podemos começar a fazer perguntas.

### Autenticação

Como sabemos que o usuário realmente é aquele aluno?

### Autorização

Um aluno pode consultar as notas de outro aluno?

### Integridade

Um usuário poderia modificar uma nota?

### Confidencialidade

As informações poderiam ser interceptadas ou expostas?

### Disponibilidade

O que acontece se o sistema acadêmico ficar indisponível?

Essas perguntas transformam um simples diagrama de arquitetura em uma análise de segurança.

---

# STRIDE

**STRIDE** é um framework utilizado para identificar categorias de ameaças.

O nome é formado pelas iniciais de seis categorias:

| Letra | Categoria              | Ideia principal                       |
| ----- | ---------------------- | ------------------------------------- |
| S     | Spoofing               | Alguém se passando por outra pessoa  |
| T     | Tampering              | Alteração indevida de informações |
| R     | Repudiation            | Negação de uma ação realizada     |
| I     | Information Disclosure | Exposição indevida de informações |
| D     | Denial of Service      | Indisponibilidade de um serviço      |
| E     | Elevation of Privilege | Obtenção de privilégios indevidos  |

Por exemplo:

Se uma aplicação possui uma área de login, podemos perguntar:

> É possível alguém se passar por outro usuário?

Isso nos leva à categoria **Spoofing**.

Se um usuário consegue alterar uma nota que deveria apenas visualizar:

> É possível modificar uma informação indevidamente?

Isso está relacionado a **Tampering**.

Se um aluno consegue acessar informações de outro aluno:

> Existe exposição indevida de informação?

Isso está relacionado a **Information Disclosure**.

O objetivo do STRIDE não é fornecer automaticamente todas as respostas.

Ele fornece uma **estrutura para fazer perguntas sistematicamente**.

---

# LINDDUN

**LINDDUN** é outro framework de Threat Modeling, mas com foco em **privacidade**.

Enquanto STRIDE é bastante utilizado para analisar ameaças de segurança, LINDDUN ajuda a pensar em riscos relacionados à privacidade e ao tratamento de dados.

Isso é especialmente relevante quando uma aplicação coleta informações sobre pessoas.

Por exemplo:

```text
Usuário
   |
   | Dados pessoais
   v
Aplicação
   |
   v
Banco de Dados
```

Podemos perguntar:

- Estamos coletando dados demais?
- Quem consegue acessar esses dados?
- Para que eles estão sendo utilizados?
- É possível identificar uma pessoa a partir desses dados?
- Os dados estão sendo armazenados por mais tempo do que deveriam?

O Devici disponibiliza STRIDE e LINDDUN no plano gratuito.

---

# O papel da IA

O Devici possui recursos de IA que podem ajudar durante a construção do Threat Model.

Por exemplo, a plataforma pode auxiliar na identificação de atributos e ameaças a partir das informações fornecidas sobre o sistema.

Isso pode ser especialmente útil para quem está começando e ainda não possui muita experiência em Threat Modeling.

Entretanto, a IA não deve ser tratada como autoridade final.

O objetivo é utilizar suas sugestões como ponto de partida e então analisar se elas realmente fazem sentido para o sistema.

Em segurança:

```text
IA
 ↓
Sugestão
 ↓
Análise humana
 ↓
Decisão
```

A decisão final deve considerar o contexto real da aplicação.

---

# Threat Modeling e desenvolvimento de software

Threat Modeling não precisa ser uma atividade realizada somente por uma equipe de segurança.

Desenvolvedores, arquitetos e profissionais de infraestrutura também podem participar.

Isso se relaciona a uma ideia importante de **DevSecOps**: segurança não deve ser uma etapa isolada no final do desenvolvimento.

Em *O Projeto Fênix*, uma das ideias centrais é a necessidade de melhorar o fluxo de trabalho entre Desenvolvimento, Operações e outras áreas, além de reduzir os ciclos de feedback e evitar que problemas sejam descobertos tarde demais.

A mesma lógica pode ser aplicada à segurança.

Em vez de:

```text
Desenvolver
     ↓
Publicar
     ↓
Descobrir problema de segurança
     ↓
Corrigir
```

podemos tentar:

```text
Projetar
   ↓
Pensar em segurança
   ↓
Desenvolver
   ↓
Testar
   ↓
Publicar
   ↓
Observar e melhorar
```

Quanto mais cedo um problema relevante for identificado, maior tende a ser a capacidade da equipe de tomar uma decisão de arquitetura antes que mudanças mais caras sejam necessárias.

---

# CodeGenius

O **CodeGenius** é um recurso do Devici que permite utilizar um repositório de código como ponto de partida para criar um Threat Model.

Ele analisa um repositório GitHub e pode identificar:

- componentes;
- fluxos de dados;
- integrações;
- elementos da aplicação.

A partir dessas informações, o Devici gera um primeiro modelo que pode ser posteriormente revisado e editado.

O CodeGenius suporta, entre outras, as seguintes linguagens:

- JavaScript;
- TypeScript;
- Python;
- Java;
- C#;
- C;
- C++.

**Importante:** o CodeGenius está disponível no plano Enterprise, portanto não faz parte do exercício gratuito deste material.

Para estudantes, o exercício manual de construir o Threat Model é, na verdade, uma boa forma de aprender o conceito antes de utilizar automação.

---

# Glossário

## Threat

Uma ameaça ou situação que pode causar impacto negativo sobre um sistema.

## Threat Model

Um modelo que representa um sistema, seus componentes, seus fluxos e as ameaças relevantes para ele.

## Threat Modeling

Processo de identificar e analisar ameaças durante o desenvolvimento de um sistema.

## Mitigation

Uma medida utilizada para reduzir ou eliminar determinado risco.

## Security by Design

Prática de considerar segurança durante o desenho e desenvolvimento de um sistema, em vez de tratá-la apenas depois que o sistema está pronto.

## Trust Boundary

Um limite entre partes de um sistema que possuem diferentes níveis de confiança.

Por exemplo:

```text
Internet
   |
   | Trust Boundary
   v
Aplicação
   |
   | Trust Boundary
   v
Banco de Dados
```

Uma requisição que vem da Internet normalmente deve ser tratada com um nível de confiança diferente de uma comunicação interna entre componentes controlados pela própria organização.

## STRIDE

Framework utilizado para categorizar ameaças de segurança em seis grupos: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service e Elevation of Privilege.

## LINDDUN

Framework utilizado para identificar ameaças relacionadas à privacidade.

## AppSec

Abreviação de **Application Security**, ou Segurança de Aplicações.

É a área dedicada à proteção de aplicações durante seu desenvolvimento e operação.

## DevSecOps

Combinação de **Development, Security and Operations**.

Representa a integração de práticas de segurança ao processo de desenvolvimento e operação de software.

---

# Continuando os estudos

Depois de criar seu primeiro Threat Model, tente repetir o exercício com sistemas diferentes.

Uma boa progressão seria:

1. Aplicação simples com banco de dados.
2. Aplicação com API externa.
3. Aplicação com autenticação.
4. Aplicação com diferentes níveis de usuário.
5. Aplicação utilizando Cloud.
6. Aplicação utilizando containers.
7. Aplicação utilizando serviços de terceiros.
8. Aplicação que utiliza Inteligência Artificial.

Para cada sistema, tente responder:

> **O que estamos construindo?**

> **Quais são os componentes?**

> **Como os componentes se comunicam?**

> **Quais dados são movimentados?**

> **Onde estão os limites de confiança?**

> **O que pode dar errado?**

> **Como podemos reduzir esses riscos?**

Esse processo é mais importante do que simplesmente aprender a utilizar uma ferramenta específica.

---

# Documentação e referências

- [Devici](https://www.securitycompass.com/devici/)
- [Devici Pricing](https://www.securitycompass.com/devici/pricing/)
- [Security Compass](https://www.securitycompass.com/)
- [Threat Modeling](https://www.securitycompass.com/blog/what-a-great-threat-modeling-review-looks-like/)
- [STRIDE](https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-threats)
- [LINDDUN](https://linddun.org/)
