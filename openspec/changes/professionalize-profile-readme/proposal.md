# Proposal

## Why

O README do perfil comunica bem a stack, mas lê como uma vitrine de widgets: 34 badges (muitos para soft skills), troféus, contador de visitas e animação da cobrinha ocupam mais espaço que qualquer evidência de trabalho entregue. Um recrutador que passa ~30 segundos na página não encontra projetos, resultados nem uma frase clara de posicionamento — e, no tema claro do GitHub, os cards com fundo `#040810` fixo aparecem como blocos pretos.

## What Changes

Cada item é uma **opção de melhoria** independente; o `design.md` traz a recomendação e as alternativas.

- **Identidade e posicionamento**
  - Nome em caixa normal ("William Sebastião") e uma headline estática legível sem animação; o typing SVG vira complemento opcional.
  - Seção "About" reescrita com 2–3 resultados quantificados (ex.: "reduzi o tempo de processamento de X para Y") no lugar de afirmações genéricas.
  - Bloco curto "Currently": no que está trabalhando, o que está estudando, o tipo de vaga que busca.
  - Contato ampliado: e-mail, LinkedIn e, se houver, portfólio ou CV, agrupados num só lugar (hoje o LinkedIn aparece duas vezes).
- **Habilidades**
  - Badges só para ferramentas/tecnologias; competências ("Storytelling", "Dashboard 360°", "Quantitative Analysis") viram texto.
  - Redução de ~34 para ~15–20 badges, priorizando a stack que de fato aparece nos projetos.
  - Paleta unificada (uma cor neutra ou a cor oficial de cada marca), no lugar de quatro cores arbitrárias por categoria.
  - O SVG "Core Stack" passa a refletir a stack declarada (hoje mostra Azure, VS Code e Linux, mas não BigQuery, dbt, Airflow nem Snowflake).
- **Trabalho em destaque (novo)**
  - Seção "Featured Projects" com 3–4 repositórios: problema, stack e resultado de cada um.
  - Opcional: "Experience Highlights" com 2–3 entregas de impacto (sem dados confidenciais).
- **Atividade no GitHub**
  - **BREAKING (visual)**: remoção de troféus, contador de visitas e cobrinha; no máximo um card de estatísticas + linguagens.
  - Cards com suporte a tema claro e escuro.
- **Acessibilidade e manutenção**
  - Títulos em Markdown (`##`) em vez de `<h2>▸`, gerando âncoras.
  - `alt` em todas as imagens.

## Capabilities

### New Capabilities
- `profile-identity`: cabeçalho, headline, "About", "Currently" e canais de contato do perfil.
- `skills-showcase`: apresentação da stack técnica (badges e o SVG "Core Stack") e das competências.
- `featured-work`: seção de projetos em destaque e de entregas de impacto.
- `activity-widgets`: cards dinâmicos de atividade no GitHub e o comportamento deles nos temas claro/escuro.

### Modified Capabilities
_Nenhuma — o repositório ainda não tinha specs._

## Impact

- `README.md`: reestruturação completa das seções.
- `.github/workflows/snake.yml`: a etapa da cobrinha pode sair; a lista de ícones do "Core Stack" muda; opcionalmente, ganha uma etapa que gera os cards de estatísticas localmente.
- `assets/`: talvez novas imagens (thumbnails de projetos, variante clara do logo).
- Dependências externas: menos serviços de terceiros (vercel.app, laobi.icu), portanto menos imagens quebradas quando eles saírem do ar.
- Conteúdo que só o William pode fornecer: métricas reais de impacto, lista de projetos em destaque, e-mail/portfólio públicos.
