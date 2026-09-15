# Modelagem Estatica 

---

## Versão Final

![Versao final da Modelagem Estatica](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

---

## Participantes 
| Nome do Membro | 
| :--- |
| [Davi Ursulino de Oliveira](https://github.com/DaviUrsulino) |
| [Gabriel Mota Oliveira](https://github.com/Gabro-MO) |
| [Yasmim de Souza Santos](https://github.com/eii-yahs) |

---

---

## Desenvolvimento

### Versão 1

![Imagem Versao 1](../assets/subequipe03-modelagem/Estatica/ClasseV1_MeuSUS.png)

<center><strong>Legenda:</strong> Diagrama de Classes (Versão 1) do domínio "Meu SUS Digital", elaborado por Davi Ursulino de Oliveira.</center>

<center><strong>Link Editável:</strong> [Abrir e editar no draw.io](https://app.diagrams.net/?url=https://raw.githubusercontent.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/docs/subequipe03-uml-estatica-v1/docs/2-Modelagem/Relatórios/2.1.3.SubEquipe_03/ClasseV1_MeuSUS.drawio)</center>

**Tipo de UML escolhido: Diagrama de Classes** — decisão do subgrupo por ser o diagrama estático mais adequado pra representar as entidades do domínio já mapeadas na Entrega 1 (Rich Picture e BPMN dos fluxos "Rede de Saúde" e "Conteúdo").

Nesta primeira versão, modelei as entidades centrais do "Meu SUS Digital" e seus relacionamentos, aplicando as diferentes semânticas de relacionamento da UML (não usando "associação" genérica pra tudo):

- **`Usuario` ◆— `ContaGovBr`** (composição, 1..1): a autenticação via gov.br não existe fora do contexto de um usuário logado no app — é parte que não sobrevive sem o todo.
- **`Usuario` ◆— `PerfilSaude`** (composição, 1..1): o perfil de saúde é parte inseparável do usuário autenticado.
- **`UnidadeDeSaude` ◇— `Especialidade`** (agregação, 1..1..\*): uma unidade "oferece" especialidades, mas a especialidade existe independentemente da unidade (agregação, não composição).
- **`Usuario` — `UnidadeDeSaude`** (associação, "busca", 1..\*) e **`Usuario` — `Conteudo`** (associação, "consulta", 1..\*): navegação simples, sem relação de posse.
- **`Conteudo` — `Categoria`** (associação, "classifica-se em", \*..1).

Cada classe segue a estrutura de 3 compartimentos (Nome / Atributos / Operações) com visibilidade explícita (`+` público, `-` privado), conforme a notação apresentada em aula.

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

O subgrupo trabalha em rotação: cada integrante fica responsável por uma versão (V1, V2 e V3) do diagrama, sempre refinando a versão anterior do colega. Nesta frente (Modelagem Estática), a rotação é: **Versão 1 — Davi** (elaboração inicial) → **Versão 2 — Gabriel** (refinamento) → **Versão 3 — Yasmim** (fechamento). O tipo de UML (Diagrama de Classes) foi definido em conjunto pelo subgrupo antes do início da V1, pra manter consistência entre as três versões.

---

### Embasamento teórico para criação:

1. A notação segue o Diagrama de Classes da UML (Unified Modeling Language), conforme material da disciplina (Profa. Milene Serrano) e a documentação de referência [uml-diagrams.org](https://www.uml-diagrams.org/class-diagrams-overview.html): cada classe é representada em 3 compartimentos (Nome, Atributos, Operações), com visibilidade `+` (público), `-` (privado) e `#` (protegido).
2. Os relacionamentos seguem semânticas distintas, e não uma associação genérica: **associação** (uso simples, verbo no meio da linha), **agregação** (losango vazado, relação "tem", parte sobrevive sem o todo) e **composição** (losango preenchido, relação "contém"/"é composto de", parte não existe sem o todo), conforme Booch, Rumbaugh & Jacobson (criadores da UML).

---

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositorio | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) | 
| [Davi Ursulino de Oliveira](https://github.com/DaviUrsulino) | Elaboração da Versão 1 do Diagrama de Classes do domínio Meu SUS Digital | 15/09/2026 | |