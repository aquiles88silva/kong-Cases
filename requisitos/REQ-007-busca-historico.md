# REQ-007: Busca no Histórico

## Descrição
Implementar funcionalidade de busca no histórico de navegação para permitir que o usuário encontre rapidamente páginas visitadas anteriormente.

## Contexto
Atualmente, o histórico é exibido apenas como uma lista simples. Não há forma de buscar ou filtrar itens do histórico, o que pode ser problemático quando há muitos itens.

## Objetivos
- Permitir buscar no histórico por URL, título ou palavras-chave
- Filtrar histórico por data/período
- Ordenar resultados de forma relevante
- Melhorar experiência de navegação no histórico

## Requisitos Funcionais
1. **Campo de Busca**
   - Campo de busca no modal de histórico
   - Busca em tempo real (filtra enquanto digita)
   - Buscar em URL, título e snippet (se disponível)
   - Suporte a busca case-insensitive

2. **Filtros**
   - Filtrar por data (hoje, última semana, último mês, etc.)
   - Filtrar por domínio
   - Filtrar por tipo de conteúdo (se detectável)
   - Combinar múltiplos filtros

3. **Ordenação**
   - Ordenar por data (mais recente primeiro - padrão)
   - Ordenar por relevância (quando usando busca)
   - Ordenar alfabeticamente
   - Ordenar por frequência de acesso

4. **Resultados**
   - Destacar termos buscados nos resultados
   - Exibir snippet/preview quando disponível
   - Mostrar data/hora de acesso
   - Limitar número de resultados exibidos (paginção ou scroll infinito)

5. **Atalhos e Ações**
   - Enter para abrir item selecionado
   - Delete para remover item do histórico
   - Ctrl+A para selecionar todos
   - Atalho de teclado para abrir histórico com foco no campo de busca

## Requisitos Não Funcionais
- Performance: Busca deve ser instantânea mesmo com 1000+ itens
- Usabilidade: Interface intuitiva similar a outros navegadores
- Responsividade: UI não deve travar durante busca

## Arquitetura Sugerida
```
app/
  services/
    history_search.py      # Serviço de busca no histórico
  views/
    history_dialog.py      # Diálogo de histórico (melhorar)
    search_widget.py       # Widget de busca
```

## Prioridade
Média - Melhoria importante da funcionalidade existente

## Dependências
- Nenhuma

## Estimativa
6-8 horas de desenvolvimento

## Notas
- Considerar indexação do histórico para melhorar performance de busca
- Avaliar uso de algoritmos de relevância (TF-IDF simples) para ordenação
- Implementar cache de resultados de busca para melhorar responsividade

