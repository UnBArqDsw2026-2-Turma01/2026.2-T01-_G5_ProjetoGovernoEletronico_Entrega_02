# Modelagem Estatica

---

## Versão Final

![Versao final da Modelagem Estatica](../caminho/para/imagem.png)

<center><strong>Legenda:</strong> Legenda para imagem</center>

---

## Participantes

| Nome do Membro                                               |
| :----------------------------------------------------------- |
| [Davi Ursulino de Oliveira](https://github.com/DaviUrsulino) |
| [Gabriel Mota Oliveira](https://github.com/Gabro-MO)         |
| [Yasmim de Souza Santos](https://github.com/eii-yahs)        |

---

---

## Desenvolvimento

### Versão 1

![Imagem Versao 1](../assets/subequipe03-modelagem/Estatica/ClasseV1_MeuSUS.png)

<center><strong>Legenda:</strong> Diagrama de Classes (Versão 1) do domínio "Meu SUS Digital", elaborado por Davi Ursulino de Oliveira.</center>

**Link Editável:** [Abrir e editar no draw.io](https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&dark=auto#R%3Cmxfile%3E%3Cdiagram%20name%3D%22ClasseV1_MeuSUS%22%20id%3D%22classe-v1-davi%22%3E7Vpdc9o6EP01zLQPmQGbkOQxQJo%2B9M50hnT6LOy10URIjCQD6a%2B%2FK1sGGTulpbJ7Gd88EGu1srXnrI714UE4W%2B%2BfJdms%2FhExsEEwjPeDcD4IglE4vsd%2FxvJWWO4ewsKQShpbp6NhQX%2BANQ6tNaMxqIqjFoJpuqkaI8E5RLpiI1KKXdUtEaz61A1JoWZYRITVrd9prFfWOh4OjxWfgaYr%2B%2BiHsmJNSmdrUCsSi51jCp8G4UwKoYur9X4GzIBX4lK0%2B%2FRO7aFjErj%2BlQaZyoik4kZTjcHVGtv7Kf1Whi5FxmMwrYeDcLpbUQ2LDYlM7Q7JRttKrxmWRniZUMZmggmZtw1jAvdJhHalpXgFp2YS3cMyMS0E1wv7tFFZLvgfhVgu%2BrMlLLP9%2BVYEYO0gNeydrtugn0GsQcs3dFk5tISWhN2RwwMx9i7jsS3bTC2LxGZQerjzEWS8sDj%2FHHOitVReMTfVhNGU4zWDBG84NZBQzNxHa9bC%2BCtsTnn6JfeZT46WF1M9H9e5S%2FK%2F89xZroImrm7MkNwk%2BDsIH%2FF3oSU%2BchBM8C4j03fjwBHQn3tEXNUcLmD%2F7vfZv%2FPIvtj0ivtBMDXAZRpjxT7JZ7Gdyg8fHWoLD5RslTFN5FeQ2A3jcQG3t7%2FP7cjH0Mbea5KK7fXq6cxEkJPjTVKHVeBHQRX4YOIT%2BF6KqsbG%2FIys0i3go3lCCY%2BID%2F1sGmPnqH7wSXUvFRQNNCbyxTB%2BoTheMEZDH%2BK4yRVdkSyG69XH4rW0MEG0Nee8m7QgkC74vdRInq1BihmRmohFVp9BVtQSV5JiQTiuMzmItsTyHO0%2BxNKlvZd6SXSGffxB5BwX2sqjYp5hz4tiZhy1%2FprV8lsRwBxaFczaIt2HYJbY91Mszy7CAWOVENXFsaajf2mtPvYhn2US9FI6D0vxz0KaLYsW1fOUvFsfIxjUBiKaz5evWUOf3DC8EXBmwu9FQqsE%2FC%2BkjRIZg4okdrm1aeY5pn3oZJXp3qllN2Py1tcOJWTxFZ%2F4zGwEbb2LTmfyXlHvpQhiqmXszEwxErJhqlhVSqLJ12zJMDRXLudEX%2FZa%2FIVJ5Wku%2BDgAOuRC72TSTCphT5dUdrcO93OsgymWCknJFatmGUJrb6thG9uWR%2BR7qZyN08eu%2BPNyWHPgr3dq1xFNYeBj%2Fm6JgLj24VOdLJHJyHo1fD7kcAk8fjRfW2GJCw45oETq0hZTshY8fllRXlZ9oqzUxLxcQnyPBkaWwKYkek3zHGni65QVR2KLzuE9U9DH9%2FDpWb1D4OFThRtlhuC2UM46fxIY0XRbhe2PuAj6x8U7R4MOHRuhVEa7oiBsmYIlE9ErIoEmB2YslYgNTwmypPkGvuGEwQF9mamos7QfX4h5PQIfaT%2FsIu3f3aF0OBCJ2WeHrli47UvmN22EOLCXm99d4T65DPemKP7rwDctplzkGVGKJoc3L6zb4QCLx%2B%2Bs8zrna%2FXw6V8%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E)</center>

**Tipo de UML escolhido: Diagrama de Classes** — decisão do subgrupo por ser o diagrama estático mais adequado pra representar as entidades do domínio já mapeadas na Entrega 1 (Rich Picture e BPMN dos fluxos "Rede de Saúde" e "Conteúdo").

Nesta segunda versão, modelei a entidade do AppMeuSUS para melhorar a logica de ligação entre os fluxos escolhidos e seus relacionamentos, aplicando as diferentes semânticas de relacionamento da UML, e fiz modificações visuais para melhorar a legibilidade.

#### Mapeamento das relações

- **`Usuario` ◆— `ContaGovBr`** (composição, 1..1): a autenticação via gov.br não existe fora do contexto de um usuário logado no app — é parte que não sobrevive sem o todo.
- **`Usuario` ◆— `PerfilSaude`** (composição, 1..1): o perfil de saúde é parte inseparável do usuário autenticado.
- **`UnidadeDeSaude` ◇— `Especialidade`** (agregação, 1..1..\*): uma unidade "oferece" especialidades, mas a especialidade existe independentemente da unidade (agregação, não composição).
- **`Usuario` — `UnidadeDeSaude`** (associação, "busca", 1..\*) e **`Usuario` — `Conteudo`** (associação, "consulta", 1..\*): navegação simples, sem relação de posse.
- **`Conteudo` — `Categoria`** (associação, "classifica-se em", \*..1).

Cada classe segue a estrutura de 3 compartimentos (Nome / Atributos / Operações) com visibilidade explícita (`+` público, `-` privado), conforme a notação apresentada em aula.

### Versão 2

**Autoria:** [Gabriel Mota](https://github.com/Gabro-MO)

![Imagem Versao 2](../assets/subequipe03-modelagem/Estatica/DigramaDeClasses-MeuSusDigitalV2.drawio.svg)

<center><strong>Legenda:</strong> Diagrama de Classes (Versão 2) do domínio "Meu SUS Digital".</center>

**Link Editável:** [Abrir e editar no draw.io](https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=DigramaDeClasses-MeuSusDigital.drawio.svg&dark=auto#R%3Cmxfile%3E%3Cdiagram%20name%3D%22ClasseV1_MeuSUS%22%20id%3D%22classe-v1-davi%22%3E7Vxbc9soFP41nkl3xhldfH30JW13JtnJ1u1ud9%2BIhG0SWWgAJU5%2B%2FYKEZCHJF9nIiertQyqOAMH5DufCAbfsyWr9hYBgeYdd6LUsw1237GnLssyBbfH%2FBOU1pgz7nZiwIMiVlTaEGXqDkmhIaohcSJWKDGOPoUAlOtj3ocMUGiAEv6jV5thTvxqABSwQZg7witS%2FkcuWktoxjM2LrxAtlvLTw%2BTFCiSVJYEugYtfMiT7pmVPCMYsflqtJ9ATzEv4Erf7vOVtOjACfXZIg5CGgCDcZojxyRUay%2F4oe02mTnDou1C0Nlr2%2BGWJGJwFwBFvXzjYnLZkK4%2BXTP44R543wR4mUVvbBXAwdzidMoKfYOZNzxnAh7logX02k18zk3KMv2nzcjyeZ%2BCFcjw%2F4glIOiQMrjNDl5P%2BAvEKMvLKqywzsNgShJcNhikwspdOR5alpCZFICVokfa8YTJ%2FkHzezXPAGKFaeS5eAw8tfP7swTnvcCxYgrjkjiSZYVGf8ubIX9xGdaa9DeW7eD3tFLGbR%2F%2F2YyexssqwaoslGcz535Y94n9njPBPtqwe72U94i1EBZ8zdHcNx6eFCkeg36%2BOfl8D%2Bt9Gf%2F5rPd6%2BrOfz5ePd8sV7vIXtXtwvdAt6pygXOCQOVCUJB7QgNKKvZCVhwpZ4gX3g3WyoY1WsNnVucSQEYvk9QsZeJaYgZFhd3nxo5PWnaH%2FdTYr%2FyO6iwnStlF7TkjsSWpgXHzzsPMWkz8hLOpYqHZAFZDu4ZpWDTKAHGHpWOakdsoFiYsBDwnejiNwuyHOI3YIHbisVLicL2uH9QVKypFfIdWNAIUVvciSCzwFGPovm3R23utOyJTlyIKXg4PVTylrZxLjudJXV0ra2s152fS9GuOnCUtubA7UDPJ9TLhB55NLxVdK%2B6Zq5DN3bssaxtNLQ4wvrHhL%2BkatP57Kbpg7DyUfPwAI%2FN9dbmYgZfMHPY6KN8YbKeNNWGW%2F16rJZ3eNsVgpixv15L7OlGK2NDdtitlxAl9F3TdWG4QD6igkzDjdh9nuasP6JJqz7MUxYyHi3vDdNVixvhKoasfZwZwdajFgpHOapLsnHwNPUgmPbuB50jJ6qC6tCaeeQtGuAskwfXoZL0o62bZ648twdEHKE%2Baf9OQK%2BWOSnR37dI8zoUKf%2FcpG%2BJycgF5DvAnGNjuce4GwdjmcQecsUhC5sru8Zu%2FwzMQltzM95%2FX2V913NrL9IDemHK0jwBBAG8Cws7nwpupKhAM%2BAvwiRD3FdqnI36APNoF%2BkrgQs5GN8A2QKXEzrC9Nz2KXKU3uokWRuKu9w%2BtxmqFr3yGDRPDZYTOM8H%2FuwEOdRHuKliA44wQnJcyqHsSAkOSLZX7Z21Dz5gIvACvvu9yXyk1fVI8pOBV9ZP8xq4q16CJLIyTvHIBO5T3bwutsTiljm4OSw0sx10Fd70LM5WlxuzXJyfsQTmMJa%2FZz87mZXS1pQ8v4yvZy9WT%2BuOCGBTtGrKThAOvyeI5KDXR3ZwUQILtLrSbMTXzEROZrI8REv%2FoLkD3wHAnC%2BhEVPx5KGNIAOiuLeJivVm%2Bw0tAGQD9yt3HLSET2qAPyvWUt1pgupQ%2FiQawsY9yGtI2RUkb449XmeNdnTER%2BKXVAYug0%2BczaRM6jLFg16Ktu1bKSVh1snJHEjDN8tiasEzjIyz0fM%2B3K0hdhdyfC2Dou33zWDa56awjU%2FRs6vNbFbg6EQxDV6EHYogN7hy2tP8G1Y%2Fe3szwXb2lN7%2BVVyGQYpDsVY6O0J1xxMSuI11TsBDNyHDx6fWtZFmQJ2nCt6QGRX0L86HJRUGC7ONxnLdY1IfeFbHjJbh8l0uIwtMEGgwa5KMoX6XEQzt1h0bINsOH%2BRqrM0ZjsTfrahFb%2BL03bngklHKAbleI%2B9d7DF%2By%2BkzA7McqV%2BfdYn94QrOgbO0yKSkTK88qiUnfVMC4ed9eT2iv3MPGda8dKmkSgkbVqFgGHL4YWMvASY0hBVcGtPgrtzJNzFzIQOuEtDsCbDvXW3MQM4nossBjwX4kdeLNoX3%2B%2B7wJPJcht5gZBCciLQEjCzAmDHnvsuAl3qnmRAdjxAKZpzo9SmwpDD1Znw3n5NqmmO6ygI7mAYHXjSZFG7qkXtWOptpfo22exLcoCE%2ByrdAxr7r7eIMh7Te2KkPygk%2FHnBoqZKnA9Ctrwn%2BBm5YndJNPx9xEnx0X6GsJ%2B%2BnFitkZFrTaAL6Te44N8iwAUln%2F4maqTnAkqHkGg9OkU0KPaQbPvmutC0B7FPPHXsQWw%2FMHQp4imP1yVXRoi8Pn7lCAHyufFG9FNGKuLqDyHlVSMB4kK4RitArxyMCW8hZG1bg0RerhgkKzyFY0EtVnbwivOeIW%2BZaZKI4nEbJoPq8qVlw6Tc%2FMiOD9mjLgrex76BkjCzjhi6nJkVDtg1lJnd3EkMLb%2B5UM5Mq2nM%2FO1UZpq7zEguF7LlGnd9F9iS%2B1bNwaOycNu5jPquzdJt50D7KqLDs8HT%2BeXh6eTg0XHrq5yXvabxsrLqGXTPZhQrZME%2FBjMrC2ZveDZmDhvHzOvrysJpphvstTPUbpz%2FW52bxtnE0748B7hTmwOc%2FA5fc5h5sgPcre2Km%2F3re6%2Bd3OXqbm3%2Bkd08X%2FMIK2Rr4Ccvbn4uMnb1Nz%2B6ad%2F8Bw%3D%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E)</center>

Nesta primeira versão, modelei as entidades centrais do "Meu SUS Digital" e seus relacionamentos, aplicando as diferentes semânticas de relacionamento da UML (não usando "associação" genérica pra tudo):

- **`AppMeuSUS` — `Usuario`** (associação, 1..\*): Varios usuários acessam o app do "Meu SUS digtal" por uma navegação simples sem relação de posse.
- **`Usuario` ◆— `PerfilSaude`** (composição, 1..1): o perfil de saúde é parte inseparável do usuário autenticado.
- **`ContaGovBr` <- - `AppMeuSUS`** (dependencia, 1..1): a autenticação do "Meu SUS digital" depedende do "gov.br", send uma parte que não sobrevive sem o conjunto.
- **`UnidadeDeSaude` ◇— `AppMeuSUS`** (agregação, 1..\*): O app do "Meu SUS digital" consulta as unidades de saúde nas proximidades, mas as unidades de saúde existem independentemente do app.
- **`UnidadeDeSaude` ◇— `Especialidade`** (agregação, 1..1..\*): uma unidade "oferece" especialidades, mas a especialidade existe independentemente da unidade (agregação, não composição).
- **`AppMeuSUS` <- - `Conteudo`** (dependencia, 1..\*): O app do "Meu SUS digital" exibi os conteudos salvos no banco de dados, e os conteudos dependem do app para serem exibidos.
- **`Conteudo` — `Categoria`** (associação, "classifica-se em", \*..1..\*): Cada Conteudo pode ser associado a uma ou mais Categorias, mas não possuem relação de posse entre sí.

Cada classe segue a estrutura de 3 compartimentos (Nome / Atributos / Operações) com visibilidade explícita (`+` público, `-` privado), conforme a notação apresentada em aula.

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

| Nome do Membro                                               | Contribuição                                                                        | Data       | Commit                                                                                                                                                   |
| ------------------------------------------------------------ | ----------------------------------------------------------------------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Gustavo Fornaciari](https://github.com/GUGOFO)              | Criação do Repositorio                                                              | 10/09/2026 | [efd139e](https://github.com/UnBArqDsw2026-2-Turma01/2026.2-T01-_G5_ProjetoGovernoEletronico_Entrega_02/commit/efd139e36025a5c1610fff909ac41451ab13eecd) |
| [Davi Ursulino de Oliveira](https://github.com/DaviUrsulino) | Elaboração da Versão 1 do Diagrama de Classes do domínio Meu SUS Digital            | 15/09/2026 | [A por depois]()                                                                                                                                         |
| [Gabriel Mota](https://github.com/Gabro-MO)                  | Adição da versão 2 do Diagrama Estatico (Diagrama de Classes) e correçãos dos links | 17/09/2026 | [A por depois]()                                                                                                                                         |
| [Gabriel Mota](https://github.com/Gabro-MO)                  | Correção dos link que estavam em HTML e da imagem V2 incorreta | 17/09/2026 | [A por depois]()                                                                                                                                         |
