# Arquitetura de dados

Série de módulos sobre analytics engineering, cada um com mapa interativo e artigo. Site estático, sem build, publicado com GitHub Pages a partir da branch `main`, pasta raiz.

## Estrutura

```
index.html                     hub: lista os módulos
artigo.html                    redirecionamento (link antigo)
modules/
  dbt-self-service/            módulo 1: dbt + autosserviço
    index.html                 mapa interativo
    artigo.html                artigo "Do dado bruto ao autosserviço"
```

## Adicionar um módulo

1. Crie `modules/<slug>/` com `index.html` (e `artigo.html`, se houver).
2. Na navegação do módulo, inclua `<a href="../../">Módulos</a>`.
3. Copie um bloco `<article class="card">` em `index.html` (raiz) apontando para `modules/<slug>/`.
4. Use caminhos relativos nos links, para funcionar sob `/data-architecture/`.

Autora: Erika Medeiros · Analytics Engineering
