# Casos de Teste - REQ-001: Integração com API de LLM Real

## Informações Gerais
- **Requisito**: REQ-001 - Integração com API de LLM Real
- **Prioridade**: Alta
- **Data de Criação**: 2025-11-08
- **Status**: Pendente

---

## CT-001: Configuração de Chave de API - Adicionar Novo Provedor

### Objetivo
Verificar se o sistema permite adicionar um novo provedor de LLM com sua respectiva chave de API.

### Pré-condições
- Usuário está na tela de configurações
- Usuário possui uma chave de API válida de um provedor suportado

### Passos
1. Acessar a seção de configurações de API
2. Clicar em "Adicionar Novo Provedor"
3. Selecionar o tipo de provedor (OpenAI, Gemini, DeepSeek)
4. Inserir a chave de API
5. Salvar a configuração

### Resultado Esperado
- Provedor é adicionado com sucesso
- Chave de API é armazenada de forma segura (criptografada)
- Provedor aparece na lista de provedores disponíveis
- Mensagem de confirmação é exibida

### Critérios de Aceitação
- ✅ Chave é armazenada de forma segura (não visível em texto plano)
- ✅ Provedor fica disponível para uso imediatamente após adição
- ✅ Interface exibe feedback visual de sucesso

---

## CT-002: Configuração de Chave de API - Editar Provedor Existente

### Objetivo
Verificar se o sistema permite editar a chave de API de um provedor já configurado.

### Pré-condições
- Existe pelo menos um provedor configurado no sistema

### Passos
1. Acessar a seção de configurações de API
2. Localizar o provedor a ser editado
3. Clicar em "Editar"
4. Atualizar a chave de API
5. Salvar as alterações

### Resultado Esperado
- Chave de API é atualizada com sucesso
- Configuração anterior é substituída pela nova
- Mensagem de confirmação é exibida

### Critérios de Aceitação
- ✅ Nova chave substitui a anterior
- ✅ Alterações são salvas corretamente
- ✅ Provedor continua funcionando com a nova chave

---

## CT-003: Configuração de Chave de API - Remover Provedor

### Objetivo
Verificar se o sistema permite remover um provedor configurado.

### Pré-condições
- Existe pelo menos um provedor configurado no sistema

### Passos
1. Acessar a seção de configurações de API
2. Localizar o provedor a ser removido
3. Clicar em "Remover"
4. Confirmar a remoção

### Resultado Esperado
- Provedor é removido da lista
- Chave de API é deletada do sistema
- Provedor não fica mais disponível para uso
- Mensagem de confirmação é exibida

### Critérios de Aceitação
- ✅ Provedor é completamente removido
- ✅ Dados sensíveis são apagados permanentemente
- ✅ Interface atualiza a lista imediatamente

---

## CT-004: Integração com OpenAI - Envio de Mensagem Simples

### Objetivo
Verificar se o sistema consegue enviar uma mensagem simples para a API da OpenAI e receber uma resposta.

### Pré-condições
- OpenAI está configurado com chave de API válida
- Usuário está na interface do chat

### Passos
1. Selecionar OpenAI como provedor ativo
2. Digitar uma mensagem simples: "Olá, como você está?"
3. Enviar a mensagem

### Resultado Esperado
- Mensagem é enviada para a API da OpenAI
- Resposta é recebida e exibida no chat
- Resposta aparece em menos de 5 segundos (requisito não funcional)

### Critérios de Aceitação
- ✅ Resposta é recebida com sucesso
- ✅ Resposta é relevante e coerente
- ✅ Tempo de resposta está dentro do esperado (< 5s)

---

## CT-005: Integração com Google Gemini - Envio de Mensagem Simples

### Objetivo
Verificar se o sistema consegue enviar uma mensagem simples para a API do Google Gemini e receber uma resposta.

### Pré-condições
- Google Gemini está configurado com chave de API válida
- Usuário está na interface do chat

### Passos
1. Selecionar Google Gemini como provedor ativo
2. Digitar uma mensagem simples: "Explique o que é inteligência artificial"
3. Enviar a mensagem

### Resultado Esperado
- Mensagem é enviada para a API do Google Gemini
- Resposta é recebida e exibida no chat
- Resposta aparece em menos de 5 segundos

### Critérios de Aceitação
- ✅ Resposta é recebida com sucesso
- ✅ Resposta é relevante e coerente
- ✅ Tempo de resposta está dentro do esperado

---

## CT-006: Integração com DeepSeek - Envio de Mensagem Simples

### Objetivo
Verificar se o sistema consegue enviar uma mensagem simples para a API do DeepSeek e receber uma resposta.

