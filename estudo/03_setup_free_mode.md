# 03 - Setup Free Mode

## Objetivo
Levantar um ambiente minimo funcional com menor dependencia de credenciais pagas, mantendo capacidade de estudar fluxos principais.

## Pre-requisitos
- Docker e Docker Compose.
- Python 3.12+, uv, Node e pnpm.
- `.env` inicial criado.

## Tempo estimado
- 45 a 90 min.

## Entregaveis
- Backend e frontend operando localmente.
- Health check e primeira chamada de API funcionando.

## Resultado esperado
Voce consegue usar o sistema com dados gratuitos e executar os primeiros labs.

## Passos
1. Copiar `.env.example` para `.env`.
2. Configurar apenas variaveis obrigatorias locais.
3. Subir stack:
```bash
make up
```
4. Rodar migracoes:
```bash
make migrate
```
5. Validar saude:
```bash
curl -s http://localhost:8000/health
```

## Limites esperados no Free Mode
- Menor cobertura de dados intraday e macro.
- Possiveis limites/faltas em provedores sem API key.
- Alguns labs em modo "Both/Full" podem ter comportamento reduzido.

## Referencia cruzada
- [04_setup_full_mode.md](./04_setup_full_mode.md)
- [05_lab_primeiro_fluxo_e2e.md](./05_lab_primeiro_fluxo_e2e.md)
- [../arquitetura_projeto/10_dados_financeiros_provider_chain.md](../arquitetura_projeto/10_dados_financeiros_provider_chain.md)
