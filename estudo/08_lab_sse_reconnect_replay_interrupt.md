# 08 - Lab: SSE Reconnect, Replay e Interrupt

## Objetivo
Validar resiliencia de fluxo em tempo real: reconectar stream, recuperar eventos e interromper execucao com seguranca.

## Pre-requisitos
- `05_lab_primeiro_fluxo_e2e.md` concluido.
- Uma thread PTC ativa para teste de reconexao.

## Tempo estimado
- 50 a 80 min.

## Entregaveis
- Evidencia de reconnect com continuidade.
- Evidencia de replay e de interrupt/cancel.

## Resultado esperado
Voce domina o comportamento de resiliencia do chat em cenarios de desconexao.

## Comandos de execucao
```bash
make up

curl -s http://localhost:8000/api/v1/threads/<THREAD_ID>/status
```

## O que observar
- Workflow continua apos desconexao do cliente.
- Reconnect devolve progresso recente.
- Interrupt altera estado sem corromper thread.

## Como validar sucesso
1. Desconectar/reconectar e manter continuidade.
2. Replay traz eventos anteriores quando aplicavel.
3. Interrupt/cancel produz status coerente.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Reconnect sem progresso | thread_id/cursor incorreto | validar thread e endpoint corretos |
| Cancel nao efetivo | workflow ja finalizado | checar status antes da acao |
| Eventos duplicados na UI | deduplicacao ausente no cliente | revisar logica de merge por event id |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| SSE reconnect/replay | Both | Both |
| Interrupt/cancel | Both | Both |
| Carga de eventos alta | Medio | Alto |

## Referencia cruzada
- [../arquitetura_projeto/13_protocolos_tempo_real.md](../arquitetura_projeto/13_protocolos_tempo_real.md)
- [../arquitetura_projeto/08_subagentes_plan_mode_hitl.md](../arquitetura_projeto/08_subagentes_plan_mode_hitl.md)
- [16_checklist_replicacao_final.md](./16_checklist_replicacao_final.md)
