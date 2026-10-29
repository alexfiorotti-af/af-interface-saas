# Identidade visual de um nicho — o método da AF

Usado para criar a marca do ClavusOS ("Cereja & Porcelana", out/2026) e para os próximos
nichos do construtor de SaaS. A lógica é a mesma das telas: decidir a partir do ofício e dos
dados reais, nunca do padrão do nicho nem do gosto do modelo.

## 1. Pesquisa (curta, com fonte)

- **O que o nicho repete.** Bancos de "estilo por indústria" (ex.: `ui-ux-pro-max`, arquivos
  `logo/industries.csv` e `cip/industries.csv`) servem como **lista de clichês**: no de beleza
  dão rosa + dourado, letra cursiva, flor e lábios. É exatamente o que evitar.
- **O que diferencia.** Análises de cor de marcas de beleza mostram nudes/cinzas como fundo
  comum e tons escuros (quase-preto) como raros e associados a autoridade; cor viva só em marcas
  "brincalhonas". Tendência 2026: tipografia como protagonista (o nome é o foco).
- **Referências reais do nicho** (portfólios de salões): anotar paleta, letra, conceito do
  logo e aplicações — para saber onde o mercado está, não para copiar.

## 2. Essência

- Uma **frase de propósito** que diga para quem e por quê (ClavusOS: "Quem cuida das unhas dos
  outros merece um sistema que cuide do studio dela").
- **Três palavras**, cada uma com o que significa no produto (Acolhedora, Precisa, Direta).
- Um quadro **"o que o nicho repete × o que a marca faz"**.

## 3. Símbolo

- Um objeto **do ofício** que só quem é do nicho reconhece (a unha amêndoa com a lúnula).
- Construído em **geometria simples** numa grade (96), com uma regra de ângulo/proporção
  explicável em uma linha. Vive em código (`marca.ts`), gera todos os assets por script.
- Versões: cheia (principal), traço (interface), noturna (sobre escuro), selo, favicon.
- Um único **detalhe precioso** (a gota de verniz) — o brilho da marca mora só ali.

## 4. Logotipo

- Nome na display com caráter; sufixo de sistema ("OS") pequeno, na cor da marca e na letra do
  app. Montar com `<tspan>` (o sufixo acompanha a largura real da fonte).
- Respiro (ex.: altura da maiúscula) e tamanhos mínimos (logotipo 120 px, símbolo 20 px).

## 5. Cor

- Fundo tonal quente (não branco de hospital), um escuro de autoridade para texto e menu,
  **um** acento de marca, um tom de apoio derivado (acento a 12% no branco) e um precioso
  (dourado) para um lugar só.
- Tabela com hex, RGB, uso e **contraste calculado** (texto ≥4,5:1).
- Barra de proporção (ex.: 56% fundo, 14% papel, 20% escuro, 8% acento, 2% precioso).

## 6. Tipografia

- Display com personalidade (Fraunces com eixo SOFT dá a curva feminina sem cursiva) + sans
  limpa (Instrument Sans). Escala curta. Sem caixa alta espaçada, sem itálico no meio de título.

## 7. Elementos gráficos

- Derivados do símbolo e do produto: moldura na forma do símbolo para fotos, padrão tom sobre
  tom para impressos, e as peças-assinatura do app (no ClavusOS, o anel do ciclo e a linha do
  dia). Cada um com regra de uso.

## 8. Voz

- Tabela "Onde / Assim não / Assim sim" com textos reais: lembrete, botão, erro, vazio,
  situação, frase de venda. Emoji só em mensagens humanas para a cliente, nunca como ícone.

## 9. Aplicações

- Ícone do app, post 4:5, story 9:16 (respeitando ~220 px do topo e ~400 px da base em
  1080×1920; o @ uma vez só, no alto), cartão de retorno (frente com padrão, verso com a data),
  perfil de WhatsApp/Instagram, cabeçalho de e-mail.

## 10. White-label e usos incorretos

- O que o cliente troca (nome, logo, cor) e o que nunca muda (fundo, escuro, letras, desenho
  das telas, "com tecnologia <marca>" no rodapé).
- "Não faça" com exemplos desenhados: esticar, girar fora do ângulo, degradê, cor fora da
  paleta, trocar a letra ou pôr sombra, acento sobre acento.

## Entrega

1. Manual visual (canvas Design, uma prancha por seção).
2. `docs/MARCA.md` no repositório do produto (texto do manual).
3. `app/src/marca.ts` atualizado + `scripts/gerar-marca.mjs` regenerando `docs/marca/`.
4. Decisão registrada no log do repositório.
