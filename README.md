# Sistema de Gestão de Notas Fiscais

## Problema

Empresas precisam coletar dados via formulário externo (sem login) e
processar internamente com validação e controle de status.

## Desafio

-   Unificar formulário externo e interno
-   Controlar múltiplos modos (create, view, edit)
-   Implementar filtros dinâmicos por status
-   Garantir consistência com acesso via URL direta

## Solução

### Arquitetura

-   SPA Angular com separação de contextos (externo vs interno)
-   Roteamento orientado a contexto (mode via route data)
-   State management com Signals
-   Componentes reutilizáveis (form e tabela)

### Fluxo

Email → Link com token → Formulário externo → Persistência → Backoffice
→ Listagem → Validação → Histórico

### Decisões Técnicas

-   Uso de signals + computed + effect
-   Separação entre estado de UI e estado de negócio
-   Reuso do formulário em múltiplos contextos
-   Uso de rota como fonte de verdade

## Problemas Enfrentados

### Status complexo

Inicialmente múltiplos estados simultâneos → simplificado para estado
único.

### Reatividade do formulário

Uso correto de computed + effect.

### Readonly vs Disabled

Implementado via template/diretiva.

## Resultado

-   Fluxo completo funcional
-   Arquitetura escalável
-   Base pronta para evolução
