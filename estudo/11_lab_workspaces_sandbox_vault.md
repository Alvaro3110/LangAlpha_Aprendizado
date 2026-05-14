# 11 - Lab: Workspaces, Sandbox e Vault

## Objetivo
Validar lifecycle completo de workspace e uso de vault por workspace em runtime de sandbox.

## Comandos de execucao
```bash
make up
curl -s http://localhost:8000/health
```

## O que observar
- Transicoes start/stop/refresh funcionando.
- Sessao/sandbox reconectando sem perda de estado essencial.
- Segredo salvo no vault sendo disponibilizado para uso no workspace.

## Como validar sucesso
1. Criar workspace e executar start/stop/start.
2. Executar uma tarefa apos restart e confirmar continuidade operacional.
3. Inserir segredo no vault e confirmar disponibilidade em tool que usa segredo.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Workspace preso em status intermediario | corrida de acoes concorrentes | repetir acao com estado limpo e revisar logs |
| Segredo nao chega no runtime | push de vault falhou | atualizar segredo novamente e validar endpoint |
| Sessao invalida apos restart | cache stale de sessao | forcar refresh workspace/sessao |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Lifecycle workspace | Both | Both |
| Vault basico por workspace | Both | Both |
| Uso de segredo em integracao externa | Limitado | Completo |

## Referencia cruzada
- [../arquitetura_projeto/09_workspaces_sandbox_sessoes.md](../arquitetura_projeto/09_workspaces_sandbox_sessoes.md)
- [../arquitetura_projeto/16_autenticacao_seguranca_chaves.md](../arquitetura_projeto/16_autenticacao_seguranca_chaves.md)
- [16_checklist_replicacao_final.md](./16_checklist_replicacao_final.md)
