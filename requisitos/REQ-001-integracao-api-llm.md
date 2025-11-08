# REQ-001: Integração com API de LLM Real

## Descrição
Implementar integração real com APIs de Large Language Models (LLMs) para substituir a resposta simulada atual no chat. O sistema deve suportar múltiplos provedores de IA (OpenAI, Google Gemini, DeepSeek, etc.) e permitir que o usuário escolha qual agente utilizar.

## Contexto
Atualmente, o chat exibe apenas uma resposta simulada quando o usuário envia uma mensagem. O README menciona que a integração com APIs de LLM é um dos próximos passos sugeridos.

## Objetivos
- Substituir a resposta simulada por chamadas reais a APIs de LLM
- Suportar múltiplos provedores (OpenAI, Gemini, DeepSeek, etc.)
- Permitir configuração de chaves de API por provedor
- Enviar o contexto capturado da página junto com a mensagem do usuário
- Exibir respostas em tempo real (streaming) quando possível
- Tratar erros de API de forma elegante

## Requisitos Funcionais
1. **Configuração de APIs**
   - Criar interface de configurações para gerenciar chaves de API
   - Armazenar chaves de forma segura (criptografadas ou em variáveis de ambiente)
   - Permitir adicionar/remover/editar provedores

2. **Integração com Provedores**
   - Implementar adaptadores para cada provedor de LLM
   - Suportar OpenAI (GPT-3.5, GPT-4)
   - Suportar Google Gemini
   - Suportar DeepSeek
   - Permitir extensão para novos provedores

3. **Envio de Mensagens**
   - Enviar mensagem do usuário para a API selecionada
   - Incluir contexto capturado da página (título, URL, seleção, snippet) quando disponível
   - Manter histórico de conversa por sessão
   - Suportar streaming de respostas quando a API permitir

4. **Tratamento de Erros**
   - Exibir mensagens de erro amigáveis ao usuário
   - Tratar casos de API indisponível, chave inválida, limite de taxa excedido
   - Permitir retry automático em caso de falhas temporárias

## Requisitos Não Funcionais
- Segurança: Não expor chaves de API no código ou logs
- Performance: Respostas devem aparecer em menos de 5 segundos para APIs rápidas
- Usabilidade: Interface deve indicar claramente quando está processando uma resposta
- Extensibilidade: Arquitetura deve facilitar adição de novos provedores

## Arquitetura Sugerida
```
app/
  services/
    llm/
      __init__.py
      base_provider.py      # Interface base para provedores
      openai_provider.py    # Implementação OpenAI
      gemini_provider.py    # Implementação Gemini
      deepseek_provider.py  # Implementação DeepSeek
      provider_factory.py   # Factory para criar provedores
  models/
    api_config.py          # Modelo para configurações de API
```

## Prioridade
Alta - Funcionalidade core do aplicativo

## Dependências
- Nenhuma

## Estimativa
8-12 horas de desenvolvimento

## Notas
- Considerar usar bibliotecas como `openai`, `google-generativeai` para facilitar integração
- Avaliar uso de async/await para melhor performance
- Considerar cache de respostas para reduzir custos de API

