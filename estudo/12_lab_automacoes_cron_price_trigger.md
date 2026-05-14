# 12 - Lab: Automacoes (Cron e Price Trigger)

## Objetivo
Criar automacoes, disparar manualmente e observar execucao assincrona com historico de resultados.

## Comandos de execucao
```bash
make up
curl -s http://localhost:8000/health
```

## O que observar
- Registro da automacao no backend.
- Trigger manual e/ou por agenda/preco quando habilitado.
- Execucao aparecendo no historico com status coerente.

## Como validar sucesso
1. Criar automacao cron simples e executar trigger manual.
2. Confirmar execucao em `executions`.
3. Validar que workflow concluiu com status esperado.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Trigger nao dispara | automacao pausada/inativa | revisar status e endpoint usado |
| Execucao falha sem detalhe | erro interno em workflow | inspecionar logs e payload de execucao |
| Price trigger nao ativa | fonte realtime indisponivel | usar full mode ou trigger manual |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Automacao cron + trigger manual | Both | Both |
| Price trigger realtime | Limitado | Completo |
| Historico de execucoes | Both | Both |

## Referencia cruzada
- [../arquitetura_projeto/15_automacoes_e_execucao_assincrona.md](../arquitetura_projeto/15_automacoes_e_execucao_assincrona.md)
- [../arquitetura_projeto/13_protocolos_tempo_real.md](../arquitetura_projeto/13_protocolos_tempo_real.md)
- [13_lab_persistencia_checkpointer_store.md](./13_lab_persistencia_checkpointer_store.md)
