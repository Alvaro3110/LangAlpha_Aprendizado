# 13 - Lab: Persistencia, Checkpointer e Store

## Objetivo
Inspecionar persistencia de negocio e persistencia de estado de execucao para entender como retomar, auditar e depurar workflows.

## Comandos de execucao
```bash
make up
make migrate
```

## O que observar
- Tabelas `conversation_*` recebendo queries/responses/usage.
- Tabelas de checkpoint/store recebendo estado incremental.
- Coerencia entre status de thread e estado persistido.

## Como validar sucesso
1. Confirmar registros em conversa para os turnos executados.
2. Confirmar existencia de checkpoints para a thread.
3. Cruzar estado final da thread com dados persistidos.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Sem registros de conversa | migracao ausente/erro de DB | reaplicar migracoes e checar pool |
| Sem checkpoint | fluxo nao passou por runtime esperado | executar novo turno e observar logs |
| Estado divergente | persistencia parcial apos falha | usar replay/status para reconciliar |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Persistencia conversa | Both | Both |
| Checkpoint/store | Both | Both |
| Cenarios de carga alta | Medio | Alto |

## Referencia cruzada
- [../arquitetura_projeto/14_banco_migracoes_persistencia.md](../arquitetura_projeto/14_banco_migracoes_persistencia.md)
- [../arquitetura_projeto/05_fluxo_chat_ptc.md](../arquitetura_projeto/05_fluxo_chat_ptc.md)
- [14_lab_testes_debug_observabilidade.md](./14_lab_testes_debug_observabilidade.md)
