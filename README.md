# 🚌 Busão to Ride — edição Rio de Janeiro

Um MVP carioca do *Ticket to Ride*: em vez de trens cruzando os EUA, **ônibus cruzando os bairros do Rio**.

## Como jogar
Abra o `index.html` com duplo clique (ou no painel de preview). É **2 jogadores no mesmo PC** (hot-seat), revezando a vez.

Na sua vez, escolha **UMA** ação:
1. **Comprar 2 cartas de ônibus** — clique nas cartas do mercado (5 visíveis) ou no MONTE. Um 🚌 curinga visível conta como as 2 cartas do turno.
2. **Conquistar uma rota** — clique numa rota no mapa e pague com cartas da cor dela (rotas **cinza** aceitam qualquer cor; 🚌 curinga vale qualquer cor). Você ganha pontos na hora.
3. **Comprar bilhetes de destino** — pega 3, guarda pelo menos 1.

### Pontuação das rotas (pelo tamanho)
1→1 · 2→2 · 3→4 · 4→7 · 5→10 · 6→15 pontos.

### Bilhetes de destino
Ligar as duas pontas com suas rotas = **+pontos**. Não ligar = **−pontos** no fim.

### Fim de jogo
Quando um jogador fica com ≤2 ônibus, todos jogam mais uma vez. Soma-se rotas + bilhetes. Maior pontuação vence.

## O que já tem (MVP)
- Mapa do Rio em SVG com 20 bairros e 33 rotas coloridas
- Baralho de cartas (8 cores + curinga), mercado de 5 cartas e monte
- Conquista de rotas com escolha de pagamento
- Bilhetes de destino com verificação de conexão (busca em grafo)
- Placar, diário de bordo e tela de resultado

## Próximos passos (ideias)
- 🤖 Oponente por IA pra jogar sozinho
- 🛣️ Bônus de "maior linha de ônibus" (rota mais longa)
- 🎨 Arte de verdade: fundo com a silhueta do Rio, Pão de Açúcar, Cristo
- 🧱 Rotas duplas (duas faixas entre os mesmos bairros)
- 📱 Layout mobile / multiplayer online
- 🚍 Tema: nomes reais de linhas de ônibus do Rio nas cartas