### Pré-condições
- DeepSeek está configurado com chave de API válida
- Usuário está na interface do chat

### Passos
1. Selecionar DeepSeek como provedor ativo
2. Digitar uma mensagem simples: "Qual é a capital do Brasil?"
3. Enviar a mensagem

### Resultado Esperado
- Mensagem é enviada para a API do DeepSeek
- Resposta é recebida e exibida no chat
- Resposta aparece em menos de 5 segundos

### Critérios de Aceitação
- ✅ Resposta é recebida com sucesso
- ✅ Resposta é relevante e coerente
- ✅ Tempo de resposta está dentro do esperado

---

## CT-007: Envio de Mensagem com Contexto da Página

### Objetivo
Verificar se o sistema envia o contexto capturado da página (título, URL, seleção, snippet) junto com a mensagem do usuário.

### Pré-condições
- Um provedor está configurado e ativo
- Usuário capturou contexto de uma página (título, URL, seleção de texto)

### Passos
1. Capturar contexto de uma página web (título, URL, seleção de texto)
2. Abrir o chat
3. Verificar se o contexto está visível na interface
4. Digitar uma mensagem relacionada ao contexto: "Resuma este conteúdo"
5. Enviar a mensagem

### Resultado Esperado
- Contexto capturado é exibido na interface do chat
- Contexto é enviado junto com a mensagem para a API
- Resposta da API considera o contexto fornecido
- Resposta faz referência ao conteúdo capturado

### Critérios de Aceitação
- ✅ Contexto é incluído na requisição à API
- ✅ Resposta demonstra que o contexto foi considerado
- ✅ Todos os elementos do contexto (título, URL, seleção, snippet) são enviados

---

## CT-008: Manutenção de Histórico de Conversa

### Objetivo
Verificar se o sistema mantém o histórico de conversa por sessão.

### Pré-condições
- Um provedor está configurado e ativo
- Usuário está em uma sessão de chat

### Passos
1. Enviar primeira mensagem: "Meu nome é João"
2. Aguardar resposta
3. Enviar segunda mensagem: "Qual é o meu nome?"
4. Aguardar resposta

### Resultado Esperado
- Primeira mensagem e resposta são mantidas no histórico
- Segunda mensagem é enviada junto com o contexto da primeira
- Resposta da segunda mensagem demonstra conhecimento do histórico
- Todas as mensagens permanecem visíveis na interface

### Critérios de Aceitação
- ✅ Histórico completo é mantido durante a sessão
- ✅ API recebe o contexto completo da conversa
- ✅ Respostas demonstram continuidade da conversa

---

## CT-009: Streaming de Respostas (quando suportado)

### Objetivo
Verificar se o sistema exibe respostas em tempo real (streaming) quando a API suporta.

### Pré-condições
- Um provedor que suporta streaming está configurado e ativo (ex: OpenAI)
- Usuário está na interface do chat

### Passos
1. Enviar uma mensagem que gere uma resposta longa: "Escreva um parágrafo sobre inteligência artificial"
2. Observar a exibição da resposta

### Resultado Esperado
- Resposta é exibida progressivamente (streaming)
- Texto aparece em tempo real, não apenas após conclusão
- Indicador visual mostra que a resposta está sendo gerada

### Critérios de Aceitação
- ✅ Resposta aparece progressivamente
- ✅ Interface indica claramente que está processando
- ✅ Experiência do usuário é melhorada com streaming

---

## CT-010: Tratamento de Erro - Chave de API Inválida

### Objetivo
Verificar se o sistema trata adequadamente o erro quando uma chave de API inválida é fornecida.

### Pré-condições
- Um provedor está configurado com chave de API inválida ou expirada

### Passos
1. Tentar enviar uma mensagem usando o provedor com chave inválida
2. Observar o comportamento do sistema

### Resultado Esperado
- Sistema detecta o erro de autenticação
- Mensagem de erro amigável é exibida ao usuário
- Erro não expõe detalhes técnicos sensíveis
- Sistema sugere verificar a chave de API nas configurações

### Critérios de Aceitação
- ✅ Erro é tratado graciosamente
- ✅ Mensagem de erro é clara e útil para o usuário
- ✅ Nenhuma informação sensível é exposta
- ✅ Usuário é direcionado para corrigir o problema

---

## CT-011: Tratamento de Erro - API Indisponível

### Objetivo
Verificar se o sistema trata adequadamente quando a API está indisponível.

### Pré-condições
- Um provedor está configurado corretamente
- API do provedor está temporariamente indisponível (simular com timeout ou erro 503)

