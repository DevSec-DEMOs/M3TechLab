# Manual de DevOps

**Gene Kim, Jez Humble, Patrick Debois e John Willis**

## Sobre este material

*Manual de DevOps* apresenta princípios e práticas para melhorar a forma como organizações desenvolvem, testam, entregam e operam software.

O livro parte de um problema simples:

> Quando Desenvolvimento, Operações e outras áreas trabalham de forma isolada, o sistema como um todo tende a ficar mais lento, mais difícil de controlar e mais propenso a falhas.

A proposta de DevOps é melhorar esse sistema como um todo, criando um fluxo mais rápido, feedback mais frequente e uma cultura de aprendizado contínuo.

Para o M3TechLab, este livro fornece a base conceitual para entender como software é desenvolvido e entregue antes de começar a adicionar práticas específicas de segurança.

---

# 1. O que é DevOps?

DevOps não é uma ferramenta, uma certificação ou simplesmente uma forma diferente de chamar uma equipe de infraestrutura.

É uma abordagem para melhorar o sistema de trabalho que existe entre:

- desenvolvimento;
- operações;
- qualidade;
- segurança;
- produto;
- negócio.

O objetivo é permitir que mudanças sejam realizadas de maneira mais rápida, segura e confiável, mantendo um ciclo contínuo de aprendizado.

Uma maneira simples de visualizar isso é:

```text
Ideia
  ↓
Código
  ↓
Build
  ↓
Teste
  ↓
Deploy
  ↓
Produção
  ↓
Feedback
  ↓
Nova mudança
```

Esse fluxo não termina quando o código é entregue.

A operação do software gera informações que devem voltar para quem desenvolve e mantém o sistema.

---

# 2. O problema que DevOps tenta resolver

Imagine uma empresa em que cada área trabalha separadamente:

```text
Desenvolvimento
      ↓
    "Terminei"
      ↓
      QA
      ↓
    "Testei"
      ↓
      Ops
      ↓
 "Vou colocar em produção"
```

Parece organizado.

O problema aparece quando algo dá errado.

Quem é responsável?

O desenvolvedor?

QA?

Operações?

Segurança?

O problema frequentemente percorre várias equipes antes de chegar a alguém capaz de corrigi-lo.

Isso cria:

- filas;
- espera;
- retrabalho;
- transferência de responsabilidade;
- perda de contexto;
- comunicação excessiva;
- trabalho manual;
- feedback tardio.

O *Projeto Fênix* ajuda a entender esses problemas através da história da Parts Unlimited.

O *Manual de DevOps* avança a discussão e apresenta princípios e práticas para melhorar esse sistema.

---

# 3. As Três Maneiras

Uma das ideias centrais do livro é organizar os princípios de DevOps em três grandes conjuntos:

```text
             DEVOPS

                │
       ┌────────┼────────┐
       ↓        ↓        ↓
     Fluxo   Feedback  Aprendizado
```

As três maneiras são:

1. **Fluxo**
2. **Feedback**
3. **Aprendizado contínuo e experimentação**

Elas não devem ser entendidas como três etapas que acontecem uma depois da outra.

São princípios que devem estar presentes continuamente no sistema.

---

# 4. Primeira Maneira: Fluxo

A primeira maneira trata de fazer o trabalho fluir pelo sistema de forma rápida e contínua.

Em uma empresa de software, o trabalho pode começar com uma necessidade do cliente e passar por diversas etapas até chegar à produção.

```text
Cliente
  ↓
Produto
  ↓
Desenvolvimento
  ↓
Testes
  ↓
Operações
  ↓
Produção
  ↓
Cliente
```

O objetivo não é fazer cada área trabalhar o mais rápido possível isoladamente.

O objetivo é melhorar o fluxo de todo o sistema.

## 4.1 Tornar o trabalho visível

Grande parte do trabalho tecnológico é invisível.

Uma tarefa pode estar:

- esperando um desenvolvedor;
- esperando um teste;
- esperando aprovação;
- esperando infraestrutura;
- esperando uma correção;
- esperando outra equipe.

Um quadro simples pode tornar isso evidente:

```text
Backlog → Desenvolvimento → Teste → Deploy → Produção
```

Assim podemos observar onde o trabalho está acumulando.

## 4.2 Limitar o trabalho em andamento

Um conceito importante é **WIP, Work in Progress**.

Imagine que uma equipe tenha dez tarefas abertas simultaneamente.

Em vez de terminar uma:

```text
Tarefa A → concluída
```

ela começa:

```text
A
B
C
D
E
F
G
H
I
J
```

O resultado pode ser muito trabalho parcialmente concluído e pouca coisa efetivamente entregue.

