---
name: af-interface-saas
description: Usar ao desenhar, redesenhar ou revisar telas e a identidade visual de app/SaaS da AF (ClavusOS, CoachOS, Pousa, ORDO e próximos nichos): marca, navegação, sistema visual, white-label e polimento.
---

# Interface e identidade de SaaS — padrão AF

Repertório de front-end e de marca da AF Tecnologia, destilado de skills públicas auditadas em 29/10/2026 (pbakaus/impeccable, Leonxlnx/taste-skill, jakubkrehel/skills, emilkowalski/skills, nextlevelbuilder/ui-ux-pro-max-skill, Nutlope/hallmark e outras; ver `references/auditoria-skills.md`). Nada aqui baixa código, chama rede ou manda telemetria: é só método.

Dois modos, decididos pela tela, não pelo produto:
- **Operar** — telas em que a pessoa TRABALHA (agenda, clientes, caixa, painel, configurações). Clareza e padrões conhecidos vêm antes da expressão; a marca aparece nos detalhes.
- **Convencer** — vitrine, página de venda, posts. Ali o design é a persuasão; mais escala e mais marca.

## Referências (ler quando a tarefa pedir)

| Arquivo | Quando |
|---|---|
| `references/identidade-de-nicho.md` | criar ou refazer a marca de um produto/nicho novo |
| `references/marca-clavusos.md` | qualquer tela, peça ou material do ClavusOS |
| `references/tokens-clavusos.css` / `.json` | implementar o ClavusOS ou derivar outro nicho do mesmo sistema |
| `references/auditoria-skills.md` | antes de instalar qualquer skill de design de terceiros |

## Antes de desenhar

1. **Leia o que existe**: o CSS/telas do repo e capture prints do estado atual (subir local e tirar screenshot no celular 390px e no notebook 1366px). O visual velho é evidência e anti-referência: num redesign, nunca "dar um polimento" no visual descartado.
2. **Inventário de tarefas**: liste as 3–5 coisas que a usuária faz todo dia, por frequência. A mais frequente fica a UM toque da primeira tela.
3. **Mostre antes de executar**: protótipo navegável das telas principais (artefato Design) para aprovação do Alex antes de mexer no código de produção. Aplicar no código em **branch + PR**, nunca direto na main de produção.

## Identidade de marca (resumo — método completo em `references/identidade-de-nicho.md`)

1. **Liste os clichês do nicho** antes de criar (no de beleza: rosa-chiclete + dourado, letra cursiva, flor/lábios/coroa, degradê rosa-roxo). Eles viram a lista do que NÃO fazer.
2. **A forma vem do ofício**, não de enfeite: o símbolo é um objeto que só esse nicho reconhece, construído em geometria e vivendo em código (`marca.ts`), nunca gerado por IA de imagem.
3. **Essência em 3 palavras** com o que cada uma significa na prática, e uma frase de propósito.
4. **Cor**: um fundo tonal quente, um escuro de autoridade para texto e um único acento de marca; um destaque precioso usado em um lugar só.
5. **Letra**: uma display com caráter (ex.: Fraunces eixo SOFT) + uma sans limpa; no máximo 2 famílias.
6. **Voz**: tabela "assim não / assim sim" com textos reais do produto.
7. **Aplicações reais**: ícone, post, story (zonas de corte), cartão, perfil, e-mail.
8. **White-label**: o que muda por cliente (nome, logo, cor) e o que nunca muda.
9. Entregar como **manual** (canvas Design) + `docs/MARCA.md` + `marca.ts` + assets gerados por script.

## Navegação (onde a maioria dos apps erra)

- **Celular**: barra fixa embaixo com 4 abas + botão central "+". Nunca menu de topo rolando de lado, nunca dois andares de menu, nunca submenu em abas por cima do conteúdo.
- O **"+" cria qualquer coisa** (horário, venda, lançamento, cliente) numa tela/folha só, com um atalho contextual.
- Visões dentro de uma área (Dia/Semana/Equipe, Hoje/Mês) são **seletor segmentado** dentro da página, não abas de navegação. O item ativo compara caminho **e** query.
- Configurações e conta: no avatar do topo (celular) ou no rodapé do menu lateral (notebook).
- **Notebook**: menu lateral escuro com as mesmas áreas; no conteúdo, duas colunas (trabalho à esquerda, avisos e próximo passo à direita) que empilham no celular na ordem de importância.

## A primeira tela ("Hoje")

- O título É a informação: "5 atendimentos hoje", não "Bem-vinda de volta". A data escrita como se fala ("Quinta-feira, 29 de outubro").
- Números são texto, não cartões: "R$ 350 previstos, 1 concluído". Nada de três cartões de KPI empilhados ocupando a tela do celular.
- Avisos viram UMA lista "Para hoje" com ação, não faixas coloridas empilhadas.
- Mostre o próximo passo: o próximo atendimento com o botão da ação.
- **Uma peça só do produto** (a assinatura), feita dos dados reais. No ClavusOS: a linha do dia por profissional e o anel de ciclo da unha no avatar.

## Sistema visual

