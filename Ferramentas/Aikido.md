# Aikido Security

O Aikido Security é uma plataforma de **Application Security (AppSec)** que reúne diferentes ferramentas de segurança para analisar aplicações, código-fonte, dependências e infraestrutura.

Ela pode ser utilizada para encontrar problemas de segurança durante o desenvolvimento de software, ajudando desenvolvedores e equipes de tecnologia a identificar e corrigir vulnerabilidades antes que elas cheguem aos usuários.

Este material foi desenvolvido para estudantes universitários que estão começando a conhecer **desenvolvimento de software, Cloud e cibersegurança**. Não é necessário ter experiência prévia em segurança.

## O que é o Aikido?

Quando desenvolvemos uma aplicação, existem diversos lugares onde problemas de segurança podem aparecer.

Por exemplo:

- no código escrito pelos desenvolvedores;
- nas bibliotecas utilizadas pelo projeto;
- em senhas ou chaves que foram acidentalmente publicadas;
- na configuração da infraestrutura;
- em imagens de containers;
- na própria aplicação quando ela está funcionando.

O Aikido reúne diferentes tipos de análises para procurar esses problemas em uma única plataforma.

De forma simplificada:

```text
                     Aplicação
                         |
        +----------------+----------------+
        |                |                |
      Código       Dependências      Infraestrutura
        |                |                |
       SAST             SCA              IaC
        |
   Secrets Detection
        |
     Container
        |
       DAST
```

A ideia é permitir que problemas de segurança sejam encontrados durante o processo de desenvolvimento, e não somente depois que uma aplicação já foi colocada em produção.

## O que podemos analisar?

Entre os principais recursos da plataforma estão:

- **SAST**
- **SCA**
- **Secrets Detection**
- **License Scanning**
- **IaC**
- **Container Scanning**
- **DAST**
- **API Security**
- **Cloud Security**
- **SBOM**
- **IDE Plugins**

A disponibilidade e os limites de cada recurso dependem do plano utilizado.

## Plano gratuito

O Aikido possui um plano gratuito voltado para desenvolvedores.

Esse plano pode ser utilizado para estudar a plataforma e experimentar diferentes recursos de segurança sem a necessidade de contratar uma licença comercial.

Entre os limites informados para o plano gratuito estão:

| Recurso | Limite |
|---|---:|
| Usuários | 2 |
| Repositórios | 10 |
| Imagens de Container | 2 |
| Domínios | 1 |
| Contas Cloud | 1 |
| AI AutoFix | 10 por mês |
| Protected Requests | 250 mil/mês |
| Rescan automático | A cada 3 dias |

O plano gratuito também disponibiliza diversos recursos de análise, incluindo SAST, SCA, Secrets Detection, IaC, Container Scanning e DAST.

> Os planos, limites e recursos de produtos comerciais podem mudar. Consulte a página oficial do Aikido antes de utilizar a ferramenta em um projeto real.

## Por que utilizar o Aikido para estudar?

Uma das vantagens para quem está começando é que o Aikido permite conhecer diferentes conceitos de segurança de aplicações dentro de uma mesma plataforma.

Por exemplo, ao analisar um projeto, você pode encontrar problemas relacionados a:

```text
Código
  ↓
SAST

Bibliotecas
  ↓
SCA

Credenciais
  ↓
Secrets Detection

Infraestrutura
  ↓
IaC

Containers
  ↓
Container Scanning

Aplicação em execução
  ↓
DAST
```

Assim, você não precisa aprender apenas uma ferramenta.

Você começa a entender **como a segurança pode ser aplicada ao desenvolvimento de software**.

## Como começar

### 1. Criar uma conta

Acesse:

https://app.aikido.dev/

Você pode iniciar o cadastro utilizando uma conta de um provedor de código, como GitHub, GitLab ou Bitbucket.

O plano gratuito não exige cartão de crédito.

### 2. Começar pelo projeto de demonstração

Se você ainda não possui um projeto próprio, uma boa maneira de começar é utilizar o projeto de demonstração disponibilizado pela plataforma.

Isso permite conhecer a interface e observar exemplos de problemas de segurança sem precisar conectar imediatamente um projeto pessoal.

Ao criar a conta, procure pela opção relacionada ao **sample/demo repository**.

### 3. Conectar um projeto

Depois de conhecer a plataforma, você pode conectar um repositório próprio.

