# Tasks

## 1. Conteúdo (fornecido pelo William)

- [ ] 1.1 Escolher a direção visual (A, B ou C do `design.md` D1) e registrar a escolha no `design.md`
- [ ] 1.2 Listar 2–4 projetos com link, problema, stack e resultado; verificar que cada item tem os 4 campos (spec `featured-work`)
- [ ] 1.3 Levantar 2–3 resultados quantificáveis e publicáveis para o "About"; verificar que nenhum expõe dados confidenciais
- [ ] 1.4 Definir os canais de contato públicos (e-mail, portfólio/CV) e confirmar que os links abrem

## 2. Cabeçalho, About e contato

- [ ] 2.1 Reescrever o cabeçalho com nome em caixa normal, headline em texto e `alt` no logo; verificar com o typing SVG bloqueado que nome e headline continuam visíveis
- [ ] 2.2 Reescrever "About" (≤ 4 linhas, ≥ 2 resultados) e adicionar "Currently" (≤ 3 itens); verificar na pré-visualização
- [ ] 2.3 Consolidar o contato numa só seção e remover o LinkedIn duplicado; verificar com `grep -c linkedin README.md` que só existe o link de contato
- [ ] 2.4 Converter todos os `<h2>` em títulos `##`; verificar que as âncoras aparecem no outline do GitHub

## 3. Projetos em destaque

- [ ] 3.1 Adicionar a seção "Featured Projects" (tabela) com os itens de 1.2; verificar que todos os links abrem
- [ ] 3.2 (Opcional) Adicionar "Experience Highlights" com ≤ 3 bullets; revisar se há dados sensíveis

## 4. Stack e habilidades

- [ ] 4.1 Reduzir os badges para ≤ 20 e mover competências para texto; verificar contando `img.shields.io` no README
- [ ] 4.2 Aplicar uma única regra de cor aos badges; verificar visualmente lado a lado
- [ ] 4.3 Atualizar a lista de ícones do "Core Stack" em `.github/workflows/snake.yml`; rodar `workflow_dispatch` e verificar o novo SVG no branch `output`

## 5. Widgets de atividade

- [ ] 5.1 Remover troféus, streak, visitor badge e a referência à cobrinha do README; verificar que nenhum desses domínios aparece mais no arquivo
- [ ] 5.2 Remover a etapa da cobrinha do workflow; verificar que o job roda verde e continua gerando o "Core Stack"
- [ ] 5.3 Deixar os cards restantes com fundo transparente (ou `<picture>` claro/escuro) e `alt`; verificar a pré-visualização nos dois temas

## 6. Verificação integrada

- [ ] 6.1 Revisar o perfil em github.com nos temas claro e escuro, no desktop e no mobile, conferindo cada cenário das specs
- [ ] 6.2 Rodar `openspec validate professionalize-profile-readme --strict` e verificar que passa

## Workflow follow-up

- Arquivar a mudança com `openspec archive professionalize-profile-readme` depois que o README novo estiver na `main`.