- **Um fundo tonal, uma tinta, um acento.** Fundo levemente quente (ex.: porcelana #F7F2EF), cartões brancos separados por degrau de tom, sem borda e sem sombra em repouso. Sombra só no que flutua (barra de abas, botão +, folha, menu).
- **White-label de verdade**: o acento é UMA variável (`--cor`, a cor do studio/cliente) e os tons de apoio derivam dela com `color-mix(in oklch, var(--cor) 12%, white)`. Testar com 4 acentos antes de aprovar. Em SVG, cor vai por atributo com o hex real (atributo não aceita `var()`).
- Cor vai em dado e estado, não em moldura: situação (concluído, a confirmar, vencida), identidade de pessoas (cada profissional um tom pálido derivado da sua cor), o "agora" na linha do tempo.
- Destaque precioso (ex.: dourado) aparece em UM lugar só (o saldo do dia).
- **Tipografia**: display para títulos e valores, sans para o resto. Evitar Poppins/Inter/Geist como voz da marca. Números com `font-variant-numeric: tabular-nums`. Fontes com fallback de métrica próxima.
- Escala curta: título 30–36px, seção 16px, corpo 15px, apoio 13px. Rótulos em letra normal, nunca CAIXA ALTA espaçada.
- Raios por nível: cartão 22–24px, controle 14px, pílula 999px.

## Proibidos (cara de app gerado ou datado)

- Gradiente no cabeçalho, em botão ou em texto; brilho/blob decorativo de fundo.
- Borda colorida grossa na esquerda de cartões e linhas.
- Emoji como ícone (mensagem para a cliente no WhatsApp pode ter emoji). Ícones são SVG de traço, uma família só, traço 1.8, `currentColor`.
- Rótulo pequeno acima do título (eyebrow), numeração 01/02/03, contador de passos ou de slides ("Passo 1 de 4").
- Palavra de destaque colorida/itálica dentro de título.
- Cartão dentro de cartão; ícone em círculo colorido em cada KPI; sparkline decorativa.
- Vidro/blur decorativo.
- Etiqueta de situação esticada na largura toda (seletor `.x span{display:block}` pegando a etiqueta: use `> span` e `width: max-content`).
- Tabela de 4+ colunas no celular: vira lista de linhas (título, subtítulo, valor à direita).

## Polimento com valores exatos (de jakubkrehel/better-ui e emilkowalski)

- Botão pressionado: `scale: .96` em 150ms ease-out; desabilitado não escala.
- Interações frequentes (abas, hover de linha) respondem na hora ou em ≤150ms só em opacity/background.
- Entradas raras: opacity + 12px de translateY em 300ms ease-out, escalonadas 100ms. Saída menor e mais curta (150ms).
- Nunca `transition: all`; nomear as propriedades.
- Hover só dentro de `@media (hover: hover)`; `overscroll-behavior: contain` em folhas e menus roláveis.
- Tudo animado tem alternativa em `prefers-reduced-motion`.
- Raio externo = raio interno + padding quando há superfícies aninhadas.
- Navegadores também carregam a marca: `::selection`, `accent-color`, foco, `text-underline-offset`.

## Acessibilidade e celular

- Toque mínimo 44px; botão principal 48–54px.
- Contraste 4.5:1 no texto (inclusive o cinza de apoio e o branco sobre o acento) — conferir com cálculo, não no olho.
- Elementos reais: `<button>`, `<a href>`, `<input>` com `<label>`; `aria-label` em botão só de ícone; `aria-current` na aba ativa.
- Celular 360–430px é o caso principal; `overflow-x: clip` em html/body; tabelas largas rolam dentro de uma caixa.
- Respeitar a área da barra do sistema: barra de abas com ~86px e `env(safe-area-inset-bottom)`.

## Estados honestos

Vazio com frase gentil e a ação que resolve; zero aparece como zero; carregando e erro desenhados; textos com as palavras do ofício ("Unha vencida há 2 dias", "A confirmar", "Livre das 12h às 14h"), nunca "Itens" ou "Registros".

## Antes de entregar

1. Screenshot real em 390px e 1366px de cada tela mexida, num lote só; corrigir o que um olhar mostra antes de olhar de novo. Sem internet no ambiente? Embutir as fontes num CSS local (pacotes `@fontsource-variable/*` fora do repo) e injetar na captura, com `bypassCSP` só no navegador de teste.
2. Conferir: navegação em 1 andar, tarefa mais frequente a 1 toque, um acento só, nenhum item da lista de proibidos, contraste calculado.
3. Testar o white-label com 4 cores.
4. Rodar tipos e testes do projeto; registrar a decisão no log de decisões do repo.
5. Fechar com o ritual da casa: branch + PR, atualizar a ficha do projeto no cofre cerebro-af e commit + push.

## Segurança ao adotar skills de terceiros

Não instalar como plugin skills com hooks que rodam binário baixado, telemetria ligada por padrão, instruções buscadas de URL mutável a cada uso, ou que enviam código do projeto para serviço externo (impeccable como plugin, superdesign, vercel web-design-guidelines sem cópia local, extras do ui-ux-pro-max que leem chaves do `.env`). Copiar o método para dentro desta skill, como feito aqui.

## Nicho beleza (ClavusOS): "Porcelana & Esmalte" + marca "Cereja & Porcelana"

Fundo porcelana #F7F2EF, papel #FFFFFF, nude #EFE7E2, ameixa #2D1B2E (texto e menu lateral), ameixa suave #6B5A66, verniz #B8892E (só a gota; em texto #8A620F, só o saldo), **cereja #A8174A** como acento padrão da ClavusOS (opções de studio testadas: esmalte #C8246A, malva #86476C, sálvia #3E6A5A). Profissionais com tons pálidos derivados da cor de cada uma. Símbolo: unha amêndoa a −20° com lúnula vazada, reflexo de laca e gota de verniz, vindo de `app/src/marca.ts`. Detalhes em `references/marca-clavusos.md`.
