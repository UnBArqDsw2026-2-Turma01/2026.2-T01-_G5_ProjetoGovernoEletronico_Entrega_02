# Uso de Inteligência Artificial Generativa

---

## 1. Descrição e Objetivo

Este documento registra o apoio e o uso de ferramentas de **Inteligência Artificial Generativa (IAG)** na **Entrega 2** pela **SubEquipe XX**. O objetivo é apresentar com transparência, senso crítico e rastreabilidade como os modelos de linguagem foram utilizados no processo de engenharia de software, na construção e validação da **Modelagem Estática (Diagrama de XXXXX)** e da **Modelagem Dinâmica (Diagrama de Colaboração)**, bem como na documentação no MkDocs.

A abordagem adotada priorizou o uso da IA como um **agente colaborador e acelerador**, mantendo o rigor técnico, a revisão humana constante e a tomada de decisão final sob responsabilidade exclusiva dos integrantes da equipe.

---

## 2. Metodologia do Foco

A coleta de depoimentos e dados de uso ocorreu de forma **assíncrona e individual**. Cada integrante contribuiu com sua própria avaliação crítica e relatos de prompts/experimentos, garantindo a autoria e a perspectiva individualizada do aprendizado.

### Ferramentas Empregadas
* **Ferramenta (versão)** Descrever como foi utilizada brevemente.
* **Ferramenta (versão)** Descrever como foi utilizada brevemente.

---

## 3. Experimento com IA Generativa nas Modelagens (opcional)

Como parte da avaliação das versões finais da entrega, a subequipe realizou um **experimento de geração e validação** focado nas modelagens da Entrega 2:

### Experimento 01: Modelagem Estática (Diagrama de XXXXX)
#### Objetivo: 
Descrever o objetivo do teste com IA.
#### Resultado Obtido: 
(inserir imagem do resultado da versão gerada por IA)

<center><strong>Legenda:</strong> Inserir legenda</center>

(imagem do prompt dado)

<center><strong>Legenda:</strong> Inserir legenda</center>

#### **Análise Crítica e Intervenção Humana:** 
Explicar pontos que a IA corrigiu e o que foi acatado pela equipe ou não e por que - citar extrapolação e limites do uso da IA.

### Experimento 02: Modelagem Dinâmica (Diagrama de Colaboração)
#### Objetivo: 
Validar a capacidade de uma IA Generativa (via prompt com arquitetura de contexto) em abstrair as regras de negócio de integração (Meu SUS Digital, Gov.br e RNDS) e gerar um Diagrama de Colaboração (Comunicação) alinhado com a UML 2.0.

#### Resultado Obtido: 
![Diagrama gerado pela IA](../assets/subequipe01-modelos/modelagem-dinamica/Versão1-DiagramaColaboracao-IA.jpeg)

<center><strong>Legenda:</strong> Primeira versão do Diagrama de Colaboração gerado integralmente pela IA Gemini com base no contexto textual.</center>

#### **Análise Crítica e Intervenção Humana (Comparação com a Versão da Equipe):** 
Ao compararmos o resultado gerado pela IA (Gemini) com as versões construídas manualmente pela equipe (Versões 1.0 a 1.2), notamos os seguintes pontos:

**O que a IA (Gemini) acertou:**
* **Mapeamento de Atores e Instâncias:** A IA instanciou perfeitamente todos os papéis (ex: `c: Cidadão`, `app: AppMeuSUS`, `auth: AuthService`) exigidos pelo contexto.
* **Ordem Numérica:** Aplicou corretamente a numeração decimal aninhada (ex: `1.1`, `1.1.1`, `1.2`) para denotar as chamadas síncronas e delegadas entre o hub (App) e os serviços externos.
* **Uso de Guardas:** Empregou corretamente as condições `[tokensValidos]` antes de prosseguir com chamadas de rede e persistência.

