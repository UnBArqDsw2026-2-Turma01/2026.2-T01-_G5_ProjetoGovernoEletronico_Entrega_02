# Modelagem Dinamica 

---

## Versão Final

![Versao final da Modelagem Dinamica](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

---

## Participantes 
| Nome do Membro | 
| :--- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) |
| [Ana Beatriz](https://github.com/AnnaBeatrizAraujo) |
| [Victor Leandro](https://github.com/Afrontoso) |

---

## Fundamentação Teorica

Exlpique bravemente como funciona o UML que voce escolheu

---

## Desenvolvimento

### Versão 1

![Diagrama de Atividades - Versão 1](../assets/subequipe02-modelos/modelagem-dinamica/V1.png)

<center><strong>Legenda:</strong> Figura 2 - Diagrama de Atividades de alto nível para a navegação pós-login</center>

#### Detalhamento da Versão 1
A **Versão 1 (V1)** foca na navegação de **alto nível** do portal pós-autenticação. As definições contemplam:

- **Escopo e Delimitação:** Mapeamento do acesso ao painel e ao menu lateral (`Início`, `Aplicações`, `Minha Saúde`, `Conteúdos`, `Meu perfil`, `Dúvidas frequentes`) e às seções de cartões (*Minha Saúde*, *Mini Apps* e *Conteúdo*). Detalhes internos de sub-módulos foram reservados para iterações futuras (V2+).
- **Partições de Responsabilidade (*Swimlanes*):** Organização do fluxo entre *Usuário (Cidadão)* e *Sistema (MEU SUS DIGITAL)*.
- **Tratamento de Exceções:** Mapeamento de nós de decisão para cenários como sessão expirada (redirecionando para o gov.br) e falhas de conexão/indisponibilidade de API do SUS.
- **Estrutura de Repetição:** Modelagem do ciclo de permanência no portal por meio de loop de decisão, permitindo novo fluxo de navegação ou encerramento de sessão com logout seguro.

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

Explicar qual a metodologia seguida pela equipe para fazer essa modelagem e , caso tenha alguma particularidade, explicar ela

"Seguindo a geral e --extra da subequipe--..."

---

### Embasamento teórico para criação:

1. UML-DIAGRAMS. *UML Activity Diagrams*. Disponível em: https://www.uml-diagrams.org/activity-diagrams.html. Acesso em: 15/09/2026.

---

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositorio | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) | 
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Versão 1 do documento | 16/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) | 