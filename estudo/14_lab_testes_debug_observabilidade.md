# 14 - Lab: Testes, Debug e Observabilidade

## Objetivo
Executar suite minima de qualidade e praticar diagnostico usando logs, status endpoints e sinais de runtime.

## Comandos de execucao
```bash
make test
make test-web
make lint
```

## O que observar
- Falhas reais por camada (backend, frontend, sandbox/provider).
- Ponto exato de quebra em logs e traces.
- Diferenca entre problema de ambiente e regressao de codigo.

## Como validar sucesso
1. Rodar testes unitarios e web com resultado esperado.
2. Simular uma falha (ex.: variavel faltante) e diagnosticar pelo log.
3. Documentar runbook de recuperacao para sua maquina.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Teste de integracao falha por infra | DB/Redis sem health | subir stack e validar health antes |
| Falha de provider em teste | credencial ausente | usar filtro de testes ou full mode |
| Lint falha por padrao | diferenca de estilo local | alinhar com regras do repo |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Unit/Web tests | Both | Both |
| Integracoes provider-dependentes | Limitado | Completo |
| Debug de realtime | Medio | Alto |

## Referencia cruzada
- [../arquitetura_projeto/17_testes_operacao_runbook.md](../arquitetura_projeto/17_testes_operacao_runbook.md)
- [../arquitetura_projeto/04_backend_fastapi_lifecycle.md](../arquitetura_projeto/04_backend_fastapi_lifecycle.md)
- [16_checklist_replicacao_final.md](./16_checklist_replicacao_final.md)
