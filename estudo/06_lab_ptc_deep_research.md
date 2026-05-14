# 06 - Lab: PTC Deep Research

## Objetivo
Executar uma tarefa PTC que use tool calling programatico, gere artefato e demonstre vantagem sobre modo Flash em workload analitico.

## Pre-requisitos
- `05_lab_primeiro_fluxo_e2e.md` concluido.
- Workspace PTC funcional.

## Tempo estimado
- 60 a 90 min.

## Entregaveis
- Uma execucao PTC com eventos de analise multi-etapa.
- Registro das tools acionadas.

## Resultado esperado
Voce comprova na pratica quando o modo PTC entrega valor acima do modo Flash.

## Comandos de execucao
```bash
make up

make test
```

## O que observar
- Uso de `execute_code` e possivel chamada a MCP wrappers.
- Producoes intermediarias de analise (texto estruturado/artefatos).
- Maior tempo inicial, mas maior profundidade de resposta.

## Como validar sucesso
1. Resposta mostra processamento multi-etapa.
2. Ferramentas de analise foram chamadas durante o fluxo.
3. Resultado final inclui conclusao reproduzivel (nao apenas lookup).

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Nao chamou execute_code | prompt simples demais | usar pergunta que exija comparacao/serie temporal |
| Erro de provider | credenciais/fallback indisponivel | verificar config de providers |
| Timeout de fluxo | tarefa muito ampla sem steering | dividir problema e reexecutar |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Fluxo PTC basico | Both | Both |
| Cobertura ampla de dados | Limitado | Completo |
| Analise com intraday rico | Limitado | Completo |

## Referencia cruzada
- [../arquitetura_projeto/05_fluxo_chat_ptc.md](../arquitetura_projeto/05_fluxo_chat_ptc.md)
- [../arquitetura_projeto/07_agente_ptc_core_middlewares.md](../arquitetura_projeto/07_agente_ptc_core_middlewares.md)
- [10_lab_tools_nativos_vs_mcp.md](./10_lab_tools_nativos_vs_mcp.md)
