# Uso de Inteligência Artificial Generativa

---

## 1. Descrição e Objetivo

Este documento registra o apoio e o uso de ferramentas de **Inteligência Artificial Generativa (IAG)** na **Entrega 2** pela **SubEquipe XX**. O objetivo é apresentar com transparência, senso crítico e rastreabilidade como os modelos de linguagem foram utilizados no processo de engenharia de software, na construção e validação da **Modelagem Estática (Diagrama de XXXXX)** e da **Modelagem Dinâmica (Diagrama de XXXXX)**, bem como na documentação no MkDocs.

A abordagem adotada priorizou o uso da IA como um **agente colaborador e acelerador**, mantendo o rigor técnico, a revisão humana constante e a tomada de decisão final sob responsabilidade exclusiva dos integrantes da equipe.

---

## 2. Metodologia do Foco

A coleta de depoimentos e dados de uso ocorreu de forma **assíncrona e individual**. Cada integrante contribuiu com sua própria avaliação crítica e relatos de prompts/experimentos, garantindo a autoria e a perspectiva individualizada do aprendizado.

### Ferramentas Empregadas
* **Ferramenta (versão)** Descrever como foi utilizada brevemente.
* **Ferramenta (versão)** Descrever como foi utilizada brevemente.

---

## 3. Experimento com IA Generativa nas Modelagens (opcional)

Como parte da avaliação das versões finais da entrega, a subequipe realizou um **experimento de geração e validação** aplicável às duas frentes de modelagem da Entrega 2:

### Experimento 01: Modelagem Estática (Diagrama de pacotes)
#### Objetivo: 
Verificar se uma IA generativa (Claude Sonnet 3.5) é capaz de produzir um **Diagrama de Pacotes UML** coerente com o domínio do aplicativo **MeuSUS Digital**, a partir de artefatos visuais já elaborados pela equipe. Para isso, foram anexados ao prompt três insumos de entrada — a **Rich Picture**, o **BPMN** e o **SIG (NFR Framework)** — acompanhados da instrução: *"De acordo com a rich picture, o BPMN e o SIG anexados, faça uma modelagem estática através de um diagrama de pacotes para o fluxo indicado do site/app MeuSUS."* O resultado gerado pela IA foi então comparado com a **Versão 1.0** do diagrama de pacotes construída manualmente pela subequipe, com o objetivo de identificar diferenças de estrutura, notação, granularidade e adequação às convenções UML.

#### Resultado Obtido: 

![Resultado](../assets/subequipe01-modelos/modelagem-estatica/exp_modelagem-estatica.png)


<center><strong>Legenda:</strong> Diagrama de Pacotes gerado pela IA a partir da Rich Picture, BPMN e SIG do MeuSUS Digital</center>

![Prompt](../assets/subequipe01-modelos/modelagem-estatica/prompt-exp_modelagem-estatica.png)

<center><strong>Legenda:</strong> Prompt fornecido à IA com os três artefatos visuais anexados (Rich Picture, BPMN e SIG)</center>

A IA gerou um diagrama com estrutura **hierárquica vertical**, contendo os seguintes pacotes estereotipados:

- **`«application»` App MeuSUS Digital (Apresentação)** — camada de topo representando a interface do aplicativo.
- **`«subsystem»` Gestão de Consentimento (LGPD)**, **`«subsystem»` Integração de Dados Clínicos (HL7 FHIR)** e **`«subsystem»` Autenticação & Autorização (OAuth2/OIDC + PKCE)** — três subsistemas centrais.
- **`«infrastructure»` Auditoria & Log (Hash SHA-256 / LGPD)** e **`«infrastructure»` Armazenamento Seguro (Secure Storage / AES-256)** — pacotes de infraestrutura.
- **`«external system»` RNDS / DATASUS (API Clínica FHIR)** e **`«external system»` Gov.BR (Provedor de Identidade)** — sistemas externos representados explicitamente.
- **`«kernel»` Segurança & Criptografia (TLS 1.3 / mTLS / JWKS / RS256)** — camada de base consumida por todos os demais.

As dependências utilizaram os estereótipos `<<use>>` e `<<import>>` com rótulos descritivos (ex.: `REST API / HL7 FHIR`, `Authorization Code + PKCE`).

#### **Análise Crítica e Intervenção Humana:** 

