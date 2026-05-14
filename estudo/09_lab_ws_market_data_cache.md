# 09 - Lab: WS Market Data e Cache Intraday

## Objetivo
Testar fluxo WS de dados de mercado e sua relacao com cache intraday para consistencia de leitura no frontend.

## Pre-requisitos
- `03_setup_free_mode.md` concluido (com fallback REST) ou `04_setup_full_mode.md` para WS completo.
- Acesso a pagina MarketView.

## Tempo estimado
- 45 a 75 min.

## Entregaveis
- Evidencia de status WS e comportamento de fallback.
- Registro de atualizacao de dados no MarketView.

## Resultado esperado
Voce entende quando o produto usa WS realtime e quando degrade para REST sem quebrar experiencia.

## Comandos de execucao
```bash
make up
curl -s http://localhost:8000/ws/v1/market-data/status
```

## O que observar
- Conexao WS autenticada e ativa.
- Atualizacao de ticks no MarketView.
- Comportamento de fallback para REST quando WS indisponivel.

## Como validar sucesso
1. Status WS reporta habilitado (quando configurado).
2. Ticks aparecem no frontend sem travar UI.
3. Sem WS, interface continua funcional por REST.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| WS desabilitado | provider nao configurado | revisar `GINLIX_DATA_URL` e setup full |
| Latencia alta de ticks | problema de rede ou backpressure | observar logs WS e consumo de cliente |
| UI sem atualizacao | subscribe simbolo ausente | revisar hook de inscricao no frontend |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Fallback REST intraday | Both | Both |
| WS realtime robusto | Limitado | Completo |
| Cache intraday rico | Limitado | Completo |

## Referencia cruzada
- [../arquitetura_projeto/12_frontend_arquitetura.md](../arquitetura_projeto/12_frontend_arquitetura.md)
- [../arquitetura_projeto/13_protocolos_tempo_real.md](../arquitetura_projeto/13_protocolos_tempo_real.md)
- [04_setup_full_mode.md](./04_setup_full_mode.md)