Um **repositório** é o local onde um projeto de software é armazenado, normalmente utilizando ferramentas como GitHub, GitLab ou Bitbucket.

Para este laboratório, você pode utilizar:

- um projeto pessoal;
- um projeto acadêmico;
- um projeto desenvolvido durante um curso;
- um projeto de exemplo;
- um projeto criado especificamente para estudar segurança.

Depois de conectar o repositório, o Aikido realiza a análise e apresenta os problemas encontrados.

## Primeiro exercício

Para começar, escolha um projeto pequeno.

Não é necessário criar uma aplicação complexa. Um simples projeto desenvolvido em uma disciplina da faculdade ou durante um curso já pode ser suficiente.

### Exercício

1. Escolha um projeto pequeno.
2. Publique o projeto em um repositório GitHub.
3. Crie uma conta gratuita no Aikido.
4. Conecte sua conta do GitHub.
5. Selecione o repositório.
6. Aguarde a primeira análise.
7. Observe os problemas encontrados.
8. Identifique em qual categoria cada problema se encontra.
9. Escolha um problema para investigar.
10. Tente entender por que ele foi identificado.

O objetivo deste exercício **não é simplesmente eliminar todos os problemas encontrados**.

O objetivo é aprender a interpretar uma ferramenta de segurança.

Para cada problema, tente responder:

> **O que foi encontrado?**

> **Por que isso pode representar um risco?**

> **Como esse problema poderia ser corrigido?**

## O que observar durante a análise

Ao navegar pela plataforma, tente identificar quais problemas estão relacionados a:

- código;
- bibliotecas;
- credenciais;
- infraestrutura;
- containers;
- aplicações em execução.

Não se preocupe em entender todas as categorias imediatamente.

O mais importante neste primeiro contato é perceber que **segurança de software possui diferentes tipos de problemas e, consequentemente, diferentes formas de análise**.

## Cuidados durante o laboratório

Ao conectar um projeto ao Aikido ou a qualquer outra ferramenta de segurança, tenha cuidado com as informações presentes no repositório.

Nunca utilize credenciais reais em projetos de teste.

Evite colocar em um repositório:

- senhas;
- API Keys;
- tokens;
- chaves privadas;
- credenciais de Cloud;
- informações pessoais;
- dados de clientes.

Se quiser estudar a detecção de secrets, utilize valores fictícios ou credenciais criadas especificamente para o laboratório.

# Entendendo os principais termos

A plataforma utiliza diversas siglas comuns na área de segurança. Você não precisa conhecê-las antes de começar.

## SAST — Static Application Security Testing

É a análise de segurança do **código-fonte** de uma aplicação.

A ferramenta procura padrões de código que podem indicar uma vulnerabilidade.

Por exemplo, imagine uma aplicação que recebe informações de um usuário e utiliza essa informação de maneira insegura.

O SAST pode analisar o código e apontar esse comportamento antes mesmo de a aplicação ser executada.

```text
Código-fonte
     ↓
   SAST
     ↓
Possível vulnerabilidade
```

## SCA — Software Composition Analysis

É a análise das **dependências** utilizadas por uma aplicação.

Projetos modernos raramente são construídos completamente do zero. É comum utilizar bibliotecas e pacotes desenvolvidos por outras pessoas ou organizações.

O SCA verifica esses componentes para identificar problemas conhecidos.

Por exemplo:

```text
Sua aplicação
     |
     +-- Biblioteca A
     |
     +-- Biblioteca B
     |
     +-- Biblioteca C
                 ↓
       Vulnerabilidade conhecida
```

Se uma biblioteca utilizada pelo seu projeto possuir uma vulnerabilidade conhecida, o SCA pode identificá-la.

## DAST — Dynamic Application Security Testing

É a análise de uma aplicação **enquanto ela está funcionando**.

Em vez de olhar somente para o código, o DAST interage com a aplicação e procura comportamentos que possam representar vulnerabilidades.

Uma diferença simples:

```text
SAST
Analisa o código

DAST
Analisa a aplicação em execução
```

## Secrets Detection

É a detecção de **informações sensíveis expostas** dentro de um projeto.

Pode procurar por coisas como:

- API Keys;
- tokens;
- senhas;
- credenciais;
- chaves privadas.

Um exemplo comum é um desenvolvedor colocar acidentalmente uma chave de acesso diretamente em um arquivo do projeto.