### Passos
1. Tentar enviar uma mensagem
2. Observar o comportamento do sistema quando a API não responde

### Resultado Esperado
- Sistema detecta que a API está indisponível
- Mensagem de erro amigável é exibida
- Sistema oferece opção de retry automático
- Usuário pode tentar novamente manualmente

### Critérios de Aceitação
- ✅ Erro é detectado corretamente
- ✅ Mensagem informa que o serviço está temporariamente indisponível
- ✅ Opção de retry é oferecida
- ✅ Sistema não trava ou fica em estado inconsistente

---

## CT-012: Tratamento de Erro - Limite de Taxa Excedido

### Objetivo
Verificar se o sistema trata adequadamente quando o limite de taxa (rate limit) da API é excedido.

### Pré-condições
- Um provedor está configurado corretamente
- Limite de requisições da API foi excedido

### Passos
1. Enviar múltiplas mensagens rapidamente até exceder o limite
2. Observar o comportamento do sistema

### Resultado Esperado
- Sistema detecta o erro de rate limit
- Mensagem de erro informa sobre o limite excedido
- Sistema sugere aguardar antes de tentar novamente
- Opção de retry automático após intervalo apropriado

### Critérios de Aceitação
- ✅ Erro de rate limit é detectado
- ✅ Mensagem é clara sobre o problema
- ✅ Sistema sugere tempo de espera apropriado
- ✅ Retry automático respeita o intervalo necessário

---

## CT-013: Retry Automático em Falhas Temporárias

### Objetivo
Verificar se o sistema realiza retry automático em caso de falhas temporárias.

### Pré-condições
- Um provedor está configurado corretamente
- API retorna erro temporário (ex: 500, 503, timeout)

### Passos
1. Configurar sistema para retry automático (3 tentativas)
2. Enviar mensagem quando API está com falha temporária
3. Observar comportamento do sistema

### Resultado Esperado
- Sistema detecta falha temporária
- Realiza retry automático (até 3 tentativas)
- Se bem-sucedido após retry, exibe resposta normalmente
- Se falhar após todas as tentativas, exibe mensagem de erro

### Critérios de Aceitação
- ✅ Retry automático é executado
- ✅ Número máximo de tentativas é respeitado
- ✅ Intervalo entre tentativas é apropriado
- ✅ Usuário é informado sobre o status das tentativas

---

## CT-014: Alternância Entre Provedores

### Objetivo
Verificar se o usuário pode alternar entre diferentes provedores durante uma sessão.

### Pré-condições
- Múltiplos provedores estão configurados (ex: OpenAI e Gemini)

### Passos
1. Selecionar OpenAI como provedor ativo
2. Enviar uma mensagem
3. Alterar para Gemini
4. Enviar outra mensagem

### Resultado Esperado
- Provedor pode ser alterado facilmente
- Cada mensagem é enviada para o provedor selecionado
- Histórico de conversa é mantido independente do provedor
- Interface indica claramente qual provedor está ativo

### Critérios de Aceitação
- ✅ Alternância entre provedores funciona corretamente
- ✅ Mensagens são enviadas para o provedor correto
- ✅ Interface atualiza o provedor ativo visualmente

---

## CT-015: Segurança - Chaves de API Não Expostas

### Objetivo
Verificar se as chaves de API não são expostas no código, logs ou interface.

### Pré-condições
- Pelo menos um provedor está configurado

### Passos
1. Verificar código-fonte por chaves de API em texto plano
2. Verificar logs do sistema
3. Verificar interface do usuário (inspecionar elementos)
4. Verificar variáveis de ambiente

### Resultado Esperado
- Nenhuma chave de API aparece em texto plano no código
- Logs não contêm chaves de API completas
- Interface não exibe chaves de API (apenas indicador de que está configurada)
- Chaves são armazenadas de forma criptografada ou em variáveis de ambiente seguras

### Critérios de Aceitação
- ✅ Chaves não aparecem em código-fonte
- ✅ Logs não expõem chaves completas (apenas máscaras)
- ✅ Interface não exibe chaves
- ✅ Armazenamento é seguro (criptografado ou em variáveis de ambiente)

---

## CT-016: Performance - Tempo de Resposta

### Objetivo
Verificar se as respostas aparecem dentro do tempo esperado (< 5 segundos para APIs rápidas).

### Pré-condições
- Um provedor está configurado e ativo
- Conexão de internet estável

### Passos
1. Enviar uma mensagem simples
2. Medir o tempo desde o envio até a exibição completa da resposta
3. Repetir para diferentes provedores

