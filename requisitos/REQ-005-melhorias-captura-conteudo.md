# REQ-005: Melhorias na Captura de Conteúdo

## Descrição
Melhorar o sistema de captura de conteúdo da página para ser mais robusto, capturar mais informações úteis e lidar melhor com páginas que bloqueiam JavaScript ou têm políticas de segurança restritivas.

## Contexto
O README menciona que a captura de conteúdo pode falhar em páginas com políticas de segurança restritivas. O sistema atual captura apenas título, URL, seleção e um snippet básico do texto.

## Objetivos
- Melhorar taxa de sucesso da captura
- Capturar mais informações relevantes
- Tratar melhor casos de falha
- Adicionar opções de formatação e processamento

## Requisitos Funcionais
1. **Captura Aprimorada**
   - Capturar metadados da página (description, keywords, author)
   - Capturar imagens principais da página
   - Capturar links importantes
   - Capturar código (se página de documentação técnica)
   - Capturar tabelas e listas formatadas
   - Detectar idioma da página

2. **Tratamento de Falhas**
   - Detectar quando captura falha silenciosamente
   - Tentar métodos alternativos (fallback)
   - Exibir mensagem clara ao usuário quando captura não é possível
   - Sugerir alternativas (copiar URL manualmente, etc.)

3. **Processamento de Conteúdo**
   - Remover elementos não essenciais (anúncios, menus, rodapés)
   - Extrair apenas conteúdo principal (article, main)
   - Formatar texto capturado de forma legível
   - Preservar estrutura (títulos, parágrafos, listas)

4. **Opções de Captura**
   - Modo simples (atual: título, URL, seleção, snippet)
   - Modo completo (todos os metadados e conteúdo)
   - Modo artigo (apenas conteúdo principal)
   - Modo técnico (inclui código e documentação)

5. **Visualização e Edição**
   - Preview do conteúdo capturado antes de enviar
   - Permitir editar conteúdo capturado
   - Destacar partes importantes
   - Resumir automaticamente conteúdo muito longo

## Requisitos Não Funcionais
- Performance: Captura não deve demorar mais de 2 segundos
- Confiabilidade: Funcionar em pelo menos 80% das páginas comuns
- Usabilidade: Interface clara indicando o que foi capturado

## Arquitetura Sugerida
```
app/
  services/
    capture_service.py     # Serviço atual (melhorar)
    content_processor.py   # Processador de conteúdo
    fallback_capture.py    # Métodos alternativos de captura
```

## Prioridade
Média - Melhoria importante da funcionalidade existente

## Dependências
- Nenhuma

## Estimativa
8-12 horas de desenvolvimento

## Notas
- Considerar usar bibliotecas como `readability` ou `trafilatura` para extração de conteúdo principal
- Avaliar uso de seletores CSS mais específicos para melhorar captura
- Implementar cache de capturas para evitar recapturar mesma página

