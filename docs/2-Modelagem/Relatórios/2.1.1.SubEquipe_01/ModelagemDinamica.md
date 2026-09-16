# Modelagem Dinâmica | Diagrama de Colaboração (Comunicação)

---

## Versão Final

<iframe 
  width="768" 
  height="432" 
  src="https://miro.com/app/board/uXjVHmpqMHQ=/?share_link_id=17243576178" 
  frameborder="0" 
  scrolling="no" 
  allow="fullscreen; clipboard-read; clipboard-write" 
  allowfullscreen>
</iframe>

<center><strong>Legenda:</strong> Diagrama de Colaboração Final (Fluxo Seguro de Autenticação e Consentimento no Meu SUS Digital)</center>

---

## Participantes 
| Nome do Membro | 
| :--- |
| [Artur Galdino](https://github.com/ArturFGaldino) |
| [Giovani Coelho](https://github.com/Gotc2607) |
| [João Leles](https://github.com/joaoleless) |
| [Nicole Jovita](https://github.com/nicolejovita) |

---

## Fundamentação Teórica

### O que é o Diagrama de Colaborações 

O **Diagrama de Colaboração** (denominado **Diagrama de Comunicação** a partir da especificação UML 2.0) é um artefato da **modelagem dinâmica** da UML (*Unified Modeling Language*). Ele é utilizado para demonstrar a interação comportamental entre objetos ou partes do sistema por meio de mensagens sequenciais organizadas em torno de uma estrutura gráfica de enlaces.

Conforme apresentado nas diretrizes teóricas da Profa. Milene Serrano, os diagramas dinâmicos da UML buscam revelar a dimensão comportamental da solução computacional. Diferentemente do Diagrama de Sequência — que prioriza a ordenação estritamente temporal disposta ao longo de linhas de vida verticais —, o Diagrama de Colaboração destaca a **organização e o relacionamento estrutural entre os objetos** que participam da interação, dando ênfase no caminho pelo qual as mensagens trafegam durante determinado cenário de uso.

A fundamentação conceitual do Diagrama de Colaboração na UML resgata as contribuições históricas de **Grady Booch**, um dos criadores da notação ao lado de James Rumbaugh (OMT) e Ivar Jacobson (OOSE).

### Principais Elementos e Regras da Notação UML

* **Atores e Objetos (*Lifelines*):** Representam os papéis e as instâncias de classes envolvidas no fluxo (ex.: `c: Cidadao`, `app: AppMeuSUS`).
* **Enlaces de Comunicação (*Links*):** Linhas sólidas ligando os objetos para indicar a existência de um canal de comunicação estrutural por onde as mensagens transitam.
* **Setas de Mensagem e Sentido de Disparo:** Setas paralelas aos enlaces que indicam a direção da chamada de método.
* **Numeração de Sequência Cronológica:** Identificadores numéricos que estabelecem a ordem temporal do fluxo (ex.: `1`, `1.1`, `2.2.1`). A notação decimal aninhada expressa sub-operações ou chamadas derivadas disparadas a partir de um método pai.
* **Expressões de Guarda (`[condição]`):** Regras condicionais entre colchetes que delimitam o disparo da mensagem mediante validação de contexto (ex.: `[tokensValidos]`, `[termoPendente]`).
* **Iteração (`*`):** Símbolo de asterisco associado à sequência para indicar execuções repetitivas em laço.
* **Moldura e Cabeçalho (*Diagram Frame* e *Frame Heading*):** Delimitação retangular do diagrama com um pentágono no canto superior esquerdo identificando a notação (`communication` ou `sd`) e o nome do caso de uso modelado.

---

## Desenvolvimento

### Versão 1.0

**Autoria:** [Nicole Jovita](https://github.com/nicolejovita)

![Imagem Versão 1](../assets/subequipe01-modelos/modelagem-dinamica/modelagem-dinamica-v1.0.jpg)

<center><strong>Legenda:</strong> Estruturação inicial da rede de colaboração e fluxo sequencial de mensagens</center>

Nesta primeira versão do artefato dinâmico, realizou-se o mapeamento primário das interações entre as instâncias envolvidas na jornada de autenticação federada (Gov.br), gestão de consentimento (LGPD) e consumo de dados clínicos (HL7 FHIR / RNDS), integrando os requisitos levantados na Rich Picture, no NFR SIG e no BPMN.

#### Convenções Visuais e Legenda do Modelo
Para orientar a interpretação do diagrama, a modelagem foi sustentada pelas seguintes regras formais:
* **Objetos / Instâncias (`:Classe`):** Representam os componentes e instâncias operacionais do ecossistema.
* **Enlaces de Comunicação (Linhas Contínuas):** Explicitam os caminhos de comunicação diretamente estabelecidos entre dois objetos.
* **Setas de Disparo:** Apontam o sentido da chamada de método entre os objetos.
* **Sequência Numérica Aninhada (`1`, `1.1`, `2.2.1`):** Define a ordem cronológica exata de execução. A numeração decimal ramificada mapeia a hierarquia de métodos chamados durante o tempo de ativação de uma operação superior.
* **Expressões de Guarda (`[condição]`):** Condicionantes de negócio aplicadas ao envio das mensagens.

#### Mapeamento de Objetos e Responsabilidades

| Objeto / Papel | Tipo / Camada | Responsabilidade no Fluxo |
| :--- | :--- | :--- |
| **`:Cidadao`** | Ator Externo | Cidadão que interage com a interface do aplicativo. |
| **`:AppMeuSUS`** | Frontend / Cliente | Cliente móvel que coordena a navegação e a renderização da interface. |
| **`:AuthService`** | Controller / Segurança | Controlador responsável pela geração do desafio PKCE e validação dos tokens JWT (RS256/JWKS). |
| **`:GovBrProvider`** | Serviço Externo | Provedor federado de identidade responsável pela autenticação e emissão do *Auth Code*. |
| **`:ConsentManager`** | Serviço / Negócio | Gerenciador que valida e coleta o aceite explícito dos Termos de Uso e Política de Privacidade (LGPD). |
| **`:AuditLogger`** | Repositório / Segurança | Serviço de auditoria que registra logs imutáveis acompanhados de Hash SHA-256. |
| **`:SecureStorage`** | Armazenamento Local | Cofre criptografado local (*KeyStore/Keychain*) para persistência dos tokens de acesso. |
| **`:RNDSClient`** | Cliente de API / Integração | Módulo de comunicação com a Rede Nacional de Dados em Saúde via mTLS/HL7 FHIR. |

---

### Versão 1.1

**Autoria:** [João Leles](https://github.com/joaoleless)

![Imagem Versão 2](../assets/subequipe01-modelos/modelagem-dinamica/modelagem-dinamica-v2.0.jpg) 

<center><strong>Legenda:</strong> Inserir legenda </center>

Explicar o que foi feito.

---

### Versão 1.2

**Autoria:** [Giovani Coelho](https://github.com/Gotc2607)

![Imagem Versão 3](../assets/subequipe01-modelos/modelagem-dinamica/modelagem-dinamica-v3.0.jpg)

<center><strong>Legenda:</strong> Inserir legenda </center>

Explicar o que foi feito.

---

### Versão 1.3

**Autoria:** [Artur Galdino](https://github.com/ArturFGaldino)

![Imagem Versão 4](../assets/subequipe01-modelos/modelagem-dinamica/modelagem-dinamica-v4.0.jpg)

<center><strong>Legenda:</strong> Inserir legenda </center>

Explicar o que foi feito.

---

## Metodologia

INSERIR METODOLOGIA NO FINAL

---

### Embasamento teórico para criação:

1. SERRANO, Milene. [Arquitetura e Desenho de Software - Aula Modelagem UML Dinâmica](https://drive.google.com/file/d/1wLDrtIJleri9zf0g5VANhwqzCJ7WTpOE/view). Brasília: UnB Gama, 2026. 1 arquivo PDF.
2. SERRANO, Milene. [Arquitetura e Desenho de Software - Aula Modelagem UML Estática](https://drive.google.com/file/d/17TPUNv5Pllzhx23HIpZ0aJnU9hAJ9Ln9/view). Brasília: UnB Gama, 2026. 1 arquivo PDF.
3. UML Diagrams. Communication Diagrams Overview. Disponível em: https://www.uml-diagrams.org/communication-diagrams.html. Acesso em: 15 set. 2026.
4. UML Diagrams. Unified Modeling Language (UML) Diagrams. Disponível em: https://www.uml-diagrams.org/. Acesso em: 15 set. 2026.
5. KDESDK. UML Basics. Disponível em: https://docs.kde.org/trunk4/pt_BR/kdesdk/umbrello/uml-basics.html. Acesso em: 15 set. 2026.

---

## Histórico de Versionamento

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositorio | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) |
| [Nicole Jovita](https://github.com/nicolejovita) | Fundamentação teórica, estruturação do documento, legenda e elaboração da Versão 1.0 | 15/09/2026 | |