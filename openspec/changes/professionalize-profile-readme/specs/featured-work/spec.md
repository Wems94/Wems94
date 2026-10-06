# Spec Delta

## Purpose

Dá ao visitante evidência concreta do trabalho do William por meio de projetos e entregas selecionados, conectando a stack a resultados.

## ADDED Requirements

### Requirement: Projetos em destaque
O README SHALL ter uma seção "Featured Projects" com 2 a 4 itens, cada um com nome com link, problema resolvido (1 frase), stack principal e resultado ou aprendizado.

#### Scenario: Projeto com link
- **WHEN** o visitante clica no nome de um projeto
- **THEN** abre o repositório ou demo público correspondente

#### Scenario: Item incompleto
- **WHEN** falta o problema, a stack ou o resultado de um projeto
- **THEN** o projeto não é publicado na seção até ser completado

### Requirement: Destaques de experiência sem dados confidenciais
Se houver a seção "Experience Highlights", ela MUST ter no máximo 3 entregas e MUST NOT expor nomes de clientes, dados internos ou números confidenciais sem autorização.

#### Scenario: Métrica sensível
- **WHEN** um resultado depende de um número interno da empresa
- **THEN** é apresentado em termos relativos (ex.: "-60% no tempo de processamento") ou omitido
