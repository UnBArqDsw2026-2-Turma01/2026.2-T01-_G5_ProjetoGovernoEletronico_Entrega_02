# Uso de Inteligência Artificial Generativa

## 1. Descrição e Objetivo

Este documento registra o apoio e o uso de ferramentas de **Inteligência Artificial Generativa (IAG)** na **Entrega 2** pela **SubEquipe 02**. O objetivo é apresentar com transparência, senso crítico e rastreabilidade como os modelos de linguagem foram utilizados no processo de engenharia de software, na construção e validação da **Modelagem Estática (Diagrama de Pacotes)** e da **Modelagem Dinâmica (Diagrama de Atividades)**, bem como na documentação no MkDocs.

A abordagem adotada priorizou o uso da IA como um **agente colaborador e acelerador**, mantendo o rigor técnico, a revisão humana constante e a tomada de decisão final sob responsabilidade exclusiva dos integrantes da equipe.

---

## 2. Metodologia do Foco

A coleta de depoimentos e dados de uso ocorreu de forma **assíncrona e individual**. Cada integrante contribuiu com sua própria avaliação crítica e relatos de prompts/experimentos, garantindo a autoria e a perspectiva individualizada do aprendizado.

### Ferramentas Empregadas
* **Gemini:** Utilizado para processar o fluxo detalhado em texto e converter as regras de negócio em código estruturado para a geração automática do diagrama no PlantUML, além de auxiliar na validação lógica e sintática do modelo.
* **NotebookLM:** Utilizado para auditar as imagens dos diagramas no Figma com base na bibliografia da disciplina.
* **PlantUML:** Ferramenta *open-source* baseada em código estruturado (sintaxe declarativa) para renderização automática de diagramas UML.

---

## 3. Experimento com IA Generativa nas Modelagens por Frente de Trabalho

Como parte da avaliação da Entrega 2, os integrantes da subequipe aplicaram IAG nas diferentes versões e evoluções dos artefatos estáticos e dinâmicos:

### Experimento 01: Diagrama de Atividades
**Responsável:** Gustavo Fornaciari

#### Objetivo
Testar a capacidade do modelo de linguagem (Gemini) em interpretar o fluxo textual do sistema pós-login e convertê-lo diretamente em código PlantUML para a geração automática do Diagrama de Atividades, avaliando a precisão do código gerado e a qualidade da imagem resultante.

#### Resultado Obtido (1ª Iteração)
<p align="center">
  <img src="../assets/subequipe02-modelos/IA/Prompt.png" width="50%" alt="Prompt enviado à IA">
</p>
<center><strong>Legenda:</strong> Figura 1 - Prompt enviado à IA com o fluxo estruturado em texto.</center>

<p align="center">
  <img src="../assets/subequipe02-modelos/IA/Codigo.png" width="50%" alt="Código PlantUML gerado pela IA">
</p>
<center><strong>Legenda:</strong> Figura 2 - Código PlantUML gerado pela IA.</center>

<p align="center">
  <img src="../assets/subequipe02-modelos/IA/Errado.png" width="50%" alt="Diagrama incorreto gerado no PlantUML">
</p>
<center><strong>Legenda:</strong> Figura 3 - Diagrama incorreto gerado pela primeira iteração do PlantUML.</center>

#### Análise Crítica e Intervenção Humana (1ª Iteração)
Ao compilar o código gerado, foi identificado um erro estrutural na diagramação: as raias (*swimlanes*) foram duplicadas incorretamente devido a falhas na sintaxe declarativa do PlantUML. Embora a sequência lógica de passos estivesse em conformidade com o texto fornecido, os rótulos de transição nas setas e a organização visual ficaram comprometidos. Para corrigir o problema, foi realizada uma nova iteração enviando o código acompanhado de uma captura de tela do erro para a IA.

#### Resultado Obtido (2ª Iteração)
<p align="center">
  <img src="../assets/subequipe02-modelos/IA/Prompt2.png" width="50%" alt="Prompt de correção enviado à IA">
</p>
<center><strong>Legenda:</strong> Figura 4 - Prompt de correção enviado com a imagem do erro.</center>

<p align="center">
  <img src="../assets/subequipe02-modelos/IA/codigo2.png" width="50%" alt="Código corrigido retornado pela IA">
</p>
<center><strong>Legenda:</strong> Figura 5 - Código corrigido retornado pela IA.</center>

<p align="center">
  <img src="../assets/subequipe02-modelos/IA/Corrigido.png" width="50%" alt="Diagrama com raias corrigidas no PlantUML">
</p>
<center><strong>Legenda:</strong> Figura 6 - Diagrama com raias e sintaxe corrigidas no PlantUML.</center>

