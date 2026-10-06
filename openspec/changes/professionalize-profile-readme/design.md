# Design

## Context

- O `README.md` é renderizado em github.com/Wems94. O GitHub remove CSS e JS, então o layout depende de Markdown, HTML básico e imagens.
- Dois assets são gerados pelo workflow `.github/workflows/snake.yml` e publicados no branch `output`: `github-snake-dark.svg` e `core-stack-animated.svg` (este último vem de `skillicons.dev` com a lista fixa `py,gcp,postgres,docker,git,github,linux,vscode,bash,azure`).
- Os widgets usam serviços públicos de terceiros: `github-readme-stats.vercel.app`, `github-profile-trophy.vercel.app`, `streak-stats.demolab.com` e `visitor-badge.laobi.icu`. A instância pública do readme-stats sofre limite de requisições com frequência.
- Todas as cores de fundo estão fixas em `#040810` (tema escuro).

Motivação: ver `proposal.md` (seção Why). Requisitos: ver `specs/`.

## Goals / Non-Goals

**Goals:**
- Hierarquia de leitura em "F": quem é → o que entrega (projetos) → com o quê (stack) → como falar com ele.
- Ficar bom nos dois temas do GitHub e no mobile (largura de ~400 px).
- Reduzir a dependência de serviços externos.

**Non-Goals:**
- Criar site/portfólio fora do GitHub.
- Traduzir o README para português (fica como opção futura, ver Open Questions).
- Redesenhar o logo.

## Decisions

### D1. Direção visual — três opções

| Opção | Ideia | Prós | Contras |
|---|---|---|---|
| **A. Executiva / minimalista** | Texto + poucos badges com a cor oficial de cada marca, sem animações, 1 card de linguagens | Leitura mais rápida, aparência sênior, quase nada quebra | Menos "personalidade" visual |
| **B. Equilibrada (recomendada)** | Mantém logo, paleta ciano/roxo e o "Core Stack" animado (corrigido); acrescenta projetos; corta troféus, streak, cobrinha e visitas | Preserva a identidade atual e ganha credibilidade | Ainda depende de 1–2 imagens geradas |
| **C. Atual + ajustes** | Mantém todos os widgets e só adiciona projetos e alt texts | Menor esforço | Continua parecendo "perfil de iniciante"; ruído visual |

**Escolha: B.** A identidade visual (logo, ciano `#00d4ff`) já é um diferencial; o que tira profissionalismo é o excesso de elementos, não o estilo.

### D2. Estrutura de seções (ordem final)
1. Cabeçalho: logo, nome, headline em texto, typing SVG opcional, badges de contato (LinkedIn, e-mail, CV).
2. About (2–4 linhas com resultados) + Currently (3 bullets).
3. Featured Projects: tabela de 2–4 linhas (`Project | Problem | Stack | Result`) ou cards de 2 colunas. Tabela foi escolhida por funcionar no mobile e não depender de imagens.
4. Tech Stack: "Core Stack" animado + até 20 badges em 4 linhas (Cloud, Engineering, Analytics/BI, Tooling) + uma linha de texto "Also: data modeling, data governance, storytelling…".
5. Experience Highlights (opcional): 3 bullets.
6. GitHub Activity: 1 card de linguagens (ou stats + linguagens) lado a lado.
7. Rodapé: formação e idiomas.

Alternativa considerada: colocar projetos depois da stack. Rejeitada porque projetos são a evidência mais forte e devem aparecer antes da dobra.

### D3. Badges
- `style=flat-square`, cor oficial da marca via `logoColor=white` + `color=<hex da marca>`. Alternativa: cor única neutra (`161b22`) — ainda mais sóbria; aceitável se a opção A for escolhida.
- Cortar: Lake House, Data Mesh, ETL/ELT, Event-Driven, API Integration, Data Modeling, Data Warehousing, BI, Storytelling, Dashboard 360°, K-means, Quantitative Analysis, Data Governance, Data Quality, AI Tools, SMTP, Excel, Sheets → passam para a linha de texto ou saem.

### D4. Core Stack
Trocar a lista de ícones no workflow por algo como `py,gcp,postgres,docker,git,github,bash` + ícones que o skillicons não tem (dbt, Airflow, Snowflake, BigQuery) ficam nos badges. Se Azure, Linux e VS Code não forem usados em projetos, saem. Alternativa: substituir o SVG animado por uma linha estática de ícones (`skillicons.dev` direto) — mais simples, perde a animação.

### D5. Temas claro/escuro
Usar `<picture>` com `<source media="(prefers-color-scheme: dark)">` para cards e logo, ou trocar os fundos fixos por transparentes (`bg_color=00000000`, `hide_border=true`). A transparência é mais simples e foi a escolhida; `<picture>` fica para o logo, se ele não tiver fundo transparente.

### D6. Widgets
Manter só `top-langs` (e, se desejado, `stats`). Para não depender da instância pública da Vercel, a opção robusta é gerar os SVGs no próprio workflow (ex.: action `lowlighter/metrics` ou fazer deploy de uma instância própria do readme-stats) e publicar no branch `output`, igual ao que já é feito com o "Core Stack".

### D7. Semântica
Trocar `<h2>▸ About</h2>` por `## About` (âncoras e outline navegável no GitHub). O "▸" decorativo pode ser mantido como emoji/texto se fizer parte da identidade visual, mas dentro de um título Markdown.

## Risks / Trade-offs

- [Faltam métricas reais para "About" e projetos] → o William fornece os números; até lá, a seção fica fora do ar em vez de ganhar texto genérico (spec `featured-work`).
- [Poucos repositórios públicos para destacar] → destacar 2 projetos bem documentados, ou criar um case de portfólio (ex.: pipeline dbt + BigQuery com dados públicos).
- [Remover a cobrinha muda o workflow] → manter o job, mas tirar só a etapa da cobrinha; o "Core Stack" continua sendo gerado.
- [Perda de "personalidade"] → a opção B mantém logo, paleta e animação principal.

## Migration Plan

1. Editar o README num branch e conferir a pré-visualização nos temas claro e escuro e no mobile.
2. Ajustar o workflow e rodar `workflow_dispatch` para regenerar os assets no branch `output`.
3. Merge na `main`. Rollback: `git revert` do commit (os assets antigos continuam no histórico do branch `output`).

## Open Questions

- Haverá uma versão em português (`README.pt-BR.md` com link no topo)? Não altera a estrutura; pode ser feita depois.
- Quais 2–4 repositórios entram em "Featured Projects" e quais métricas podem ser publicadas? (Conteúdo — não muda a estrutura.)