### Resultado Esperado
- Respostas aparecem em menos de 5 segundos para APIs rápidas
- Sistema exibe indicador de carregamento durante o processamento
- Tempo de resposta é consistente

### Critérios de Aceitação
- ✅ 90% das respostas aparecem em menos de 5 segundos
- ✅ Indicador de carregamento é exibido durante processamento
- ✅ Performance é aceitável para a experiência do usuário

---

## CT-017: Usabilidade - Indicador de Processamento

### Objetivo
Verificar se a interface indica claramente quando está processando uma resposta.

### Pré-condições
- Um provedor está configurado e ativo

### Passos
1. Enviar uma mensagem
2. Observar a interface durante o processamento
3. Verificar indicadores visuais

### Resultado Esperado
- Indicador visual (spinner, barra de progresso, etc.) é exibido
- Mensagem do usuário fica marcada como "processando"
- Interface não permite envio de nova mensagem durante processamento
- Indicador desaparece quando resposta é recebida

### Critérios de Aceitação
- ✅ Indicador visual é claro e visível
- ✅ Usuário entende que o sistema está processando
- ✅ Interface previne ações durante processamento

---

## CT-018: Extensibilidade - Adição de Novo Provedor

### Objetivo
Verificar se a arquitetura facilita a adição de novos provedores.

### Pré-condições
- Arquitetura base está implementada
- Desenvolvedor precisa adicionar novo provedor (ex: Anthropic Claude)

### Passos
1. Criar novo arquivo de provedor seguindo o padrão base_provider.py
2. Implementar métodos obrigatórios
3. Registrar provedor no factory
4. Testar integração

### Resultado Esperado
- Novo provedor pode ser adicionado seguindo o padrão existente
- Código mínimo é necessário (apenas implementação do provedor)
- Novo provedor funciona imediatamente após implementação
- Não é necessário modificar código existente

### Critérios de Aceitação
- ✅ Arquitetura permite adição sem modificar código existente
- ✅ Padrão é claro e fácil de seguir
- ✅ Novo provedor funciona corretamente após implementação

---

## CT-019: Validação de Chave de API ao Adicionar

### Objetivo
Verificar se o sistema valida a chave de API ao adicionar um novo provedor.

### Pré-condições
- Usuário está na tela de configurações

### Passos
1. Tentar adicionar um provedor com chave de API inválida
2. Observar comportamento do sistema

### Resultado Esperado
- Sistema valida a chave antes de salvar
- Mensagem de erro é exibida se chave for inválida
- Provedor não é adicionado se chave for inválida
- Usuário pode corrigir a chave e tentar novamente

### Critérios de Aceitação
- ✅ Validação ocorre antes de salvar
- ✅ Mensagem de erro é clara
- ✅ Sistema não permite salvar chave inválida

---

## CT-020: Envio de Mensagem Vazia

### Objetivo
Verificar se o sistema trata adequadamente tentativas de enviar mensagem vazia.

### Pré-condições
- Um provedor está configurado e ativo

### Passos
1. Tentar enviar uma mensagem vazia
2. Observar comportamento do sistema

### Resultado Esperado
- Sistema impede envio de mensagem vazia
- Mensagem de validação é exibida
- Botão de envio fica desabilitado para mensagens vazias

### Critérios de Aceitação
- ✅ Mensagem vazia não é enviada
- ✅ Validação é clara para o usuário
- ✅ Interface previne envio inválido

---

## Resumo de Cobertura

### Requisitos Funcionais Cobertos
- ✅ **RF-001**: Configuração de APIs (CT-001, CT-002, CT-003, CT-019)
- ✅ **RF-002**: Integração com Provedores (CT-004, CT-005, CT-006, CT-014, CT-018)
- ✅ **RF-003**: Envio de Mensagens (CT-007, CT-008, CT-009, CT-020)
- ✅ **RF-004**: Tratamento de Erros (CT-010, CT-011, CT-012, CT-013)

### Requisitos Não Funcionais Cobertos
- ✅ **RNF-001**: Segurança (CT-015)
- ✅ **RNF-002**: Performance (CT-016)
- ✅ **RNF-003**: Usabilidade (CT-017)
- ✅ **RNF-004**: Extensibilidade (CT-018)

### Total de Casos de Teste
- **20 casos de teste** cobrindo todos os requisitos funcionais e não funcionais

---

## Notas de Execução
- Casos de teste devem ser executados em ambiente de teste isolado
- Chaves de API de teste devem ser utilizadas (não usar chaves de produção)
- Alguns casos podem requerer simulação de erros de API (usar mocks quando necessário)
- Casos de performance devem ser executados com conexão estável

