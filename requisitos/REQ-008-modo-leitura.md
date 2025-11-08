# REQ-008: Modo de Leitura

## Descrição
Implementar modo de leitura que remove elementos de distração da página (anúncios, menus, sidebars) e apresenta apenas o conteúdo principal em formato otimizado para leitura.

## Contexto
Muitos navegadores modernos possuem modo de leitura que melhora a experiência de leitura de artigos e páginas de conteúdo. Esta funcionalidade complementa bem o sistema de captura de conteúdo existente.

## Objetivos
- Detectar automaticamente quando uma página é adequada para modo de leitura
- Remover elementos de distração
- Formatar conteúdo de forma legível
- Permitir personalização da apresentação

## Requisitos Funcionais
1. **Detecção Automática**
   - Detectar quando página contém artigo ou conteúdo principal
   - Sugerir modo de leitura quando apropriado
   - Indicador visual quando modo de leitura está disponível

2. **Processamento de Conteúdo**
   - Extrair conteúdo principal (article, main, ou conteúdo relevante)
   - Remover anúncios, menus, sidebars, rodapés
   - Remover elementos de navegação
   - Preservar estrutura (títulos, parágrafos, listas, imagens)
   - Manter links funcionais

3. **Formatação**
   - Aplicar tipografia otimizada para leitura
   - Ajustar largura de linha para legibilidade
   - Espaçamento adequado entre elementos
   - Suporte a imagens (redimensionar se necessário)

4. **Personalização**
   - Escolher tamanho de fonte
   - Escolher família de fonte (serif, sans-serif, monospace)
   - Escolher tema (claro, escuro, sepia)
   - Escolher largura de coluna
   - Salvar preferências do usuário

5. **Controles**
   - Botão para ativar/desativar modo de leitura
   - Atalho de teclado (ex: F9)
   - Botão para voltar à visualização original
   - Opção para imprimir em modo de leitura

## Requisitos Não Funcionais
- Performance: Ativação do modo de leitura deve ser instantânea
- Confiabilidade: Funcionar em pelo menos 70% das páginas de artigos
- Acessibilidade: Manter contraste adequado e suporte a leitores de tela

## Arquitetura Sugerida
```
app/
  services/
    reader_mode.py         # Serviço de modo de leitura
    content_extractor.py   # Extrator de conteúdo (pode reutilizar de REQ-005)
  views/
    reader_view.py         # Visualização de modo de leitura
    reader_toolbar.py      # Barra de ferramentas do modo de leitura
```

## Prioridade
Baixa - Funcionalidade nice-to-have

## Dependências
- Pode reutilizar código de REQ-005 (Melhorias na Captura de Conteúdo)

## Estimativa
10-14 horas de desenvolvimento

## Notas
- Considerar usar bibliotecas como `readability` ou `trafilatura` para extração
- Avaliar uso de CSS customizado para formatação
- Implementar fallback gracioso quando modo de leitura não é aplicável

