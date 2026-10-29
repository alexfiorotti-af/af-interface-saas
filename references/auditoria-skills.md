# Auditoria das skills de design de terceiros (29/10/2026)

Leitura do código de cada repositório, sem executar nada. Nenhum tinha instrução maliciosa
(vazar variáveis, ler `~/.ssh`, dar push escondido). Os riscos encontrados são de outro tipo:
código baixado na hora, hooks automáticos, telemetria e envio de código para terceiros.

| Repositório | Veredito | O que aproveitamos | Por que cuidado |
|---|---|---|---|
| pbakaus/impeccable | CAUTION (evitar como plugin) | modos Operar/Convencer, piso de qualidade, lista do que recusar | hooks rodam binário baixado a cada edição; telemetria ligada por padrão (`DO_NOT_TRACK=1`); API que devolve direções remotas |
| Leonxlnx/taste-skill | CAUTION | regras de telas de app (cor em dado, KPI como texto, rosto do produto) | pesada (~56 mil palavras), scripts Node + Chrome, busca imagens em APIs públicas |
| jakubkrehel/skills (better-ui) | SAFE | valores exatos de polimento (scale .96, 150 ms, entradas 300 ms) | — |
| emilkowalski/skills | SAFE | movimento e interação | só markdown |
| nextlevelbuilder/ui-ux-pro-max-skill | SAFE (núcleo) / CAUTION (extras) | dados por indústria como lista de clichês; modelo de manual de marca | extras de logo/CIP leem `~/.claude/.env` e mandam chaves a Gemini/AtlasCloud/MuAPI |
| Nutlope/hallmark | CAUTION | piso anti-"cara de IA" para páginas | instala hook em `settings.json` se pedido; Together AI para imagens |
| superdesigndev/superdesign-skill | AVOID com código de cliente | — | `npx @superdesign/cli@latest` sem versão fixa; envia código do projeto aos servidores deles; exige créditos |
| vercel-labs web-design-guidelines | CAUTION | — | busca as regras numa URL de branch mutável a cada uso |
| Ilm-Alan/frontend-design, MengTo ui/* | SAFE | — | só markdown |

**Regra da casa:** copiar o método para dentro da `af-interface-saas`, nunca instalar plugin
com hook, binário baixado, telemetria ou upload de código.

## Fontes

- Subframe, *Best Claude Code Skills for UI Design (2026, Tested)* — https://www.subframe.com/tips/best-claude-code-skills-for-ui-design
- AgentSkillsHub, *Claude Design Skills for Frontend & UI: 187 Graded* — https://agentskillshub.top/best/ai-design/
- Open Design, skill *brand* (ui-ux-pro-max) — https://open-design.ai/skills/brand/
- Barefaced, *Colour in beauty branding* — https://barefaced.substack.com/p/colour-in-beauty-branding
- Selfnamed, *Design Trends That Define Beauty Branding in 2026* — https://www.blog.selfnamed.com/design/design-branding-trends-2026
- Cosmetics Business, *Colour and packaging trends set to dominate beauty in 2026* — https://cosmeticsbusiness.com/colour-and-packaging-trends-set-to-dominate-beauty
