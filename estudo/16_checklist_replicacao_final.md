# 16 - Checklist Final de Replicacao

## Objetivo
Fornecer criterios finais e objetivos para declarar que a replicacao local foi concluida com sucesso.

## Checklist tecnico
- [ ] Stack local sobe (`make up`) sem erro critico.
- [ ] Migracoes aplicadas (`make migrate`).
- [ ] Primeira mensagem de chat concluida com SSE.
- [ ] Reconnect/replay de SSE validado.
- [ ] WS market data validado (ou fallback REST documentado).
- [ ] Um fluxo PTC profundo executado com sucesso.
- [ ] Um fluxo Flash rapido executado com sucesso.
- [ ] Uma automacao criada e disparada.
- [ ] Persistencia de conversa e checkpoint verificada.
- [ ] Execucao de testes base (`make test`, `make test-web`) registrada.

## Evidencias recomendadas
- Capturas de tela da UI (chat, market, automations).
- IDs de thread/workspace usados nos testes.
- Logs relevantes de startup, workflow e execucao final.

## Referencia cruzada
- [05_lab_primeiro_fluxo_e2e.md](./05_lab_primeiro_fluxo_e2e.md)
- [08_lab_sse_reconnect_replay_interrupt.md](./08_lab_sse_reconnect_replay_interrupt.md)
- [09_lab_ws_market_data_cache.md](./09_lab_ws_market_data_cache.md)
- [12_lab_automacoes_cron_price_trigger.md](./12_lab_automacoes_cron_price_trigger.md)
- [../arquitetura_projeto/00_indice.md](../arquitetura_projeto/00_indice.md)