Limitar o WIP significa controlar a quantidade de trabalho simultâneo.

A ideia pode ser resumida como:

> Pare de começar e comece a terminar.

## 4.3 Trabalhar em lotes menores

Uma grande mudança acumulada durante semanas pode conter muitos problemas.

Uma mudança pequena é mais fácil de:

- testar;
- revisar;
- entender;
- implantar;
- reverter;
- corrigir.

Por isso, DevOps favorece mudanças menores e frequentes em vez de grandes lotes de trabalho.

Isso também possui uma consequência importante para segurança.

Uma alteração pequena facilita descobrir:

> "Qual mudança introduziu esse problema?"

---

# 5. Segunda Maneira: Feedback

A segunda maneira trata de criar mecanismos para descobrir rapidamente se aquilo que estamos fazendo está funcionando.

Sem feedback:

```text
Código
  ↓
Deploy
  ↓
Problema
  ↓
Descoberta muito depois
```

Com feedback:

```text
Código
  ↓
Teste
  ↓
Feedback
  ↓
Correção
  ↓
Novo teste
```

O feedback pode vir de diferentes lugares:

- testes automatizados;
- logs;
- métricas;
- monitoramento;
- usuários;
- incidentes;
- revisão de código;
- ferramentas de segurança.

Quanto mais rápido recebemos informação sobre um problema, mais cedo podemos agir.

---

# 6. Feedback também é segurança

Essa ideia é fundamental para entender **DevSecOps**.

Imagine que uma aplicação possua uma vulnerabilidade.

Existem diferentes momentos em que podemos descobrir isso:

```text
Desenvolvimento
      ↓
Testes
      ↓
Build
      ↓
Deploy
      ↓
Produção
      ↓
Ataque
```

Quanto mais tarde o problema aparece, maior tende a ser o impacto.

Por isso, ferramentas de segurança podem ser utilizadas como mecanismos de feedback dentro do processo de desenvolvimento.

Por exemplo:

```text
Git
 ↓
Pull Request
 ↓
Build
 ↓
SAST
 ↓
SCA
 ↓
Secret Scanning
 ↓
Testes
 ↓
Deploy
```

Aqui, segurança não é uma inspeção realizada somente antes da produção.

Ela passa a fazer parte do fluxo.

---

# 7. Terceira Maneira: Aprendizado contínuo

A terceira maneira trata de transformar experiências em aprendizado.

Sistemas complexos inevitavelmente apresentam:

- erros;
- falhas;
- incidentes;
- comportamentos inesperados;
- hipóteses incorretas.

O objetivo não deve ser simplesmente descobrir quem errou.

A pergunta mais importante é:

> O que podemos aprender com isso para melhorar o sistema?

Isso leva a práticas como:

- experimentação;
- retrospectivas;
- post-mortems;
- testes;
- compartilhamento de conhecimento;
- melhoria contínua.

Uma falha pode gerar conhecimento.

Esse conhecimento pode gerar uma mudança.

A mudança pode ser testada.

E o resultado gera novo feedback.

```text
Falha
 ↓
Aprendizado
 ↓
Mudança
 ↓
Experimento
 ↓
Feedback
 ↓
Melhoria
```

---

# 8. Automação

Automação aparece como um elemento fundamental das práticas DevOps.

Mas automatizar não significa simplesmente "usar uma ferramenta".

O objetivo é retirar trabalho repetitivo e tornar o processo mais consistente.

Por exemplo, em vez de alguém executar manualmente:

```text
1. Baixar código
2. Compilar
3. Executar testes
4. Gerar artefato
5. Copiar para servidor
6. Reiniciar aplicação
```

podemos transformar isso em um pipeline:

```text
Commit
  ↓
Build
  ↓
Testes
  ↓
Artefato
  ↓
Deploy
```

Isso reduz trabalho manual e permite repetir o processo de maneira consistente.

---

# 9. Integração contínua

**CI, Continuous Integration**, significa integrar mudanças de código frequentemente e validar essas mudanças automaticamente.

Um fluxo simples:

```text
Developer
    ↓
Commit
    ↓
Pipeline
    ↓
Build
    ↓
Testes
    ↓
Feedback
```

Se algo falhar, o desenvolvedor recebe essa informação rapidamente.

Isso é muito diferente de descobrir problemas depois de semanas de desenvolvimento.

---

# 10. Entrega e deployment de baixo risco

DevOps procura tornar mudanças menores e mais frequentes.

Uma consequência disso é reduzir o risco associado a cada alteração.

Uma mudança pequena pode ser:

- testada;
- monitorada;
- revertida;
- corrigida;

com maior facilidade.

Isso também muda a maneira como pensamos sobre segurança.