**O que a IA errou (Limites e Correções Humanas Necessárias):**
* **Sintaxe Visual da UML 2.0:** O Gemini modelou os enlaces de comunicação como se fossem setas direcionais longas ligando as caixas. Na especificação formal da UML para diagramas de comunicação, o enlace (link) é uma linha contínua, e a *seta de mensagem* é um vetor curto desenhado paralelo à linha, próximo ao rótulo textual. O modelo da equipe (v1.1 e v1.2) respeita melhor essa anatomia.
* **Falta de Caminhos de Exceção:** A IA incluiu guardas validando o estado feliz, mas foi incapaz de modelar autonomamente o que acontece no cenário de falha (ex: quando o token é inválido). A intervenção humana na Versão 1.2 da equipe foi justamente adicionar os retornos alternativos (ex: `negarAcesso()`), demonstrando resiliência arquitetural.
* **Conclusão:** O uso da IA Generativa como o Gemini é excepcional para criar um esboço rápido (*brainstorming* estrutural), mas a formatação canônica da UML e as regras de tratamento de erros devem ser guiadas pelo refinamento crítico da equipe de arquitetura.

---

## 4. Análise Crítica e Lições Aprendidas

Abaixo estão consolidados os aspectos avaliados durante a experimentação de IA Generativa na construção e validação dos artefatos de modelagem:

* **Cobertura Conceitual:** O Gemini conseguiu cobrir bem todos os atores e serviços envolvidos no ecossistema (App, Cidadão, RNDS, Gov.br), refletindo fielmente os objetos fornecidos no prompt.
* **Legibilidade e Organização:** O diagrama gerado distribuiu bem as instâncias ao redor do AppMeuSUS, facilitando a leitura inicial das trocas de mensagens na arquitetura.
* **Aderência à Técnica UML:** Baixa aderência visual à UML 2.0. Os enlaces de comunicação foram desenhados incorretamente como setas direcionais longas. Por outro lado, o emprego da numeração decimal aninhada das mensagens e expressões de guarda foi satisfatório.
* **Influência do Prompting:** Foi essencial fornecer o escopo arquitetural rigoroso previamente. A precisão na identificação dos sistemas externos só ocorreu porque o prompt já declarava o papel de "Facade" da plataforma.
* **Editabilidade dos Artefatos:** O fato de a IA entregar o código em PlantUML facilitou testes rápidos, porém a limitação da própria engine do PlantUML em renderizar Diagramas de Colaboração precisos frustrou refinamentos mais finos por código.
* **Confiabilidade e Validação:** O fluxo principal ("caminho feliz") mostrou-se confiável, mas as omissões dos tratamentos de exceção (ex: falha de token) exigiram que a equipe expandisse as regras de negócio de forma manual.
* **Limites do Experimento:** O teste confirmou que a IA é muito útil para *brainstorming* e rascunho de estruturas relacionais, mas não substitui a modelagem criteriosa de exceções, resiliência e rigor formal exigidos pela UML.

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

* **Uso da IA Generativa (Senso Crítico):** Usar a Inteligência Artificial ajudou bastante no começo para montar a base dos nossos diagramas estáticos e dinâmicos. Mas ficou claro que a gente precisa ficar de olho o tempo todo, porque a IA às vezes cria umas relações que não têm nada a ver com as regras de negócio do projeto, ou inventa fluxos meio sem sentido se o prompt não estiver muito bem explicado. A revisão manual e o ajuste do que ela gerou foram essenciais.

* **Lições Aprendidas:**
  A principal lição é que a IA não faz o trabalho de modelagem sozinha, ela só dá um empurrão. Percebi que o melhor jeito é ir fazendo aos poucos, tipo gerar uma parte do modelo, validar com o pessoal da equipe, melhorar o prompt e depois acertar os detalhes na mão nas ferramentas. Isso salva tempo e evita que a gente aceite coisas erradas ou alucinações. O resultado final depende muito de como a gente escreve o prompt no começo.
---

### João Leles
* **GitHub:** [@joaoleless](https://github.com/joaoleless)

* **Uso da IA Generativa (Senso Crítico):** Lorem ipsum dolor sit amet, consectetur adipiscing elit...

* **Lições Aprendidas:**
  Lorem ipsum dolor sit amet, consectetur adipiscing elit...

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
| [Giovani Coelho](https://github.com/Gotc2607) | Relato do uso de IA Generativa e lições aprendidas | 17/09/2026 | [54d3bd9](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/54d3bd9db024ebb55333559599d4d9c8306e13ce) |
