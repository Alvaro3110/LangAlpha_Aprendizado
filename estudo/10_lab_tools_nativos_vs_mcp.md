# 10 - Lab: Tools Nativas vs MCP

## Objetivo
Construir criterio pratico para decidir entre tool nativa e MCP+execute_code em diferentes tipos de pergunta.

## Comandos de execucao
```bash
make up

make test
```

## O que observar
- Lookup curto tende a usar tool nativa.
- Analise de dados volumosos tende a usar `execute_code` + MCP.
- Tempo/custo/contexto diferem entre as trilhas.

## Como validar sucesso
1. Rodar uma pergunta de lookup e registrar tool usada.
2. Rodar uma pergunta analitica longa e registrar tool usada.
3. Comparar qualidade, latencia e rastreabilidade dos dois resultados.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Sempre cai em tool nativa | prompt pouco exigente | formular tarefa com transformacao/modelagem |
| Sempre cai em MCP | prompt super amplo | separar lookup inicial de analise profunda |
| Resultado inconsistente | provider fallback variando | fixar contexto e registrar source retornado |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Comparacao estrutural nativa/MCP | Both | Both |
| Volume de dados avancado | Limitado | Completo |
| Cobertura multi-mercado | Limitado | Completo |

## Referencia cruzada
- [../arquitetura_projeto/10_dados_financeiros_provider_chain.md](../arquitetura_projeto/10_dados_financeiros_provider_chain.md)
- [../arquitetura_projeto/11_mcp_servers_e_tools_nativos.md](../arquitetura_projeto/11_mcp_servers_e_tools_nativos.md)
- [../arquitetura_projeto/07_agente_ptc_core_middlewares.md](../arquitetura_projeto/07_agente_ptc_core_middlewares.md)
