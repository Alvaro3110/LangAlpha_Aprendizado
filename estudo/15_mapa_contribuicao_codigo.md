# 15 - Mapa de Contribuicao de Codigo

## Objetivo
Ajudar voce a escolher onde contribuir primeiro com baixo risco e alto ganho de aprendizado.

## Areas de contribuicao por perfil
| Perfil | Primeiras areas sugeridas |
|---|---|
| Backend focado em API | `src/server/app`, `src/server/handlers/chat` |
| Agent engineering | `src/ptc_agent/agent/middleware`, `src/ptc_agent/agent/tools` |
| Dados financeiros | `src/data_client`, `src/tools/market_data` |
| Frontend | `web/src/pages/ChatAgent`, `web/src/pages/MarketView` |
| Qualidade | `tests/unit`, `tests/integration` |

## Estrategia de entrada
1. Comecar por bug pequeno ou melhoria de documentacao tecnica.
2. Escrever/ajustar teste junto com a mudanca.
3. Validar impacto em pelo menos uma camada consumidora.

## Checklist de PR tecnico
- [ ] Mudanca localizada e com escopo claro.
- [ ] Teste adicionado/atualizado.
- [ ] Impacto em API/contrato analisado.
- [ ] Logs/observabilidade adequados.

## Referencia cruzada
- [../arquitetura_projeto/02_mapa_repositorio.md](../arquitetura_projeto/02_mapa_repositorio.md)
- [../arquitetura_projeto/17_testes_operacao_runbook.md](../arquitetura_projeto/17_testes_operacao_runbook.md)
- [17_referencias_internas_do_repo.md](./17_referencias_internas_do_repo.md)
