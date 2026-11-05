# Guia de arquitetura de soluções para analytics engineering

Guia vivo, escrito por **Erika Medeiros**, sobre como projetar soluções de dados em que analytics engineering é o centro: do dado bruto ao consumo por pessoas, sistemas e agentes de IA, todos sobre a mesma definição de negócio.

Criei este guia para **compartilhar a minha experiência** com arquitetura de soluções em analytics engineering. Ele reflete o que vivi na prática, as decisões que tomei e o que aprendi com elas. Não é manual definitivo nem receita única: está em evolução, e cada módulo é revisado conforme eu aprendo mais. Se algo aqui fizer você pensar diferente, a conversa é bem-vinda.

Publicado em https://medeiros-erika.github.io/data-architecture/

## Posicionamento

Arquitetura de soluções, vista a partir de analytics engineering. O foco não é a ferramenta, e sim as decisões de desenho que fazem uma plataforma de dados escalar sem virar gargalo:

- **Uma definição de negócio, vários consumidores.** Métricas e regras vivem em um só lugar, e analistas, cientistas, sistemas e agentes de IA se servem dele.
- **Autosserviço com governança.** Quem consome não depende de quem constrói, e quem constrói não perde o controle do que é publicado.
- **Dado tratado como produto.** Dono, contrato, qualidade e prontidão explícitos, não apenas tabelas.
- **Decisão justificada.** Cada módulo explica o raciocínio e os trade-offs, não só o resultado.

## Formato de cada módulo

Todo módulo segue o mesmo desenho, para o guia ficar coerente conforme cresce:

1. **Mapa interativo** (`index.html`): visão de referência com uma demonstração por bloco.
2. **Artigo** (`artigo.html`): o raciocínio completo, com exemplos e trade-offs.

## Módulos

| Módulo | Tema | Situação |
|---|---|---|
| [`dbt-self-service`](modules/dbt-self-service/) | Organizar um projeto dbt para autosserviço: camadas, camada semântica, data products e consumo | Publicado |

### Candidatos para os próximos módulos

Lista de trabalho, sem ordem nem prazo. Edite livremente.

- Observabilidade e resposta a incidentes de dados
- Contratos de dados entre produtores e consumidores
- Estratégia de materialização e custo
- Dado para agentes de IA: contexto, permissões e confiabilidade
- Governança e papéis em times de dados

## Estrutura do repositório

```
index.html                     hub: lista os módulos
artigo.html                    redirecionamento (link antigo)
assets/                        imagens compartilhadas (foto da bio)
modules/
  <slug>/                      um diretório por módulo
    index.html                 mapa interativo
    artigo.html                artigo
```

Site estático, sem build. Publicado com GitHub Pages a partir da branch `main`, pasta raiz.

## Como evoluir o guia

**Novo módulo**

1. Crie `modules/<slug>/` com `index.html` e, se houver, `artigo.html`.
2. Na navegação do módulo, inclua `<a href="../../">Módulos</a>`.
3. Copie um bloco `<article class="card">` no `index.html` da raiz, apontando para `modules/<slug>/`.
4. Atualize a tabela de módulos neste README.
5. Use caminhos relativos, para funcionar sob `/data-architecture/`.

**Revisar um módulo existente**

- Mantenha o mesmo endereço: links compartilhados não podem quebrar.
- Se mudar o endereço de uma página, deixe um redirecionamento no lugar, como o `artigo.html` da raiz.
- Registre mudanças relevantes de conteúdo na mensagem de commit, para o histórico do git servir de changelog.

**Convenções**

- Idioma: português do Brasil.
- Nomes de modelos, métricas e números nas demos são exemplos e devem ser identificados como tais.
- Visual claro, com fundo branco, tipografia Geist e paleta inspirada na Warren (neutros quentes `#333131`, `#F7F3F2`, `#E4E0DD` e acentos `#356D3E`, `#34639C`, `#7E527A`, `#94632B`, `#B23B51`). Cada página funciona em tela de celular.

## Autoria

Erika Medeiros · Analytics Engineering
