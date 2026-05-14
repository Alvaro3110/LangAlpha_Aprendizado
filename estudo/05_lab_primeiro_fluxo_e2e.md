# 05 - Lab: Primeiro Fluxo E2E

## Objetivo
Executar seu primeiro fluxo ponta a ponta: criar workspace, enviar mensagem, receber SSE e validar persistencia basica.

## Pre-requisitos
- Setup local concluido (`03` ou `04`).
- Backend e frontend acessiveis.

## Tempo estimado
- 45 a 75 min.

## Entregaveis
- Um workspace criado.
- Uma thread com resposta completa.
- Evidencia de stream SSE funcionando.

## Resultado esperado
Voce consegue executar a primeira jornada completa do produto sem bloqueio estrutural.

## Comandos de execucao
```bash
make up

make migrate

curl -s http://localhost:8000/health
```

## O que observar
- Cricao de workspace e thread no frontend.
- Evento de stream chegando de forma incremental.
- Status final da thread em `completed`.

## Como validar sucesso
1. Workspace aparece listado.
2. Thread aparece no historico.
3. Mensagem de resposta completa foi persistida.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Backend nao sobe | variavel/env faltando | revisar `.env` e logs do container |
| SSE nao chega | frontend sem conexao com backend | verificar proxy/URL base |
| Thread fica pendente | workflow interrompido ou erro interno | consultar `/status` e logs de handler |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Criar workspace/thread | Both | Both |
| Receber SSE basico | Both | Both |
| Dados de mercado ricos | Limitado | Completo |

## Referencia cruzada
- [../arquitetura_projeto/05_fluxo_chat_ptc.md](../arquitetura_projeto/05_fluxo_chat_ptc.md)
- [../arquitetura_projeto/13_protocolos_tempo_real.md](../arquitetura_projeto/13_protocolos_tempo_real.md)
- [16_checklist_replicacao_final.md](./16_checklist_replicacao_final.md)
