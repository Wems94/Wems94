# Spec Delta

## Purpose

Garante que quem abre o perfil entenda em poucos segundos quem é o William, que problema ele resolve, o que busca e como contatá-lo.

## ADDED Requirements

### Requirement: Headline estática legível
O cabeçalho SHALL exibir o nome em caixa normal e uma headline em texto puro com cargo, especialidade e localização, visível sem depender de imagem ou animação externa.

#### Scenario: Serviço de imagem fora do ar
- **WHEN** o serviço do typing SVG não responde
- **THEN** o nome e a headline continuam visíveis como texto no README

#### Scenario: Leitor de tela
- **WHEN** um leitor de tela percorre o cabeçalho
- **THEN** ele lê o nome e a headline completos, e o logo tem `alt` descritivo

### Requirement: About orientado a resultados
A seção "About" MUST ter no máximo 4 frases ou bullets e conter ao menos 2 resultados concretos (métrica, escala ou impacto no negócio).

#### Scenario: Leitura rápida por recrutador
- **WHEN** alguém lê apenas a seção "About"
- **THEN** encontra ao menos dois resultados mensuráveis ou verificáveis, e não só adjetivos

### Requirement: Status atual
O perfil SHALL ter um bloco "Currently" com no máximo 3 itens: trabalho atual, aprendizado em curso e tipo de oportunidade buscada.

#### Scenario: Disponibilidade para vagas
- **WHEN** o William está aberto a oportunidades
- **THEN** o bloco informa o tipo de vaga (ex.: Analytics Engineer, remoto/híbrido)

### Requirement: Contato consolidado
O README SHALL listar todos os canais públicos de contato (LinkedIn obrigatório; e-mail e portfólio/CV quando existirem) numa única seção, sem repetir o mesmo link em outras seções.

#### Scenario: Contato sem LinkedIn
- **WHEN** o visitante prefere não usar o LinkedIn
- **THEN** encontra ao menos um canal alternativo na seção de contato

#### Scenario: Sem duplicação
- **WHEN** o README é renderizado
- **THEN** cada canal de contato aparece uma única vez como chamada para ação
