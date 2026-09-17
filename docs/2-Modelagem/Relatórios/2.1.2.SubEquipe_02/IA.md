# Uso de Inteligência Artificial Generativa

## 1. Descrição e Objetivo

Este documento registra o apoio e o uso de ferramentas de **Inteligência Artificial Generativa (IAG)** na **Entrega 2** pela **SubEquipe 02**. O objetivo é apresentar com transparência, senso crítico e rastreabilidade como os modelos de linguagem foram utilizados no processo de engenharia de software, na construção e validação da **Modelagem Estática (Diagrama de Pacotes)** e da **Modelagem Dinâmica (Diagrama de Atividades)**, bem como na documentação no MkDocs.

A abordagem adotada priorizou o uso da IA como um **agente colaborador e acelerador**, mantendo o rigor técnico, a revisão humana constante e a tomada de decisão final sob responsabilidade exclusiva dos integrantes da equipe.

---

## 2. Metodologia do Foco

A coleta de depoimentos e dados de uso ocorreu de forma **assíncrona e individual**. Cada integrante contribuiu com sua própria avaliação crítica e relatos de prompts/experimentos, garantindo a autoria e a perspectiva individualizada do aprendizado.

### Ferramentas Empregadas
* **Gemini:** Utilizado para processar o fluxo detalhado em texto e converter as regras de negócio em código estruturado para a geração automática do diagrama no PlantUML, além de auxiliar na validação lógica e sintática do modelo.
* **PlantUML:** Ferramenta *open-source* baseada em código estruturado (sintaxe declarativa) para renderização automática de diagramas UML.

---

## 3. Experimento com IA Generativa nas Modelagens

Como parte da avaliação das versões finais da entrega, a subequipe realizou um **experimento de geração e validação** aplicável às duas frentes de modelagem da Entrega 2:

### Experimento 01: Modelagem Dinâmica (Diagrama de Atividades)

#### Objetivo: 
Testar a capacidade do modelo de linguagem (Gemini) em interpretar o fluxo textual do sistema pós-login e convertê-lo diretamente em código PlantUML para a geração automática do Diagrama de Atividades, avaliando a precisão do código gerado e a qualidade da imagem resultante.

#### Resultado Obtido (1ª Iteração):

![Prompt](../assets/subequipe02-modelos/IA/Prompt.png)

<center><strong>Legenda:</strong> Figura 1 - Prompt enviado à IA com o fluxo estruturado em texto</center>

![Codigo Resultado](../assets/subequipe02-modelos/IA/Codigo.png)

<center><strong>Legenda:</strong> Figura 2 - Código PlantUML gerado pela IA</center>

![errado](../assets/subequipe02-modelos/IA/Errado.png)

<center><strong>Legenda:</strong> Figura 3 - Diagrama incorreto gerado pela primeira iteração do PlantUML</center>

#### **Análise Crítica e Intervenção Humana (1ª Iteração):** 
Ao compilar o código gerado, foi identificado um erro estrutural na diagramação: as raias (*swimlanes*) foram duplicadas incorretamente devido a falhas na sintaxe declarativa do PlantUML. Embora a sequência lógica de passos estivesse em conformidade com o texto fornecido, os rótulos de transição nas setas e a organização visual ficaram comprometidos.

Para corrigir o problema, foi realizada uma nova iteração enviando o código acompanhado de uma captura de tela do erro para a IA.

#### Resultado Obtido (2ª Iteração):

![Prompt](../assets/subequipe02-modelos/IA/Prompt2.png)

<center><strong>Legenda:</strong> Figura 4 - Prompt de correção enviado com a imagem do erro</center>

![Prompt](../assets/subequipe02-modelos/IA/codigo2.png)

<center><strong>Legenda:</strong> Figura 5 - Código corrigido retornado pela IA</center>

![Corrigido](../assets/subequipe02-modelos/IA/Corrigido.png)

<center><strong>Legenda:</strong> Figura 6 - Diagrama com raias e sintaxe corrigidas no PlantUML</center>

#### **Análise Crítica e Intervenção Humana:** 
A segunda iteração corrigiu com sucesso a estrutura das raias e a sintaxe lógica das decisões e agrupamentos. No entanto, a imagem exportada diretamente pelo compilador do PlantUML apresentou limitações técnicas significativas de renderização: baixa resolução gráfica, problemas de escala nos textos e pixelização dos elementos em diagramas mais extensos.

Diante dessa restrição estética e de legibilidade para a documentação oficial do projeto, optou-se por utilizar o código validado pela IA como um **gabarito lógico**, realizando o redesenho vetorial completo e manual do Diagrama de Atividades dentro do Figma. Dessa forma, garantiu-se alta definição visual, padronização tipográfica e perfeita alinhamento com a identidade visual da entrega.

---

## 4. Análise Crítica e Lições Aprendidas