Em vez de tentar criar um processo que impeça qualquer mudança potencialmente perigosa, podemos criar mecanismos que permitam:

- detectar problemas;
- limitar impacto;
- reverter mudanças;
- corrigir rapidamente;
- aprender com os resultados.

---

# 11. Segurança da Informação como atividade de todos

Esta é uma das partes mais importantes do livro para o M3TechLab.

Segurança não deveria ser uma atividade realizada exclusivamente por uma equipe especializada no final do processo.

Ela precisa fazer parte do trabalho cotidiano.

Isso significa que desenvolvedores, operações, arquitetura e outras áreas também precisam considerar segurança durante o desenvolvimento e operação dos sistemas.

Em vez de:

```text
Desenvolvimento
      ↓
Operações
      ↓
Segurança
      ↓
"Aprovado?"
      ↓
Produção
```

podemos buscar:

```text
Desenvolvimento
      ↓
Testes + Automação + Segurança
      ↓
Operações
      ↓
Monitoramento
      ↓
Feedback
```

A segurança deixa de ser apenas um gate e passa a ser também um mecanismo de feedback.

---

# 12. DevSecOps

É aqui que podemos fazer a conexão com o restante do M3TechLab.

**DevSecOps** não significa simplesmente colocar uma ferramenta de segurança em uma pipeline.

A ideia é integrar segurança ao mesmo fluxo utilizado para desenvolver e entregar software.

Por exemplo:

```text
Código
  ↓
Pull Request
  ↓
Build
  ↓
Testes
  ↓
SAST
  ↓
SCA
  ↓
Secret Scanning
  ↓
Container Scanning
  ↓
Deploy
  ↓
Monitoramento
```

Cada controle fornece informações que podem ser utilizadas pela equipe.

O objetivo não é adicionar burocracia ao processo.

É produzir **feedback de segurança de forma rápida e integrada ao trabalho**.

---

# 13. Começando com poucos recursos

Uma das ideias mais importantes para uma pequena equipe é que não é necessário implementar tudo de uma vez.

Uma startup pode começar com:

```text
Git
 ↓
CI
 ↓
Testes automatizados
 ↓
SAST
 ↓
SCA
 ↓
Secret Scanning
```

Depois pode evoluir para:

```text
Container Security
IaC Security
DAST
Threat Modeling
Security Monitoring
```

A ordem exata dependerá do sistema, da arquitetura e dos riscos.

O importante é evitar a ideia de que segurança só pode começar quando a organização possui uma grande equipe dedicada.

---

# 14. Proteger o pipeline

O pipeline também é parte do sistema que precisa ser protegido.

Ele pode possuir acesso a:

- código;
- credenciais;
- secrets;
- artefatos;
- ambientes;
- infraestrutura;
- produção.

Portanto:

> Se alguém comprometer o pipeline, pode conseguir comprometer aquilo que o pipeline consegue acessar.

Isso torna importante considerar:

- autenticação;
- autorização;
- proteção de secrets;
- permissões mínimas;
- proteção dos repositórios;
- controle das alterações;
- segurança dos agentes de CI;
- segurança dos artefatos.

O pipeline não é apenas uma ferramenta de automação.

Ele faz parte da superfície de ataque da organização.

---

# 15. Segurança não deve criar feedback lento

Existe uma diferença importante entre:

**Controle de segurança**

e

**processo burocrático de segurança.**

Um controle automatizado pode fornecer feedback em minutos.

Um processo manual pode criar uma fila de dias.

Por isso, quando possível:

```text
Segurança
    ↓
Automação
    ↓
Feedback rápido
```

é preferível a:

```text
Desenvolvimento
    ↓
Solicitação
    ↓
Fila
    ↓
Revisão manual
    ↓
Aprovação
    ↓
Desenvolvimento
```

O objetivo não é eliminar controles necessários.

É encontrar formas de incorporá-los ao fluxo sem criar gargalos desnecessários.

---

# 16. O que isso significa para uma startup?

Uma equipe pequena normalmente possui recursos limitados.

Isso significa que ela precisa escolher cuidadosamente onde investir seu esforço.

Uma abordagem razoável é:

### 1. Automatizar o básico

```text
Git
CI
Build
Testes
```

### 2. Adicionar segurança ao fluxo

```text
SAST
SCA
Secrets
```

### 3. Proteger a infraestrutura de desenvolvimento

```text
CI/CD
Cloud
Containers
Secrets
```

### 4. Começar a pensar antes do código

```text
Threat Modeling
Arquitetura
Attack Paths
```

### 5. Aprender com o sistema em produção

```text
Logs
Métricas
Alertas
Incidentes
```

O processo pode evoluir conforme a empresa cresce.

---

# 17. DevOps não significa usar muitas ferramentas

