# 04 - Setup Full Mode

## Objetivo
Configurar ambiente completo para reproduzir recursos avancados: dados em tempo real, fallback premium e fluxos de automacao com maior fidelidade.

## Pre-requisitos
- Todos os requisitos do Free Mode.
- Credenciais necessarias para provedores alvo (ex.: FMP, ginlix-data, OAuth/BYOK).

## Tempo estimado
- 90 a 180 min.

## Entregaveis
- Ambiente com provedores completos ativos.
- WS de mercado e trilha de dados enriquecida funcionando.

## Resultado esperado
Voce consegue reproduzir os cenarios mais proximos de producao no contexto do projeto.

## Passos
1. Preencher no `.env` as credenciais do Full Mode.
2. Ajustar `config.yaml`/`agent_config.yaml` conforme providers desejados.
3. Subir stack e migrar:
```bash
make up
make migrate
```
4. Validar endpoints centrais:
```bash
curl -s http://localhost:8000/health
curl -s http://localhost:8000/ws/v1/market-data/status
```

## Sinais de sucesso
- WS market data habilitado.
- Fallback chain com provider prioritario ativo.
- Fluxos PTC com ferramentas de dados mais ricas.

## Referencia cruzada
- [03_setup_free_mode.md](./03_setup_free_mode.md)
- [09_lab_ws_market_data_cache.md](./09_lab_ws_market_data_cache.md)
- [../arquitetura_projeto/11_mcp_servers_e_tools_nativos.md](../arquitetura_projeto/11_mcp_servers_e_tools_nativos.md)
