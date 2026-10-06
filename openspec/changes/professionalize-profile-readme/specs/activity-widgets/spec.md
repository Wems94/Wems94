# Spec Delta

## Purpose

Define quais indicadores dinâmicos de atividade no GitHub aparecem no perfil e garante que continuem legíveis e confiáveis em qualquer tema.

## ADDED Requirements

### Requirement: Widgets limitados e sóbrios
O perfil MUST exibir no máximo 2 widgets de atividade e MUST NOT exibir troféus, contador de visitas nem animações decorativas de contribuição.

#### Scenario: Renderização do perfil
- **WHEN** o README é renderizado
- **THEN** não aparecem troféus, contador de visitas nem a animação da cobrinha

### Requirement: Compatibilidade com temas claro e escuro
Toda imagem com fundo próprio SHALL ter variante para tema claro e para tema escuro, ou fundo transparente.

#### Scenario: Tema claro
- **WHEN** o visitante usa o tema claro do GitHub
- **THEN** nenhum widget aparece como um bloco escuro sobre fundo branco

### Requirement: Degradação graciosa
Todo widget SHALL ter `alt` descritivo, e o README MUST continuar legível se o serviço que gera o widget estiver indisponível.

#### Scenario: Serviço externo indisponível
- **WHEN** a imagem de um widget falha ao carregar
- **THEN** o texto alternativo descreve o conteúdo e o layout das outras seções não quebra
