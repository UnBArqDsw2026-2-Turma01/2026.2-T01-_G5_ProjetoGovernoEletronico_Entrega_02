# Modelagem Estática 

---

## Versão Final

<iframe 
  width="768" 
  height="432" 
  src="https://miro.com/app/board/uXjVHmp1ME8=/?share_link_id=760710539095" 
  frameborder="0" 
  scrolling="no" 
  allow="fullscreen; clipboard-read; clipboard-write" 
  allowfullscreen>
</iframe>

<center><strong>Legenda:</strong> Diagrama de Pacotes Final (Arquitetura em Camadas e Módulos do Sistema)</center>

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

O **Diagrama de Pacotes** é um diagrama estrutural e estático da UML (Unified Modeling Language) cujo principal objetivo é organizar o sistema em subsistemas, módulos ou camadas lógicas de alto nível. Ele permite agrupar elementos de modelagem — como classes, interfaces, componentes e outros pacotes — em contêineres gerenciáveis representados graficamente como pastas de arquivos. 

Essa notação reduz a complexidade visual de projetos complexos, facilitando a visualização de dependências, acoplamentos e separação de responsabilidades (como a divisão entre camadas de apresentação, lógica de negócios, segurança e persistência), mantendo a arquitetura modular e escalável.

---

## Desenvolvimento

### Versão 1

**Autoria:** [Artur Galdino](https://github.com/ArturFGaldino)
![Imagem Versao 1](../assets/subequipe01-modelos/modelagem-estatica/modelagem-estatica-v1.0.jpg)

<center><strong>Legenda:</strong> Estruturação inicial dos pacotes principais e dependências arquiteturais do sistema</center>

Nesta primeira e definitiva versão do artefato, realizamos a modelagem estática de pacotes traduzindo os requisitos funcionais, fluxos de autenticação (OAuth 2.0 / Gov.br) e restrições não funcionais (como LGPD e segurança) mapeados nos relatórios anteriores (*Rich Picture*, *NFR Framework* e *BPMN*). 

O sistema foi estruturado em quatro grandes pacotes e seus respectivos subpacotes internos para encapsular as responsabilidades lógicas:
* **`Presentation`**: Contém os subpacotes `Screens` (responsável pelas interfaces gráficas e telas de dashboard de saúde) e `NavigationController` (gerenciador de rotas e fluxo de navegação, incluindo o acesso sem login/visitante).
* **`Authentication`**: Agrupa os módulos de segurança de borda e federação de identidade, contendo `OAuthClient` (gerenciamento do fluxo de login federado), `PKCEHandler` (tratamento criptográfico de códigos de verificação via SHA-256) e `TokenValidator` (validação de assinaturas e tokens via JWKS e RS256).
* **`SecurityAndCompliance`**: Focado na conformidade regulatória e proteção de dados, englobando `SecureStorage` (cofre criptografado local para sessões), `ConsentManager` (gestão explícita de termos de uso e privacidade exigidos pela LGPD) e `AuditLogger` (geração de logs imutáveis com hash SHA-256).
* **`HealthIntegration`**: Responsável pela interoperabilidade e comunicação com o ecossistema de saúde, contendo `FHIRClient` (consumo de dados clínicos no padrão internacional HL7 FHIR) e `NetworkGateway` (camada de transporte protegida por mTLS).

As dependências entre os pacotes foram estabelecidas por meio de setas pontilhadas com o estereótipo `<<use>>`, refletindo diretamente o sentido de consumo de serviços: a camada de apresentação consome o módulo de autenticação, enquanto os módulos funcionais dependem das diretrizes de segurança, auditoria e conformidade legal providas pelo pacote de segurança.

### Versão 2

**Autoria:** [Giovani Coelho](https://github.com/Gotc2607)
![Imagem Versao 2](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

Oque voce modificou e porque modificou

### Versão 3

**Autoria:** [João Leles](https://github.com/joaoleless)
![Imagem Versao 3](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

Oque voce modificou e porque modificou

### Versão 4

**Autoria:** [Nicole Jovita](https://github.com/nicolejovita)
![Imagem Versao 4](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

Oque voce modificou e porque modificou

---

## Metodologia

A equipe seguiu uma abordagem colaborativa e incremental para a construção do artefato, alinhando as decisões arquiteturais diretamente aos modelos produzidos nas entregas anteriores (especialmente o mapeamento de segurança do BPMN e os Requisitos Não Funcionais do NFR Framework). 

Seguindo a diretriz geral da disciplina e as especificidades da nossa subequipe, o processo consistiu na extração dos principais domínios lógicos identificados na engenharia reversa do aplicativo *Meu SUS Digital*, convertendo fluxos comportamentais e restrições de cibersegurança em pacotes modulares de alto acoplamento interno e baixo acoplamento externo.

---

### Embasamento teórico para criação:

1. SERRANO, Milene. [Arquitetura e Desenho de Software - Aula Modelagem UML Estática](https://drive.google.com/file/d/17TPUNv5Pllzhx23HIpZ0aJnU9hAJ9Ln9/view). Brasília: UnB Gama, 2026. 1 arquivo PDF.
2. UML Diagrams. UML Package Diagrams Overview. Disponível em: https://www.uml-diagrams.org/package-diagrams-overview.html. Acesso em: 15 set. 2026.
3. UML Diagrams. Unified Modeling Language (UML) Diagrams. Disponível em: https://www.uml-diagrams.org/. Acesso em: 15 set. 2026.
4. KDESDK. UML Basics. Disponível em: https://docs.kde.org/trunk4/pt_BR/kdesdk/umbrello/uml-basics.html. Acesso em: 15 set. 2026.

---

## Histórico de Versionamento

| Nome do Membro  | Contribuição   | Data  | Commit |
| ---- | ------ | ----- | ---- |
| [Gustavo Fornaciari](https://github.com/GUGOFO) | Criação do Repositorio | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) | 
| [Artur Galdino](https://github.com/ArturFGaldino) | Estruturação inicial do artefato de modelagem estática de pacotes e definição dos módulos | 15/09/2026 | [74546bc](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/74546bc3f8c51bdd738df156dbc65de0edcfceac) |