#### Análise Crítica e Intervenção Humana

A segunda iteração corrigiu com sucesso a estrutura das raias e a sintaxe lógica das decisões e agrupamentos. No entanto, a imagem exportada diretamente pelo compilador do PlantUML apresentou limitações técnicas significativas de renderização: baixa resolução gráfica e pixelização dos elementos. Diante disso, optou-se por utilizar o código validado pela IA como um **gabarito lógico**, realizando o redesenho vetorial completo dentro do Figma.

---


### Experimento 02: Diagrama de Atividades V2 e Diagrama de Pacotes V3
**Responsável:** Ana Beatriz

#### Objetivo
Utilizar o **NotebookLM** carregado com as fontes teóricas (material da profa. Milene Serrano, OMG UML 2.5.1 e livro do Guedes) para realizar revisões sobre as imagens dos diagramas gerados no Figma, identificando falhas de sintaxe UML, inconformidades de notação e omissões de conceito tanto no Diagrama de Atividades (V2) quanto no Diagrama de Pacotes (V3).

---
#### Parte 1: Validação do Diagrama de Atividades (V2)

##### Prompt Enviado
<p align="center">
  <img src="../assets/subequipe02-modelos/IA/prompt-atividades-notebooklm.png" width="50%" alt="Prompt de validação enviado ao NotebookLM">
</p>
<center><strong>Legenda:</strong> Figura 7 - Prompt de validação do Diagrama de Atividades enviado ao NotebookLM.</center>

##### Resultado Retornado pelo NotebookLM
<p align="center">
  <img src="../assets/subequipe02-modelos/IA/analise-atividades-notebooklm.jpg" width="50%" alt="Análise do Diagrama de Atividades retornado pelo NotebookLM">
</p>
<center><strong>Legenda:</strong> Figura 8 - Análise de sintaxe e lógica do Diagrama de Atividades retornado pelo NotebookLM.</center>

##### Análise Crítica e Intervenção Humana
A partir dos apontamentos da IA, reestruturei manualmente o diagrama no Figma reorganizando o traçado das setas para contornar os blocos sem sobreposições e unificando dois losangos redundantes em um único *Merge Node* para tratar os fluxos de sucesso e erro da RNDS. Também eliminei um nó cego ao conectar a ação de interação de volta à decisão de navegação, garantindo a continuidade lógica e a conformidade sintática da sessão.

---

#### Parte 2: Validação do Diagrama de Pacotes (V3)

##### Prompt Enviado
<p align="center">
  <img src="../assets/subequipe02-modelos/IA/prompt-pacotes-v3.png" width="50%" alt="Prompt enviado para validação da V3 do Diagrama de Pacotes">
</p>
<center><strong>Legenda:</strong> Figura 9 - Prompt enviado ao NotebookLM para auditoria da V3 do Diagrama de Pacotes.</center>

##### Resultado Retornado pelo NotebookLM
<p align="center">
  <img src="../assets/subequipe02-modelos/IA/resultado-pacotes-v3.png" width="50%" alt="Inconformidades estruturais apontadas pelo NotebookLM">
</p>
<center><strong>Legenda:</strong> Figura 10 - Inconformidades estruturais apontadas pelo NotebookLM na V3 do Diagrama de Pacotes.</center>

##### Análise Crítica e Intervenção Humana
Avaliando o relatório da IA, refatorei a modelagem no Figma substituindo um pacote duplicado pelo módulo `GestaoSaudeMental` na Aplicação e inserindo a entidade `RegistroAcolhimento` no Domínio. Além disso, ajustei o container gráfico da camada de Integração para enquadrar completamente o pacote de Hemocentros e adicionei o bloco externo `Serviço de Push` conectado via REST/API ao pacote de Notificações, garantindo a completude técnica da arquitetura.

---

### Experimento 03: Diagramas de Pacotes V1 e Atividades V1
**Responsável:** Victor Leandro

#### Objetivo
[Preenchimento futuro: Descreva a aplicação da IA na elaboração e validação da primeira versão do Diagrama de Pacotes e/ou do Diagrama de Atividades.]

#### Resultado Obtido e Iterações
*(Adicione os prints e iterações)*

#### Análise Crítica e Intervenção Humana
[Preenchimento futuro: Análise crítica sobre as respostas e intervenções manuais aplicadas.]

---

## 4. Análise Crítica e Lições Aprendidas

Abaixo estão consolidados os aspectos avaliados durante a experimentação de IA Generativa na construção e validação dos artefatos:

