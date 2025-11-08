# REQ-010: Sistema de Atalhos de Teclado

## Descrição
Implementar sistema completo de atalhos de teclado para todas as funcionalidades do navegador, melhorando a produtividade e experiência do usuário.

## Contexto
Atualmente, apenas alguns atalhos básicos existem (Ctrl+Enter para enviar chat). Um navegador moderno deve ter atalhos para todas as ações principais.

## Objetivos
- Definir atalhos padrão para todas as funcionalidades
- Permitir personalização de atalhos
- Exibir atalhos disponíveis na interface
- Suportar atalhos globais (quando aplicável)

## Requisitos Funcionais
1. **Atalhos de Navegação**
   - Ctrl+T: Nova aba
   - Ctrl+W: Fechar aba atual
   - Ctrl+Shift+W: Fechar todas as abas
   - Ctrl+Tab: Próxima aba
   - Ctrl+Shift+Tab: Aba anterior
   - Ctrl+1-9: Ir para aba N
   - Alt+←: Voltar
   - Alt+→: Avançar
   - F5: Recarregar
   - Ctrl+F5: Recarregar ignorando cache
   - Ctrl+R: Recarregar
   - Alt+Home: Página inicial

2. **Atalhos de Endereço e Busca**
   - Ctrl+L: Focar barra de endereço
   - Ctrl+K: Focar barra de endereço (modo busca)
   - Ctrl+E: Focar barra de endereço
   - F6: Alternar foco entre endereço e página

3. **Atalhos de Página**
   - Ctrl+F: Buscar na página
   - F3: Próxima ocorrência na busca
   - Shift+F3: Ocorrência anterior
   - Ctrl+G: Próxima ocorrência
   - Esc: Fechar busca/fechar diálogos
   - F11: Tela cheia
   - Ctrl+Plus: Zoom in
   - Ctrl+Minus: Zoom out
   - Ctrl+0: Resetar zoom

4. **Atalhos de Funcionalidades**
   - Ctrl+D: Adicionar favorito
   - Ctrl+Shift+D: Adicionar todos os favoritos
   - Ctrl+H: Abrir histórico
   - Ctrl+Shift+B: Mostrar/ocultar favoritos
   - Ctrl+J: Abrir downloads
   - Ctrl+Shift+Delete: Limpar dados de navegação
   - Ctrl+,: Abrir configurações
   - F9: Modo de leitura (se implementado)

5. **Atalhos de Chat**
   - Ctrl+Enter: Enviar mensagem (já implementado)
   - Shift+Enter: Nova linha (já implementado)
   - Ctrl+K: Focar chat (se não usado para busca)

6. **Personalização**
   - Diálogo de configuração de atalhos
   - Lista de todos os atalhos disponíveis
   - Permitir redefinir atalhos
   - Detectar conflitos de atalhos
   - Restaurar padrões
   - Exportar/importar configurações de atalhos

7. **Ajuda Contextual**
   - Exibir atalhos em tooltips quando disponível
   - Menu "Ajuda" com lista completa de atalhos
   - Indicador visual quando atalho está disponível

## Requisitos Não Funcionais
- Consistência: Atalhos devem seguir convenções de outros navegadores quando possível
- Usabilidade: Atalhos devem ser intuitivos e fáceis de lembrar
- Flexibilidade: Sistema deve permitir fácil adição de novos atalhos

## Arquitetura Sugerida
```
app/
  models/
    shortcuts_model.py     # Modelo para atalhos
  services/
    shortcut_service.py    # Serviço de gerenciamento de atalhos
  views/
    shortcuts_dialog.py    # Diálogo de configuração de atalhos
  controllers/
    shortcut_controller.py # Controller para atalhos
```

## Prioridade
Média - Melhora significativamente a usabilidade

## Dependências
- REQ-002 (Suporte para Guias) - alguns atalhos dependem de abas

## Estimativa
8-10 horas de desenvolvimento

## Notas
- PyQt6 possui QShortcut para implementar atalhos
- Considerar usar QKeySequence para parsing de combinações de teclas
- Avaliar necessidade de atalhos globais (requer QxtGlobalShortcut ou similar)

