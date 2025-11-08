# REQ-011: Temas Personalizáveis

## Descrição
Implementar sistema de temas personalizáveis para permitir que o usuário customize a aparência do navegador além do tema escuro atual.

## Contexto
Atualmente, o Kong possui apenas um tema escuro hardcoded. Usuários podem querer temas claros, personalizados ou seguir preferências do sistema.

## Objetivos
- Fornecer múltiplos temas pré-definidos
- Permitir criação de temas customizados
- Suportar tema claro e escuro
- Seguir preferências do sistema operacional

## Requisitos Funcionais
1. **Temas Pré-definidos**
   - Tema Escuro (atual)
   - Tema Claro
   - Tema Automático (seguir preferências do sistema)
   - Tema Azul Escuro
   - Tema Verde Escuro
   - Tema Sepia

2. **Personalização de Tema**
   - Editor de tema visual
   - Escolher cores para:
     - Fundo principal
     - Fundo secundário
     - Texto principal
     - Texto secundário
     - Destaque/Accent
     - Bordas
   - Preview em tempo real
   - Salvar tema customizado
   - Exportar/importar temas

3. **Aplicação de Tema**
   - Aplicar tema imediatamente sem reiniciar
   - Tema aplicado a toda interface (toolbar, menus, diálogos)
   - Tema aplicado ao webview quando possível
   - Persistir escolha de tema

4. **Interface de Seleção**
   - Menu ou diálogo para escolher tema
   - Preview de cada tema
   - Nome e descrição de cada tema
   - Indicador do tema atual

5. **Temas do Sistema**
   - Detectar preferência de tema do sistema (claro/escuro)
   - Aplicar automaticamente quando "Automático" selecionado
   - Atualizar quando preferência do sistema mudar

## Requisitos Não Funcionais
- Performance: Mudança de tema deve ser instantânea
- Consistência: Todas as partes da UI devem seguir o tema
- Acessibilidade: Manter contraste adequado em todos os temas

## Arquitetura Sugerida
```
app/
  models/
    theme_model.py         # Modelo para temas
  services/
    theme_service.py       # Serviço de gerenciamento de temas
    theme_loader.py        # Carregador de temas
  views/
    theme_dialog.py        # Diálogo de seleção de tema
    theme_editor.py        # Editor de tema customizado
  themes/
    dark.json              # Tema escuro
    light.json             # Tema claro
    blue_dark.json         # Tema azul escuro
    # etc.
```

## Prioridade
Baixa - Melhoria estética, não funcional

## Dependências
- Nenhuma

## Estimativa
10-14 horas de desenvolvimento

## Notas
- Considerar usar arquivos JSON ou CSS para definir temas
- Avaliar uso de QStyleSheet ou QPalette do PyQt6
- Implementar validação de contraste para acessibilidade
- Considerar integração com bibliotecas de cores (como `colorthief` para extrair cores de imagens)