* **Cobertura Conceitual:** A IA demonstrou alta eficiência em mapear caminhos lógicos e apoiar a revisão notacional das especificações da OMG.
* **Legibilidade e Layout:** Layouts gerados automaticamente (ex: PlantUML) apresentam limitações de legibilidade e acabamento visual, exigindo redesign manual no Figma.
* **Aderência à Técnica UML:** A verificação de regras como fluxo *top-down* e uso de estereótipos (`«use»`, `«camada»`) é acelerada com IAG, mas requer conferência com a bibliografia da disciplina.
* **Influência do Prompting:** Prompts iterativos acompanhados de capturas de tela e trechos da norma resultam em correções sintáticas significativamente mais precisas.

---

## 5. Pontos de Vista Individuais

### Ana Beatriz 
* **GitHub:** [@AnnaBeatrizAraujo](https://github.com/AnnaBeatrizAraujo)

* **Uso da IA Generativa (Senso Crítico):** Utilizei a IAG (especificamente o NotebookLM abastecido com fontes confiaveis) para a validação arquitetural e notacional tanto do Diagrama de Atividades (V2) quanto da Versão 3 do Diagrama de Pacotes. A ferramenta auxiliou na checagem de conformidade com as regras de sintaxe da UML 2.5.1 (OMG e Guedes), na identificação de falhas de fluxo, nos nós de fusão (*Merge Nodes*) e na verificação do desacoplamento da camada de Mini Apps. A IA funcionou de forma excelente como auditora técnica para apontar erros no Figma.

* **Lições Aprendidas:**
 A principal lição foi compreender a importância do rigor notacional e da coesão estrutural na modelagem de sistemas complexos. Entendi na prática como aplicar o desacoplamento em camadas e a modularização de componentes (separando interface, aplicação e domínio nos Mini Apps), além de perceber que a rastreabilidade entre o BPMN e a modelagem UML é fundamental para garantir que o software reflita com precisão as regras de negócio do domínio da saúde.

---

### Gustavo Fornaciari

* **GitHub:** [@GUGOFO](https://github.com/GUGOFO)

* **Uso da IA Generativa (Senso Crítico):** Utilizei o Gemini para converter a especificação textual do fluxo do sistema em código PlantUML e validar a coerência lógica do Diagrama de Atividades. A ferramenta funcionou de maneira excelente como um copiloto para aceleração sintática, permitindo estruturar em minutos um diagrama complexo com múltiplas raias e tomadas de decisão. No entanto, o experimento evidenciou as limitações da IA e do PlantUML no quesito de qualidade e acabamento visual. O redesenho manual no Figma foi indispensável para entregar um artefato com padrão profissional.

* **Lições Aprendidas:**
  A principal lição foi compreender a importância da clareza notacional e da coesão estrutural na representação visual de sistemas de grande porte. Ao elaborar a **Primeira Versão (V1) do Diagrama de Atividades**, consolidei na prática o mapeamento de fluxos dinâmicos e o uso de partições (*swimlanes*) para delimitar claramente as responsabilidades entre as ações do cidadão e do sistema. Complementarmente, o desenvolvimento da **Segunda Versão (V2) do Diagrama de Pacotes** aprofundou meu entendimento sobre modularização, organização de subsistemas e controle de dependências arquiteturais, garantindo uma visão coerente, escalável e bem delimitada da aplicação.
---

### Victor Leandro
* **GitHub:** [@Afrontoso](https://github.com/Afrontoso)

* **Uso da IA Generativa (Senso Crítico):** [Preenchimento do Victor...]

* **Lições Aprendidas:**
  

---

## 6. Síntese do Aprendizado da Subequipe

A utilização da Inteligência Artificial Generativa ao longo da Entrega 2 permitiu otimizar o tempo de validação lógica e sintática tanto dos diagramas estáticos quanto dos dinâmicos. A experiência consolidou o entendimento de que a IAG é extremamente eficaz na prevenção de erros notacionais e na aceleração de rascunhos, mas que o trabalho de engenharia de software é um processo estritamente humano e reflexivo.



## Histórico de Versionamento

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositório | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) |
| [Artur Galdino](https://github.com/ArturFGaldino) e [Nicole Jovita](https://github.com/nicolejovita) | Criação do template da documentação de IA Generativa, experimentos e relatos | 17/09/2026 | [8ddaf26](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/8ddaf262b0619515620ef2f029cc1ae973b3626f) |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositório | 10/09/2026 | [cbc2910](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/cbc291011901135eddbe798db4fd4650e2530000) |
| [Ana Beatriz Araujo](https://github.com/AnnaBeatrizAraujo) | Modificações na estrutura do template e adição do experimento de IA Generativa | 17/09/2026 | [7873814](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/7873814) |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Atualizar Licoes Aprendidas | 10/09/2026 | [37c82b9](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) |