Abaixo estão consolidados os aspectos avaliados durante a experimentação de IA Generativa na construção e validação dos artefatos de modelagem:

* **Cobertura Conceitual:** A IA demonstrou alta eficiência em mapear todos os caminhos principais e alternativos descritos no fluxo textual, garantindo que nenhum passo da navegação pós-login fosse omitido.
* **Legibilidade e Organização:** O layout gerado automaticamente pelo PlantUML apresentou limitações de espaçamento e sobreposição visual, exigindo intervenção no Figma para obter uma disposição gráfica clara.
* **Aderência à Técnica UML:** A estrutura lógica gerada seguiu os padrões da OMG para Diagramas de Atividades, utilizando corretamente nós de início/fim, decisões, partições e bifurcações .
* **Influência do Prompting:** Prompts textuais diretos funcionaram bem para a lógica inicial, mas a inclusão de imagens do erro na segunda iteração foi decisiva para que a IA corrigisse as falhas de sintaxe do PlantUML.
* **Editabilidade dos Artefatos:** A geração em código (PlantUML) acelerou a alteração rápida de fluxos e validação de regras, enquanto a versão vetorial no Figma viabilizou ajustes finos de layout.
* **Confiabilidade e Validação:** Os resultados da IA exigem revisão humana rigorosa; a primeira resposta continha erros de sintaxe que comprometeram a renderização do diagrama.
* **Limites do Experimento:** O PlantUML se mostrou limitado para a exportação final de diagramas complexos em alta resolução, apresentando pixelização que inviabilizou seu uso direto na documentação.

---

## 5. Pontos de Vista Individuais

### Ana Beatriz 
* **GitHub:** [@AnnaBeatrizAraujo](https://github.com/AnnaBeatrizAraujo)

* **Uso da IA Generativa (Senso Crítico):** Lorem ipsum dolor sit amet, consectetur adipiscing elit...

* **Lições Aprendidas:**
  Lorem ipsum dolor sit amet, consectetur adipiscing elit...

---

### Gustavo Fornaciari

* **GitHub:** [@GUGOFO](https://github.com/GUGOFO)

* **Uso da IA Generativa (Senso Crítico):** Utilizei o Gemini para converter a especificação textual do fluxo do sistema em código PlantUML e validar a coerência lógica do Diagrama de Atividades. A ferramenta funcionou de maneira excelente como um copiloto para aceleração sintática, permitindo estruturar em minutos um diagrama complexo com múltiplas raias e tomadas de decisão. No entanto, o experimento evidenciou as limitações da IA e do PlantUML no quesito de qualidade e acabamento visual: a imagem final gerada era de baixa resolução e pouco legível. O senso crítico foi essencial para entender que a IA resolveu a camada lógica, mas o trabalho de engenharia e design visual exigiu o redesenho manual no Figma para entregar um artefato com padrão profissional.

* **Lições Aprendidas:**
  A principal lição foi compreender o papel da IA Generativa como aceleradora de etapas intermediárias e não como uma solução fim a fim. Ela reduz drasticamente o tempo gasto com a sintaxe inicial e a checagem de regras, mas a lapidação final, a garantia de legibilidade e a escolha estética dependem exclusivamente do julgamento técnico e do trabalho humano.

---

### Vitor Leandro
* **GitHub:** [@Afrontoso](https://github.com/Afrontoso)

* **Uso da IA Generativa (Senso Crítico):** Lorem ipsum dolor sit amet, consectetur adipiscing elit...

* **Lições Aprendidas:**
  Lorem ipsum dolor sit amet, consectetur adipiscing elit...

---

## 6. Síntese do Aprendizado da Subequipe

Lorem ipsum dolor sit amet, consectetur adipiscing elit...

---

## 7. Ferramentas Utilizadas

* **[Gemini](https://gemini.google.com/app):** Modelo de linguagem utilizado para geração e correção de código PlantUML e validação de fluxos.
* **[PlantUML](https://www.plantuml.com/plantuml/uml/):** Ferramenta de modelagem *code-based* para compilação e renderização sintática de diagramas UML.
* **[Figma](https://www.figma.com/):** Editor gráfico vetorial utilizado para o redesenho e exportação em alta resolução do Diagrama de Atividades.

---

## Histórico de Versionamento

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositório | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) |
| [Artur Galdino](https://github.com/ArturFGaldino) e [Nicole Jovita](https://github.com/nicolejovita) | Criação do template da documentação de IA Generativa, experimentos e relatos | 17/09/2026 | [8ddaf26](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/8ddaf262b0619515620ef2f029cc1ae973b3626f) |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Consolidação do experimento de IA no Diagrama de Atividades, análise crítica e depoimento individual | 17/09/2026 | [cbc2910](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/cbc291011901135eddbe798db4fd4650e2530000) |