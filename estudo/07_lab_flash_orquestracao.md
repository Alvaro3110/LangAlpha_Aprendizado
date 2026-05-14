# 07 - Lab: Flash e Orquestracao Rapida

## Objetivo
Comparar o comportamento do modo Flash com PTC em consultas curtas e verificar quando Flash e a escolha ideal.

## Pre-requisitos
- `05_lab_primeiro_fluxo_e2e.md` concluido.
- Entendimento basico de PTC vs Flash (`01_visao_geral_produto`).
## Tempo estimado
- 40 a 70 min.

## Entregaveis
- Uma execucao Flash registrada.
- Comparativo objetivo Flash vs PTC para caso curto.

## Resultado esperado
Voce sabe decidir rapidamente qual modo usar para cada tipo de pergunta.

## Comandos de execucao
```bash
make up
curl -s http://localhost:8000/health
```

## O que observar
- Tempo de resposta menor no Flash.
- Ausencia de sandbox/MCP.
- Uso de tools leves para lookup e resumo.

## Como validar sucesso
1. Consulta curta retorna rapidamente.
2. Nao ha dependencia de provisionamento de sandbox.
3. Resultado e suficiente para triagem inicial.

## Erros comuns e correcoes
| Erro | Causa provavel | Correcao |
|---|---|---|
| Resultado superficial demais | pergunta exigia processamento profundo | migrar para PTC |
| Falha em anexos multimodais | modelo sem modalidade suportada | trocar modelo/ajustar anexo |
| Perda de contexto | thread nova sem historico relevante | continuar na mesma thread quando necessario |

## Matriz de compatibilidade
| Etapa | Free Mode | Full Mode |
|---|---|---|
| Flash lookup | Both | Both |
| Secretaria/orquestracao basica | Both | Both |
| Dados premium em lookup | Limitado | Completo |

## Referencia cruzada
- [../arquitetura_projeto/06_fluxo_chat_flash.md](../arquitetura_projeto/06_fluxo_chat_flash.md)
- [../arquitetura_projeto/01_visao_geral_produto.md](../arquitetura_projeto/01_visao_geral_produto.md)
- [05_lab_primeiro_fluxo_e2e.md](./05_lab_primeiro_fluxo_e2e.md)
