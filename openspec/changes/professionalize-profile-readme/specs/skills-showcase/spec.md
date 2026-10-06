# Spec Delta

## Purpose

Apresenta a stack técnica de forma enxuta, coerente e comprovável, separando ferramentas de competências comportamentais e analíticas.

## ADDED Requirements

### Requirement: Badges apenas para tecnologias
Badges SHALL representar somente ferramentas, linguagens ou plataformas; competências e conceitos MUST aparecer como texto.

#### Scenario: Competência analítica
- **WHEN** "Storytelling with Data" ou "Quantitative Analysis" é listado
- **THEN** aparece como texto, não como badge

### Requirement: Quantidade limitada de badges
A seção de habilidades MUST ter no máximo 20 badges, agrupados em até 4 categorias.

#### Scenario: Contagem
- **WHEN** os badges do README são contados
- **THEN** o total é menor ou igual a 20

### Requirement: Paleta consistente
Todos os badges SHALL seguir uma única regra de cor (cor oficial da marca ou uma cor neutra única) e um único estilo.

#### Scenario: Comparação visual
- **WHEN** dois badges de categorias diferentes são comparados
- **THEN** a cor de ambos segue a mesma regra

### Requirement: Core Stack coerente com as habilidades
Cada tecnologia exibida no "Core Stack" MUST também constar na seção de habilidades ou em um projeto em destaque.

#### Scenario: Ícone sem correspondência
- **WHEN** o "Core Stack" mostra uma tecnologia (ex.: Azure)
- **THEN** essa tecnologia também aparece nas habilidades ou em um projeto; caso contrário, sai do "Core Stack"
