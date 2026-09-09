# Demonstração da fórmula de Bhaskara em MathML

Trabalho da disciplina de Desenvolvimento Web: página em **HTML5 puro** que apresenta a
dedução completa da fórmula resolutiva da equação do segundo grau, com toda a notação
matemática marcada em **MathML** nativo — sem JavaScript, sem imagens e sem bibliotecas
externas (nada de MathJax ou KaTeX).

## Conteúdo da página

1. **O problema** — a forma geral `ax² + bx + c = 0` e a condição `a ≠ 0`.
2. **A dedução** — sete passos de completamento de quadrados, cada um com sua justificativa.
3. **O discriminante** — definição de Δ e a tabela de natureza das raízes.
4. **Verificação** — a substituição que confirma que as raízes anulam a equação.
5. **Exemplo resolvido** — `2x² − 7x + 3 = 0`.
6. **Relações de Girard** — soma e produto das raízes como consequência da fórmula.

## Arquivos

| Arquivo | Papel |
| --- | --- |
| `index.html` | Estrutura semântica e todo o MathML |
| `estilo.css` | Tipografia, layout, tema claro/escuro e estilo de impressão |
| `ROTEIRO.md` | Roteiro cronometrado da apresentação em vídeo, com a divisão da dupla |
| `slides.html` | Deck de 22 slides em 16:9 (HTML paginado, também com MathML nativo), com identidade visual temática do Grêmio |
| `slides.pdf` | O mesmo deck exportado em PDF, para projetar durante a apresentação |

## Como visualizar

Abra `index.html` em qualquer navegador moderno. O MathML é renderizado nativamente
por Firefox, Safari e Chrome/Edge (a partir da versão 109).

Para servir localmente:

```bash
python -m http.server 8000
# depois acesse http://localhost:8000
```

## Elementos MathML utilizados

`<math>`, `<mrow>`, `<mi>`, `<mn>`, `<mo>`, `<mfrac>`, `<msup>`, `<msub>`, `<msqrt>`,
`<mtext>` e `<mspace>` — além do atributo `display="block"` para as equações destacadas.
