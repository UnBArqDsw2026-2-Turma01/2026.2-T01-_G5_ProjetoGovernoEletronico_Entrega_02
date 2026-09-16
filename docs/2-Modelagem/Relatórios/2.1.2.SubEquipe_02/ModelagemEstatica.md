# Modelagem Estática

A modelagem estática da SubEquipe 02 foi feita com o **Diagrama de Pacotes** da UML, aplicado ao **Meu SUS Digital** — o mesmo sistema que a subequipe já havia analisado por Engenharia Reversa nos artefatos da Entrega 01 (Rich Picture, SIG e BPMN).

---

## Versão Final

![Diagrama de Pacotes do Meu SUS Digital - versão 1.0](../assets/subequipe02-modelos/modelagem-estatica/diagrama-pacotes-v1.0.png)

<center><strong>Legenda:</strong> Diagrama de Pacotes do Meu SUS Digital (v1.0) — organização do sistema em camadas lógicas, pacote transversal e dependências com os sistemas externos gov.br e RNDS.</center>

> **Arquivo editável:** [`diagrama-pacotes-v1.0.drawio`](../assets/subequipe02-modelos/modelagem-estatica/diagrama-pacotes-v1.0.drawio) — pode ser aberto diretamente em [app.diagrams.net](https://app.diagrams.net/) por qualquer membro que queira revisar ou evoluir o artefato.

---

## Participantes
| Nome do Membro |
| :--- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) |
| [Ana Beatriz](https://github.com/AnnaBeatrizAraujo) |
| [Victor Leandro](https://github.com/Afrontoso) |

---

## Fundamentação Teórica

O **Diagrama de Pacotes** é um diagrama **estrutural e organizacional** da UML. Segundo o material da disciplina, trata-se de "mais um diagrama estrutural, estático, o qual permite organizar o sistema como se representasse uma visão em módulos" (SERRANO, 2026). Ele não descreve comportamento nem detalha classes: seu papel é **agrupar elementos de modelagem em unidades maiores e mostrar como essas unidades dependem umas das outras**.

Na taxonomia apresentada em aula, a UML é dividida em diagramas estruturais/estáticos, comportamentais/dinâmicos, **organizacionais (ou em pacotes)** e anotacionais. O Diagrama de Pacotes ocupa justamente a fatia organizacional — é o diagrama que responde à pergunta *"como o sistema está dividido?"* antes de responder *"como cada parte funciona?"*.

### Elementos da notação utilizados

| Elemento | Representação | Uso neste artefato |
| :--- | :--- | :--- |
| **Pacote** | Retângulo com aba, no formato de pasta | Cada camada lógica e cada módulo interno do Meu SUS Digital |
| **Aninhamento** | Pacote desenhado dentro de outro | Os módulos internos (`Home`, `ConsultaDeRegistros`, …) dentro de suas camadas, e as camadas dentro da fronteira do sistema |
| **Dependência `«use»`** | Seta tracejada com ponta aberta | Um pacote precisa de outro para cumprir sua função; a ponta aponta para o pacote **fornecedor** |
| **Estereótipo** | Texto entre guilhemés (`«camada»`, `«sistema externo»`) | Classifica o papel de cada pacote, distinguindo camada interna, pacote transversal e sistema de terceiros |
| **Nota** | Retângulo com canto dobrado | Legenda da notação e tabela de rastreabilidade com o BPMN |

### Por que este diagrama para esta subequipe

Os três artefatos que a SubEquipe 02 produziu na Entrega 01 são todos **comportamentais ou contextuais**: o Rich Picture mostra atores e preocupações, o SIG mostra requisitos não funcionais e o BPMN mostra o fluxo do processo. Faltava uma visão que respondesse **onde**, na estrutura do software, cada um desses comportamentos vive.

O Diagrama de Pacotes preenche exatamente essa lacuna, e faz isso no nível de abstração compatível com o que a Engenharia Reversa caixa-preta permite afirmar. Como o Meu SUS Digital não tem código-fonte publicado, **não é honesto modelar um Diagrama de Classes** — não há como conhecer atributos, operações ou multiplicidades reais. Já os módulos e as dependências entre eles são inferíveis a partir do comportamento observado nas telas e das integrações que o próprio sistema expõe ao usuário. O pacote é, portanto, a menor unidade sobre a qual a subequipe consegue fazer afirmações verificáveis.

---

## Desenvolvimento

### Versão 1

**Autoria:** [Victor Leandro](https://github.com/Afrontoso)

![Diagrama de Pacotes - versão 1](../assets/subequipe02-modelos/modelagem-estatica/diagrama-pacotes-v1.0.png)

<center><strong>Legenda:</strong> Primeira versão do Diagrama de Pacotes — quatro camadas internas, um pacote transversal e dois sistemas externos.</center>

#### O que foi feito

A modelagem partiu do BPMN produzido pela subequipe e converteu **responsabilidades observadas em fluxo** para **responsabilidades alocadas em módulos**. O sistema foi organizado em uma **arquitetura em camadas**, com dependências fluindo em sentido único (de cima para baixo), mais um pacote transversal.

**`Apresentação` «camada»** — tudo que o cidadão vê e opera. Reúne `Home` (a tela de entrada com a bifurcação por tipo de serviço), `MinhaSaude.UI` e `MiniApps.UI` (os dois grandes ramos que no BPMN viraram subprocessos colapsados) e `Avaliacao.UI` (a tela acionada pela notificação de avaliação pendente).

**`Aplicação` «camada»** — a orquestração dos casos de uso, isto é, a tradução de cada fluxo do BPMN em um módulo coordenador. `GestaoDeSessao` cobre o login federado e o reuso da sessão para consultar vários serviços sem refazer a autenticação; `ConsultaDeRegistros` cobre o subprocesso *Minha saúde*; `CatalogoDeMiniApps` cobre o subprocesso *Mini apps*; `AvaliacaoDeAtendimento` cobre o ciclo de notificação, resposta e retorno ao fluxo principal.

**`Domínio` «camada»** — os conceitos de negócio que existem independentemente de tela ou de protocolo de integração: `Cidadao`, `RegistroDeSaude` (vacinas, exames e atendimentos) e `Comprovante` (o documento gerado no gateway *Deseja comprovante?* do BPMN).

**`Integração` «camada»** — a fronteira técnica com o mundo externo. `AutenticacaoGovBr` isola o protocolo de login federado, `IntegracaoRNDS` isola o consumo dos dados clínicos e `Notificacoes` isola o disparo das mensagens que chegam ao cidadão.

**`Comum` «transversal»** — as preocupações que não pertencem a uma única camada: `SegurancaDeSessao` (guarda de token e encerramento de sessão), `PrivacidadeEConsentimento` (o consentimento explícito exigido quando um mini app usa dados pessoais, ponto levantado tanto no SIG quanto no BPMN) e `TratamentoDeFalhas` (a política de resposta a indisponibilidade, que na v2 do BPMN apareceu como evento de borda `RNDS indisponível`).

**Sistemas externos** — `gov.br` e `RNDS` foram mantidos **fora da fronteira do sistema** e desenhados com traço tracejado. Essa decisão é a tradução direta de como eles aparecem no BPMN: o gov.br era uma piscina fechada (*black box*), da qual só se conhecem as mensagens trocadas, e a RNDS era um depósito de dados externo. Modelá-los como pacotes internos afirmaria um conhecimento sobre a estrutura deles que a Engenharia Reversa não sustenta.

#### Decisões de modelagem e justificativas

| # | Decisão | Justificativa |
| :--- | :--- | :--- |
| 1 | Organizar em **camadas**, e não por funcionalidade (ex.: um pacote `Vacinas`, outro `Exames`) | O BPMN mostrou que os serviços compartilham o mesmo caminho: autenticar, consultar a RNDS, exibir, opcionalmente gerar comprovante. Pacotes por funcionalidade duplicariam essa estrutura três ou quatro vezes; camadas a representam uma vez só. |
| 2 | **Dependências em sentido único**, sempre de cima para baixo | Evita ciclos entre pacotes, que são o principal sintoma de acoplamento ruim em um diagrama organizacional. Nenhuma camada inferior conhece quem a utiliza. |
| 3 | Separar `Integração` de `Domínio` | Protege as regras de negócio de mudanças de protocolo: se a RNDS trocar de contrato, o impacto fica contido em `IntegracaoRNDS`, sem atingir `RegistroDeSaude`. |
| 4 | Criar `Comum` como pacote **transversal**, em vez de distribuir segurança e privacidade pelas camadas | Segurança, privacidade e tratamento de falhas foram justamente os pontos que o SIG e o Rich Picture destacaram como preocupações do projeto. Concentrá-los em um pacote os torna visíveis no diagrama, em vez de diluí-los. |
| 5 | Manter `gov.br` e `RNDS` **fora** da fronteira, com traço tracejado | Coerência com a piscina *black box* e o depósito de dados externo do BPMN. Marca explicitamente o limite do que a subequipe pode afirmar sobre o sistema. |
| 6 | Dependências para os externos partindo dos **pacotes internos**, e não da camada inteira | Mostra qual módulo especificamente conversa com cada terceiro, o que é a informação útil para quem for avaliar impacto de uma indisponibilidade. |
| 7 | Incluir `Notificacoes` mesmo sem ele aparecer como serviço na home | Na v2 do BPMN a avaliação de atendimento deixou de ser uma escolha do cidadão e virou um evento de mensagem disparado pelo sistema. Um disparador de mensagem é um módulo, e precisava de lugar na estrutura. |

#### Rastreabilidade com os artefatos anteriores

| Elemento do artefato anterior | Pacote correspondente |
| :--- | :--- |
| BPMN — piscina *black box* `gov.br (provedor de identidade)` | `gov.br` «sistema externo» + `AutenticacaoGovBr` |
| BPMN — depósito de dados `RNDS` | `RNDS` «sistema externo» + `IntegracaoRNDS` |
| BPMN — subprocesso colapsado `Minha saúde` | `MinhaSaude.UI` + `ConsultaDeRegistros` |
| BPMN — subprocesso colapsado `Mini apps` | `MiniApps.UI` + `CatalogoDeMiniApps` |
| BPMN — gateway `Deseja comprovante?` | `Comprovante` |
| BPMN — gateway `Usa dados pessoais?` | `PrivacidadeEConsentimento` |
| BPMN — evento de borda `RNDS indisponível` | `TratamentoDeFalhas` |
| BPMN — eventos de mensagem da avaliação de atendimento | `Notificacoes` + `AvaliacaoDeAtendimento` + `Avaliacao.UI` |
| BPMN — gateway `Consultar outro serviço?` (reuso da sessão) | `GestaoDeSessao` |
| Rich Picture — ator `Cidadão` | `Cidadao` |
| Rich Picture — ícones de Agendamento, Vacinação e Exames/Laudos | `RegistroDeSaude` |

#### Limitações identificadas nesta versão

- O diagrama trata o Meu SUS Digital como **uma única unidade implantável**. A separação real entre o que roda no aplicativo do cidadão e o que roda em servidor do Ministério da Saúde não é observável por Engenharia Reversa caixa-preta e, portanto, não foi afirmada aqui.
- As dependências estão **todas no estereótipo `«use»`**. A UML também oferece `«import»` e `«access»`, que distinguem se os elementos do pacote fornecedor passam a fazer parte do espaço de nomes do cliente — distinção que só faz sentido com acesso ao código e que ficou como possível refinamento para a V2.
- `Notificacoes` foi inferido a partir do comportamento observado, mas **nenhum provedor externo de push foi representado**, porque a subequipe não conseguiu observar qual serviço é usado.
- O pacote `Comum` agrupa três preocupações de natureza diferente (segurança, privacidade e resiliência). Se ele crescer nas próximas versões, vale avaliar se deve ser quebrado em pacotes irmãos.

### Versão 2

![Imagem Versao 2](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

Oque voce modificou e porque modificou

### Versão 3

![Imagem Versao 3](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

Oque voce modificou e porque modificou

---

## Metodologia

Seguindo a metodologia geral da equipe, a subequipe manteu a prática já adotada na Entrega 01: **partir sempre de um artefato existente, e não de uma folha em branco**. A modelagem estática foi construída em cima do BPMN que a própria subequipe havia produzido e revisado, de modo que cada pacote do diagrama pudesse ser justificado por um elemento concreto do fluxo modelado anteriormente — é essa a origem da tabela de rastreabilidade apresentada acima.

O processo seguiu quatro passos:

1. **Releitura dos artefatos da Entrega 01**, listando cada responsabilidade que o sistema demonstrou ter (autenticar, consultar, exibir, gerar comprovante, notificar, tratar indisponibilidade, pedir consentimento).
2. **Agrupamento das responsabilidades por afinidade**, buscando alta coesão dentro de cada grupo e o mínimo de conversa entre grupos.
3. **Escolha do critério de decomposição.** Foram consideradas duas alternativas — decompor por funcionalidade ou por camada — e a segunda foi adotada pelo motivo registrado na decisão nº 1 do quadro acima.
4. **Verificação do resultado**, conferindo a notação contra o material da disciplina e a referência da OMG, e checando que não havia dependência cíclica entre pacotes.

Como **particularidade da subequipe**, manteve-se a restrição metodológica assumida desde o BPMN: *não afirmar no modelo aquilo que a Engenharia Reversa caixa-preta não permite observar*. É por essa razão que o gov.br e a RNDS aparecem como pacotes externos tracejados, que o diagrama não desce ao nível de classes e que a separação cliente/servidor não foi representada. A seção de limitações existe justamente para deixar essa fronteira explícita em vez de escondê-la.

A ferramenta escolhida foi o **[diagrams.net (draw.io)](https://app.diagrams.net/)**, por ter as formas de pacote UML nativas, ser gratuita e produzir um arquivo-fonte versionável no repositório — o que permite que qualquer membro da equipe abra e evolua o artefato nas próximas versões sem depender de conta em serviço externo.

---

### Embasamento teórico para criação:

1. SERRANO, Milene. *Arquitetura e Desenho de Software — Aula: Modelagem UML Estática*. Brasília: FGA/UnB, 2026. 1 arquivo PDF.
2. OBJECT MANAGEMENT GROUP (OMG). *Unified Modeling Language (UML), Version 2.5.1*. Needham: OMG, 2017. Disponível em: https://www.omg.org/spec/UML/2.5.1/. Acesso em: 15 set. 2026.
3. UML DIAGRAMS. *UML Package Diagrams Overview*. Disponível em: https://www.uml-diagrams.org/package-diagrams-overview.html. Acesso em: 15 set. 2026.
4. CHIKOFSKY, Elliot J.; CROSS, James H. Reverse engineering and design recovery: a taxonomy. *IEEE Software*, Los Alamitos, v. 7, n. 1, p. 13-17, jan. 1990.
5. MARTIN, Robert C. *Clean Architecture: a craftsman's guide to software structure and design*. Boston: Prentice Hall, 2017. (Base para a regra de dependência em sentido único adotada entre as camadas.)

---

## Histórico de Versionamento

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositorio | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) |
| [Victor Leandro](https://github.com/Afrontoso) | Versão 1.0 da Modelagem Estática: Diagrama de Pacotes do Meu SUS Digital, fundamentação teórica, decisões de modelagem, rastreabilidade com o BPMN e metodologia | 15/09/2026 | |