É possível montar uma arquitetura extremamente complexa:

```text
GitHub
Jenkins
Kubernetes
Docker
Terraform
ArgoCD
Prometheus
Grafana
Vault
Aikido
Devici
...
```

e ainda assim ter um processo ruim.

Ferramentas são meios.

O objetivo é melhorar:

- fluxo;
- feedback;
- qualidade;
- segurança;
- confiabilidade;
- capacidade de aprendizado.

A pergunta não deveria ser:

> "Qual ferramenta DevOps devemos usar?"

Mas:

> "Qual problema do nosso fluxo estamos tentando resolver?"

---

# 18. Exercício M3TechLab

Imagine que você está criando uma pequena aplicação web para uma startup.

O processo atual é:

```text
Developer
   ↓
Código
   ↓
Teste manual
   ↓
Servidor
   ↓
Deploy
   ↓
Usuário
```

Agora redesenhe esse fluxo utilizando os princípios apresentados neste material.

Uma possibilidade:

```text
Developer
   ↓
Git
   ↓
Pull Request
   ↓
Build
   ↓
Testes automatizados
   ↓
Security Scanning
   ↓
Code Review
   ↓
Deploy
   ↓
Monitoramento
   ↓
Feedback
   ↓
Nova mudança
```

Agora responda:

1. Onde existem atividades manuais?
2. Onde existem filas?
3. Onde existe trabalho em andamento?
4. Onde podemos receber feedback mais cedo?
5. Onde podemos automatizar?
6. Onde a segurança entra?
7. O que acontece quando uma vulnerabilidade é encontrada?
8. O que acontece quando um teste falha?
9. Como podemos reduzir o tamanho das mudanças?
10. Como podemos aprender com uma falha?

---

# 19. Conectando o livro às ferramentas

O objetivo do M3TechLab não é apenas conhecer os conceitos.

É experimentar.

| Conceito | O que experimentar |
|---|---|
| Git | Criar e versionar um projeto |
| CI | Criar uma pipeline |
| Testes | Executar testes automaticamente |
| SAST | Encontrar problemas no código |
| SCA | Identificar vulnerabilidades em dependências |
| Secrets | Encontrar credenciais expostas |
| Threat Modeling | Identificar ameaças antes do desenvolvimento |
| CI/CD Security | Incorporar segurança ao pipeline |
| Monitoramento | Observar o comportamento da aplicação |
| Feedback | Corrigir problemas e repetir o ciclo |

Assim, o estudante não precisa apenas ler sobre DevSecOps.

Ele pode construir um pequeno projeto e experimentar os conceitos.

---

# 20. Relação com O Projeto Fênix

Os dois livros cumprem papéis diferentes.

| O Projeto Fênix | Manual de DevOps |
|---|---|
| Mostra os problemas | Apresenta princípios e práticas |
| Gargalos | Fluxo |
| Trabalho não planejado | Visualização do trabalho |
| Silos | Colaboração |
| Incidentes | Feedback |
| Aprendizado | Experimentação |
| Transformação organizacional | Práticas técnicas |
| Problemas de entrega | CI/CD e automação |
| Segurança como preocupação | Segurança integrada ao fluxo |

Uma maneira simples de lembrar:

> **O Projeto Fênix ajuda a entender por que o sistema de trabalho está quebrado. O Manual de DevOps apresenta princípios e práticas para começar a melhorá-lo.**

---

# 21. Conceitos para continuar estudando

Depois deste material, vale pesquisar:

- DevOps
- DevSecOps
- Agile
- Lean
- Value Stream
- Kanban
- WIP
- Continuous Integration
- Continuous Delivery
- Continuous Deployment
- CI/CD
- Infrastructure as Code
- Automated Testing
- Observability
- Telemetry
- SAST
- SCA
- Secret Scanning
- Container Security
- Threat Modeling
- Security Champions
- Shift Left
- Software Supply Chain Security

---

# 22. A principal ideia

DevOps não é sobre fazer software simplesmente mais rápido.

É sobre criar um sistema capaz de:

```text
Entregar
   ↓
Observar
   ↓
Aprender
   ↓
Melhorar
   ↓
Entregar novamente
```

Quando segurança é incorporada a esse ciclo, temos a base para uma abordagem de **DevSecOps**.

E o ponto mais importante para quem está começando é:

> **Segurança não precisa começar como um grande programa. Ela pode começar como pequenos controles automatizados, integrados ao fluxo de desenvolvimento, que fornecem feedback rápido e permitem que a equipe aprenda e evolua.**

---

# Referência

**KIM, Gene; HUMBLE, Jez; DEBOIS, Patrick; WILLIS, John. _Manual de DevOps_. 2020.**
