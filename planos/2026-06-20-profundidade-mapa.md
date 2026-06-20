# Profundidade visual do mapa (Busão to Ride)

**Data:** 2026-06-20
**Status:** implementado (aguardando verificação visual no navegador)

## Objetivo

Dar acabamento e sensação de profundidade ao mapa, que hoje parece "colado" no fundo
(bairros, rotas e elementos na mesma camada). **Sem alterar regras, dados
(cidades/rotas/bilhetes) nem o layout atual**, usando apenas CSS e filtros SVG simples
(`feDropShadow`, gradientes) — nada de bibliotecas externas. Mudanças incrementais.

Tudo em **`index.html`** (bloco `<style>` + funções `rioBackground()` e `renderMap()`).

## Princípios
- Sutil acima de tudo: sombras suaves, baixa opacidade, sem poluição.
- Cores originais preservadas (profundidade vem de sombra/contorno/gradiente).
- Compatível com temas: o mapa muda de cor por jogador via `TH`; efeitos usam sombras neutras.

## Passos
1. **`<defs>` reutilizável** em `renderMap()`: filtros `routeShadow`, `nodeShadow`,
   `labelShadow` e gradiente `nodeFill` (branco→cinza-claro).
2. **Camadas SVG nomeadas**: `lyr-terrain / lyr-water / lyr-relief` no fundo e
   `lyr-routes / lyr-nodes / lyr-labels` em `renderMap`, mantendo a ordem de desenho.
3. **Rotas**: `filter="url(#routeShadow)"` no grupo; remover a sombra-retângulo manual dos
   slots vazios (evita sombra dupla). Cor intacta.
4. **Cidades**: `fill="url(#nodeFill)"` no lugar de `#fff` + `nodeShadow`. Geometria/clique intactos.
5. **Labels**: stroke preto suavizado (~2.5px, opacity ~.45) + `labelShadow`, mantendo legibilidade.
6. **Terreno**: 2–3 gradientes radiais de baixa opacidade sobre a terra + áreas verdes
   translúcidas reaproveitando o array `hills`. Sem `feTurbulence`.

## Arquivos afetados
- `index.html` — `<style>` (`.citylabel`), `rioBackground()`, `renderMap()`.

## Verificação
1. Abrir `index.html` e iniciar partida.
2. Conferir profundidade (rotas/ônibus, nós, labels, terreno).
3. Trocar de jogador (temas) — sombras neutras, nada quebra.
4. Cliques nas rotas idênticos ao atual.
5. Responsivo (`@media max-width:760px`) intacto.
6. Antes/depois: cores e dados inalterados.

## Observações
- Risco baixo: tudo aditivo/visual; nenhuma lógica, dado ou layout alterado.
