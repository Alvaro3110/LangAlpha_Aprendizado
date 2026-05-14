# 02 - Glossario e Mental Models

## Objetivo
Padronizar vocabulario tecnico para reduzir confusao entre conceitos parecidos durante os labs.

## Pre-requisitos
- Leitura de `../arquitetura_projeto/01_visao_geral_produto.md`.

## Tempo estimado
- 60 a 90 min.

## Entregaveis
- Glossario anotado com exemplos seus.

## Resultado esperado
Voce consegue explicar com suas palavras os blocos principais sem confundir termos.

## Glossario essencial
| Termo | Definicao pratica |
|---|---|
| PTC | Modo de agente com sandbox e `execute_code` para analise profunda |
| Flash | Modo rapido sem sandbox, para interacoes leves |
| Workspace | Contexto persistente de pesquisa e artefatos |
| Thread | Conversa dentro do workspace |
| HITL | Interrupcao com aprovacao/rejeicao humana |
| Checkpointer | Persistencia do estado incremental do grafo |
| Store | Memoria estruturada de contexto adicional |
| SSE | Streaming de eventos de workflow |
| WS | Canal de dados de mercado em tempo real |
| MCP | Protocolo para conectar servers de ferramentas |

## Mental models
1. "Thread e historico de conversa; workspace e ambiente de trabalho".
2. "SSE entrega progresso da execucao; DB entrega estado persistente".
3. "Tool nativa para lookup curto; MCP+code para processamento pesado".
4. "Plan mode protege execucao mutante com aprovacao humana".

## Referencia cruzada
- [../arquitetura_projeto/05_fluxo_chat_ptc.md](../arquitetura_projeto/05_fluxo_chat_ptc.md)
- [../arquitetura_projeto/13_protocolos_tempo_real.md](../arquitetura_projeto/13_protocolos_tempo_real.md)
- [10_lab_tools_nativos_vs_mcp.md](./10_lab_tools_nativos_vs_mcp.md)