```text
Código
   ↓
API Key exposta
   ↓
Secrets Detection
   ↓
Alerta
```

## IaC — Infrastructure as Code

Significa **Infrastructure as Code**, ou Infraestrutura como Código.

É uma forma de definir infraestrutura utilizando arquivos de código.

Em vez de configurar tudo manualmente, ferramentas como Terraform e Kubernetes permitem descrever a infraestrutura em arquivos que podem ser versionados e automatizados.

Por exemplo, um arquivo pode definir:

```text
Criar servidor
Criar rede
Criar banco de dados
Configurar permissões
```

O problema é que esses arquivos também podem conter configurações inseguras.

A análise de IaC procura esse tipo de problema.

## Container Scanning

Containers são uma forma de empacotar uma aplicação juntamente com os componentes necessários para executá-la.

Docker é um exemplo de tecnologia muito utilizada para trabalhar com containers.

Uma imagem de container pode conter diversos componentes, incluindo bibliotecas e partes de um sistema operacional.

O **Container Scanning** procura vulnerabilidades nesses componentes.

```text
Imagem Docker
     |
     +-- Sistema operacional
     +-- Bibliotecas
     +-- Dependências
     +-- Aplicação
             ↓
      Container Scanning
```

## SBOM — Software Bill of Materials

SBOM significa **Software Bill of Materials**.

É uma lista dos componentes que fazem parte de um software.

Uma forma simples de entender é imaginar uma lista de ingredientes:

```text
Aplicação
├── Python
├── Framework X
├── Biblioteca Y
├── Biblioteca Z
└── Outros componentes
```

O SBOM ajuda a responder:

> **Quais componentes existem dentro deste software?**

Isso pode ser importante quando uma nova vulnerabilidade é descoberta e precisamos descobrir quais aplicações utilizam o componente afetado.

## AppSec — Application Security

AppSec significa **Application Security**, ou Segurança de Aplicações.

É a área dedicada à segurança dos softwares e aplicações.

SAST, SCA, DAST e Secrets Detection são exemplos de técnicas e ferramentas utilizadas dentro desse universo.

De forma simplificada:

```text
                AppSec
                  |
       +----------+----------+
       |          |          |
      SAST       SCA        DAST
       |
 Secrets Detection
       |
      IaC
       |
 Container Security
```

## DevSecOps

DevSecOps é a combinação de:

**Development + Security + Operations**

Em português:

**Desenvolvimento + Segurança + Operações**

A ideia principal é incorporar segurança ao processo de desenvolvimento de software, em vez de deixar todos os testes de segurança para o final.

Um processo tradicional pode ser imaginado assim:

```text
Desenvolver
    ↓
Testar
    ↓
Publicar
    ↓
Verificar segurança
```

Em uma abordagem DevSecOps:

```text
Desenvolver
    ↓
Testar
    ↓
Analisar segurança
    ↓
Corrigir
    ↓
Publicar
```

A segurança passa a fazer parte do processo de desenvolvimento.

## CI/CD — Continuous Integration / Continuous Delivery

CI/CD representa práticas utilizadas para automatizar etapas do desenvolvimento e entrega de software.

Um pipeline pode, por exemplo:

```text
Desenvolvedor
      ↓
     Git
      ↓
  Pipeline
      ↓
   Testes
      ↓
 Segurança
      ↓
    Build
      ↓
   Deploy
```

Um **pipeline** é basicamente uma sequência automatizada de etapas.

Ferramentas de segurança podem ser colocadas dentro desse processo para verificar o código e outros componentes automaticamente.

# Continuando os estudos

Depois de realizar o primeiro exercício, tente explorar os diferentes tipos de análise disponíveis no Aikido.

Uma possível ordem de estudo é:

1. SAST
2. SCA
3. Secrets Detection
4. Container Scanning
5. IaC
6. DAST
7. SBOM
8. CI/CD
9. DevSecOps

A ideia não é memorizar as siglas.

O mais importante é entender **qual problema cada uma dessas tecnologias tenta resolver e em que momento ela pode ser utilizada no desenvolvimento de software**.

# Documentação e referências

- [Aikido Security](https://www.aikido.dev/)
- [Aikido Pricing](https://www.aikido.dev/pricing)
- [Aikido Documentation](https://help.aikido.dev/)
- [Aikido Developer Hub](https://apidocs.aikido.dev/)