A comparação entre o resultado gerado pela IA e a **Versão 1.0** do diagrama de pacotes (de autoria de [Artur Galdino](https://github.com/ArturFGaldino)) revelou diferenças estruturais e conceituais significativas:

1. **Abordagem arquitetural distinta:** a Versão 1.0 adota uma disposição **horizontal com quatro pacotes de mesmo nível** (`Presentation`, `Authentication`, `SecurityAndCompliance`, `HealthIntegration`), cada um contendo subpacotes técnicos internos. A IA, por outro lado, gerou uma estrutura **hierárquica vertical** com camadas explícitas (`«application»` → `«subsystem»` → `«infrastructure»`/`«external system»` → `«kernel»`). Embora a abordagem da IA seja visualmente interessante e demonstre capacidade de organização em camadas, a Versão 1.0 da equipe é mais adequada para um diagrama de pacotes UML puro, pois evidencia com clareza as fronteiras modulares e os subpacotes internos de cada módulo.

2. **Granularidade e subpacotes:** a Versão 1.0 detalha subpacotes técnicos dentro de cada pacote (ex.: `OAuthClient`, `PKCEHandler`, `TokenValidator` dentro de `Authentication`; `FHIRClient`, `NetworkGateway` dentro de `HealthIntegration`). A IA **não criou subpacotes** — as informações técnicas foram colocadas apenas entre parênteses nos rótulos dos pacotes (ex.: `Autenticação & Autorização (OAuth2/OIDC + PKCE)`). Isso reduz a utilidade do diagrama para a fase de projeto, pois não permite visualizar a decomposição interna de cada módulo.

3. **Representação de sistemas externos:** a IA incluiu explicitamente os pacotes `«external system»` para **RNDS/DATASUS** e **Gov.BR**, o que é um ponto positivo por tornar visíveis as fronteiras do sistema com o ambiente externo. A Versão 1.0 não representa sistemas externos diretamente — eles são apenas referenciados indiretamente por meio de seus clientes (`FHIRClient`, `OAuthClient`). Essa contribuição da IA foi considerada válida e pode ser incorporada em versões futuras.

4. **Uso de estereótipos UML:** a IA utilizou estereótipos ricos como `«application»`, `«subsystem»`, `«infrastructure»`, `«external system»` e `«kernel»`, que são mais típicos de **Diagramas de Componentes** do que de **Diagramas de Pacotes** segundo a especificação UML. A Versão 1.0 utiliza a notação correta de pacotes (retângulo com aba) sem estereótipos adicionais, o que é mais aderente à semântica formal do diagrama de pacotes. Esse ponto evidencia uma tendência da IA de **misturar notações** de diferentes diagramas UML.

5. **Tipos de dependência:** a IA empregou tanto `<<use>>` quanto `<<import>>` com rótulos descritivos (ex.: `<<import>> REST API / HL7 FHIR`), enquanto a Versão 1.0 padronizou **todas** as dependências como `<<use>>`, o que é mais simples e igualmente correto para este nível de abstração. O uso de `<<import>>` pela IA não está incorreto tecnicamente, mas adiciona uma distinção semântica (visibilidade pública dos elementos importados) que não foi intencionada pela equipe nesta etapa.

6. **Centralização da segurança:** a IA concentrou toda a segurança em um único pacote `«kernel»` na base do diagrama, enquanto a Versão 1.0 distribui as responsabilidades de segurança no pacote `SecurityAndCompliance` (com `SecureStorage`, `ConsentManager`, `AuditLogger`). A abordagem da Versão 1.0 é mais granular e facilita a rastreabilidade de requisitos não funcionais (LGPD, auditoria, criptografia) a módulos específicos.

7. **Idioma e nomenclatura:** a IA gerou nomes em **português** (Gestão de Consentimento, Integração de Dados Clínicos), enquanto a Versão 1.0 adota **inglês técnico** (SecurityAndCompliance, HealthIntegration). A padronização em inglês foi mantida pela equipe para garantir consistência com convenções de código e interoperabilidade com padrões técnicos internacionais (FHIR, OAuth 2.0).

**Conclusão do Experimento:** a IA demonstrou capacidade de interpretar artefatos visuais e propor uma organização arquitetural coerente em alto nível. Porém, o resultado gerou um diagrama que se aproxima mais de um **Diagrama de Componentes** do que de um **Diagrama de Pacotes**, misturando notações e estereótipos. A ausência de subpacotes internos e a nomeação em português também divergem das convenções adotadas pela equipe. O experimento reforça que a IA é útil como **ponto de partida para brainstorming arquitetural**, mas a modelagem final requer intervenção humana para garantir aderência à notação UML correta, granularidade adequada e consistência com os padrões definidos pelo projeto.

### Experimento 02: Modelagem Dinâmica (Diagrama de XXXXX)
#### Objetivo: 
Descrever o objetivo do teste com IA.
#### Resultado Obtido: 
(inserir imagem do resultado da versão gerada por IA)

<center><strong>Legenda:</strong> Inserir legenda</center>

(imagem do prompt dado)

<center><strong>Legenda:</strong> Inserir legenda</center>


#### **Análise Crítica e Intervenção Humana:** 
Explicar pontos que a IA corrigiu e o que foi acatado pela equipe ou não e por que - citar extrapolação e limites do uso da IA.

---

## 4. Análise Crítica e Lições Aprendidas

Abaixo estão consolidados os aspectos avaliados durante a experimentação de IA Generativa na construção e validação dos artefatos de modelagem:

* **Cobertura Conceitual:** XXXXX.
* **Legibilidade e Organização:** XXXXX.
* **Aderência à Técnica UML:** XXXXX.
* **Influência do Prompting:** XXXXX.
* **Editabilidade dos Artefatos:** OXXXXX.
* **Confiabilidade e Validação:** XXXXX.
* **Limites do Experimento:** XXXXX.

---

## 5. Pontos de Vista Individuais

### Artur Galdino
* **GitHub:** [@ArturFGaldino](https://github.com/ArturFGaldino)

* **Uso da IA Generativa (Senso Crítico):** Lorem ipsum dolor sit amet, consectetur adipiscing elit...

* **Lições Aprendidas:**
  Lorem ipsum dolor sit amet, consectetur adipiscing elit...

---

### Giovani Coelho
* **GitHub:** [@Gotc2607](https://github.com/Gotc2607)

* **Uso da IA Generativa (Senso Crítico):** Lorem ipsum dolor sit amet, consectetur adipiscing elit...

* **Lições Aprendidas:**
  Lorem ipsum dolor sit amet, consectetur adipiscing elit...
---

### João Leles
* **GitHub:** [@joaoleless](https://github.com/joaoleless)

* **Uso da IA Generativa (Senso Crítico):** Utilizei IA generativa para acelerar a modelagem visual do diagrama de colaboração UML, mas todo o conteúdo técnico foi validado por mim antes de ser aceito. Ao revisar a primeira versão gerada, identifiquei que a notação de moldura (Diagram Frame) e o cabeçalho pentagonal precisavam seguir estritamente a especificação oficial de UML, e não apenas uma aproximação visual — pedi correções específicas até o resultado condizer com a convenção formal. Também conferi manualmente a lógica de cada mensagem numerada (ex.: a ordem do fluxo OAuth 2.0/PKCE e o momento exato da verificação de consentimento LGPD) para garantir que a IA não tivesse alterado a semântica do processo apenas para "encaixar" visualmente as setas. A ferramenta foi tratada como um assistente de produtividade para desenhar e formatar, não como fonte de decisão arquitetural.

* **Lições Aprendidas:** Aprendi que gerar um diagrama estruturalmente correto é diferente de gerar um diagrama semanticamente correto — a IA pode produzir uma peça visualmente convincente com pequenos erros de direção de seta ou de nomenclatura que só um revisor com conhecimento do domínio percebe. Também reforcei a importância de seguir rigorosamente as convenções da UML (nomeação de instância no formato `instancia: Classe`, distinção entre linha de comunicação e seta de disparo, uso correto de expressões de guarda) em vez de aceitar qualquer representação "parecida". Por fim, entendi que documentar versão a versão o que mudou e por quê é tão importante quanto o próprio diagrama, pois isso torna as decisões de design rastreáveis para o restante da equipe.

---

### Nicole Jovita
* **GitHub:** [@nicolejovita](https://github.com/nicolejovita)

* **Uso da IA Generativa (Senso Crítico):** Lorem ipsum dolor sit amet, consectetur adipiscing elit...

* **Lições Aprendidas:**
  Lorem ipsum dolor sit amet, consectetur adipiscing elit...

---

## 6. Síntese do Aprendizado da Subequipe

Lorem ipsum dolor sit amet, consectetur adipiscing elit...

---

## 7. Referências e Ferramentas Utilizadas

* **Ferramenta (versão):** Descrição do uso e link para a ferramenta.
* Colocar link para atas da subequipe caso pertinente (por exemplo, uso de transcricao automatica da gravacao com IA - nesse caso citar anteriormente no uso de IA)
* Experimentos com IA (link puxando para a secao 3 desse documento caso tenham optado por inserir)

---

## Histórico de Versionamento

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositorio | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) |
| [Artur Galdino](https://github.com/ArturFGaldino) e [Nicole Jovita](https://github.com/nicolejovita) | Criação do template da documentação de IA Generativa, experimentos e relatos | 17/09/2026 | [8ddaf26](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/8ddaf262b0619515620ef2f029cc1ae973b3626f) |
| [João Leles](https://github.com/joaoleless) | Relato de uso de IA Generativa | 17/09/2026 | [c4547eb](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/c4547eb16406dc3d11a1b329f62436a3a73ef251) |