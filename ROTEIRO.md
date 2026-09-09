# Roteiro da apresentação em vídeo

**Trabalho:** demonstração da fórmula de Bhaskara em HTML puro com MathML
**Dupla:** Gabriel e Pedro Henrique Barcellos
**Duração alvo:** ~14 min (o teto é 15; deixe margem)

A divisão alterna em blocos para que os dois falem de MathML — é ali que está o foco
da avaliação, não na matemática em si.

| # | Tempo | Quem | Bloco |
| --- | --- | --- | --- |
| 1 | 0:00–1:00 | Gabriel | Abertura e o problema |
| 2 | 1:00–3:30 | Pedro Henrique Barcellos | O que é MathML e por que ele existe |
| 3 | 3:30–6:00 | Gabriel | Anatomia da marcação: os elementos |
| 4 | 6:00–9:00 | Pedro Henrique Barcellos | A dedução na tela, passo a passo |
| 5 | 9:00–11:00 | Gabriel | Estrutura, CSS e responsividade do MathML |
| 6 | 11:00–13:00 | Pedro Henrique Barcellos | Acessibilidade e suporte dos navegadores |
| 7 | 13:00–14:00 | Ambos | Fechamento |

---

## 1. Abertura — Gabriel (1 min)

Apresenta a dupla e o objetivo: uma página em HTML puro que demonstra a fórmula de
Bhaskara usando o módulo MathML. Mostre a capa da página com a fórmula grande e diga a
regra que vocês se impuseram: **nenhuma imagem, nenhum JavaScript, nenhuma biblioteca**
— nem MathJax, nem KaTeX. Tudo é markup nativo do navegador.

## 2. O que é MathML — Pedro Henrique Barcellos (2,5 min)

O bloco conceitual. Cubra:

- MathML é um **padrão do W3C** para descrever notação matemática em XML/HTML, existe
  desde 1998 e hoje faz parte do HTML5 — o `<math>` é um elemento nativo, como `<table>`
  ou `<svg>`.
- Duas vertentes: **Presentation MathML** (como a fórmula *aparece*) e **Content MathML**
  (o que ela *significa*, semanticamente). O trabalho usa Presentation, que é o suportado
  pelos navegadores.
- **MathML Core** é o subconjunto enxuto que os navegadores implementam hoje.
- O contraste que justifica tudo: as três alternativas para pôr matemática na web são
  **imagem** (não escala, não copia, não é lida por leitor de tela), **biblioteca JS**
  (peso, dependência externa, depende de JS ativo) e **MathML** (texto real, no DOM,
  estilizável por CSS, acessível, imprimível).

## 3. Anatomia da marcação — Gabriel (2,5 min)

Abra o `index.html` no editor e percorra os elementos, um a um, comparando com o que
aparece na tela. É o bloco mais técnico — vá devagar:

- `<math>` — o contêiner; `display="block"` faz a equação centralizada e destacada,
  `inline` (padrão) a coloca no meio do texto.
- `<mrow>` — agrupa; é o "parênteses invisível" que mantém a expressão coesa nas quebras.
- `<mi>` identificador (variável, em itálico automático), `<mn>` número, `<mo>` operador
  — a diferença de espaçamento entre eles é o navegador aplicando regras tipográficas
  matemáticas sozinho.
- `<mfrac>` fração — **dois filhos**: numerador e denominador.
- `<msup>` / `<msub>` — base + expoente, base + índice.
- `<msqrt>` — raiz com o radical desenhado do tamanho certo.
- `<mtext>` e `<mspace width="2em">`.

Mostre um caso concreto — a própria fórmula final — e leia o markup em voz alta apontando
o aninhamento `mfrac > mrow > msqrt`. Vale citar também o uso de **entidades numéricas**
(`&#8722;` para o menos matemático, `&#177;` para o ±, `&#916;` para o Δ) em vez dos
caracteres soltos.

## 4. A dedução na tela — Pedro Henrique Barcellos (3 min)

Rola a página pelos 7 passos, narrando a matemática **em ritmo rápido** — multiplicar por
4a, isolar, somar b², fatorar `(2ax+b)²`, extrair raiz com o ±, isolar x. O ponto de
amarração, sempre: cada passo é um bloco `<math display="block">` distinto, e a estrutura
visual (cartão numerado + justificativa) é HTML/CSS ao redor do MathML. Feche com a tabela
do discriminante e o exemplo `2x² − 7x + 3 = 0`.

## 5. Estrutura, CSS e responsividade — Gabriel (2 min)

- MathML é estilizável como qualquer elemento: `math { font-family }`, `font-size: 1.3em`
  nos blocos, tema claro/escuro por `prefers-color-scheme` — a fórmula muda de cor junto
  com a página.
- **Demonstre ao vivo**: dê zoom (Ctrl +) e mostre que a fórmula é *texto* — escala
  perfeita, sem borrar; e **selecione a fórmula com o mouse** para mostrar que ela é
  copiável. Imagem nenhuma faz isso.
- `overflow-x: auto` nos blocos de equação para telas estreitas, e o `@media print`.

## 6. Acessibilidade e suporte — Pedro Henrique Barcellos (2 min)

- O argumento mais forte do MathML: **leitores de tela leem a fórmula como matemática** —
  "x igual a menos b mais ou menos raiz quadrada de..." — porque a estrutura está no
  markup. Uma imagem só teria um `alt` escrito à mão. Se conseguirem, gravem o
  Narrador/NVDA lendo um bloco: vale muito.
- Suporte: nativo há anos no **Firefox e Safari**; **Chrome e Edge** passaram a suportar a
  partir da **versão 109 (janeiro de 2023)** — antes disso o MathML era o motivo de
  existirem MathJax e KaTeX. Hoje a cobertura é praticamente universal.
- Casos de uso reais: material didático, artigos científicos, EPUB, provas online.

## 7. Fechamento — ambos (1 min)

Gabriel resume o que a página entrega; Pedro Henrique Barcellos fecha com a lição: MathML
devolve a matemática à web como **conteúdo semântico**, não como figura. Encerrem com os
dois nomes e a disciplina.

---

## Dicas de execução

- **Ensaiem cronometrando.** O bloco 3 é o que mais estoura; se precisar cortar, corte do
  bloco 4 (a matemática), nunca do 3 ou do 6.
- Gravem a tela com o editor de um lado e o navegador do outro — a comparação markup ↔
  renderização é o que prova domínio do assunto.
- Ao trocar de apresentador, faça uma passagem explícita ("agora o Pedro Henrique
  Barcellos mostra...") — em vídeo de dupla isso conta ponto.
- Aumente a fonte do editor antes de gravar; markup MathML em fonte pequena é ilegível
  em vídeo.
