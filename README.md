# Pregações — Dariel Sobzak

Site estático (um `index.html`, sem dependências) publicado no GitHub Pages:
https://darielmss.github.io/pregacoes/

## Estrutura

```
pregacoes/
├── index.html   # página (a lista de pregações fica dentro dela)
├── README.md    # este passo a passo
└── pdf/         # um PDF por pregação
```

## Como adicionar uma nova pregação

### 1. Copie o PDF para a pasta `pdf/`

Use a versão `_A4-corte` do PDF e renomeie ao copiar:

- tudo minúsculo, palavras separadas por hífen
- sem espaço, sem acento, sem `ç` e sem pontuação
- exemplo: `Fé que Move Montanhas_A4-corte.pdf` → `fe-que-move-montanhas.pdf`

### 2. Cadastre a pregação no `index.html`

Abra o `index.html` em um editor de texto (Bloco de Notas ou VS Code) e procure `const pregacoes = [`.
Logo abaixo dessa linha, cole um bloco novo **com a vírgula no final**:

```js
    {
        titulo: "Fé que Move Montanhas",
        referencia: "Mateus 17:20 · Sermão Textual",
        data: "2026-11-02",
        resumo: "Uma frase com o tema da pregação.",
        arquivo: "pdf/fe-que-move-montanhas.pdf"
    },
```

| Campo | O que colocar |
|---|---|
| `titulo` | Título como está na capa do PDF |
| `referencia` | Texto bíblico + tipo de sermão (copie da capa) |
| `data` | `AAAA-MM-DD`. A lista ordena sozinha, da mais nova para a mais antiga |
| `resumo` | O "Tema" da capa serve bem |
| `arquivo` | `pdf/` + o nome que você deu no passo 1 |

Cuidados:
- mantenha as aspas `"` em volta de cada valor
- se o texto tiver aspas, use aspas simples dentro: `"O chamado de 'levanta-te'"`
- o nome em `arquivo` tem que ser **idêntico** ao do PDF, senão o link quebra

### 3. Confira no computador

Dê dois cliques no `index.html`. O card novo deve aparecer, e **Ler pregação** deve abrir o PDF.
Se a página ficar sem nenhum card, faltou uma vírgula ou uma aspa no bloco que você colou.

### 4. Publique

No terminal, dentro da pasta `pregacoes`:

```bash
git add .
git commit -m "Adiciona pregação: Fé que Move Montanhas"
git push
```

Em 1 a 2 minutos o site está atualizado. Se não aparecer, recarregue com `Ctrl+F5`.

> Sem terminal: no GitHub, abra o repositório `pregacoes`, use **Add file → Upload files** para enviar o PDF dentro de `pdf/`, e edite o `index.html` pelo lápis ✏️ direto no site.
