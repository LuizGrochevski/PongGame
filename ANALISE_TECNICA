# Análise técnica — PongGame

## 1) Visão geral
O repositório implementa um jogo Pong minimalista em Java com quatro classes principais:
- `Game`: janela, loop principal, input e renderização.
- `Player`: raquete controlada pelo usuário (setas esquerda/direita).
- `Enemy`: raquete adversária com comportamento automático.
- `Ball`: movimentação da bola, colisões, quique nas paredes e lógica de ponto.

A arquitetura é intencionalmente simples e focada em fundamentos de jogos 2D.

## 2) Conceitos implementados
- **Loop de jogo**: atualização (`tick`) e desenho (`render`) em ciclo contínuo.
- **Taxa de atualização**: `Thread.sleep(1000/60)` para aproximar 60 FPS.
- **Renderização com buffer**: uso de `BufferStrategy` para evitar flicker.
- **Entrada de teclado**: `KeyListener` com estados booleanos (`left/right`).
- **Colisão AABB**: `Rectangle.intersects(...)` para bola e raquetes.
- **Física simplificada**:
  - inversão de `dx` nas laterais,
  - rebatida com novo ângulo aleatório nas raquetes,
  - direção vertical corrigida para seguir o sentido esperado após colisão.
- **IA básica**: inimigo acompanha a posição X da bola.

## 3) Pontos fortes
- Código curto, direto e didático para quem está iniciando.
- Separação em classes por responsabilidade (jogo, entidades e bola).
- Implementa os blocos essenciais de um arcade 2D sem dependências externas.
- Fácil de compilar e executar localmente.

## 4) Limitações
- Não há HUD/placar na interface (apenas `System.out.println`).
- Não existe estado de jogo formal (`menu`, `playing`, `game over`, `pause`).
- Reinício de rodada cria um novo `Game`, sem gerenciador de estado.
- Valores “mágicos” de dimensão/velocidade/ângulo espalhados no código.
- IA do inimigo é extremamente linear e previsível.

## 5) Problemas observados
- **Reset de rodada frágil**: em `Ball.tick()`, ao pontuar, chama `new Game()` sem substituir a instância em execução, o que pode causar inconsistência de estado.
- **Acoplamento global**: uso de atributos estáticos (`Game.player`, `Game.enemy`, `Game.ball`) dificulta testes e escalabilidade.
- **Loop infinito sem controle de ciclo de vida**: não há mecanismo de parar thread/jogo de forma limpa.
- **Ausência de tratamento de foco/input**: dependendo do SO, pode ser necessário clicar na janela para capturar teclado.

## 6) Melhorias simples (baixo esforço)
1. Implementar placar em memória e desenhar na tela.
2. Substituir `new Game()` por método de reset da rodada (reposição de bola/raquetes).
3. Centralizar constantes em um bloco/config para facilitar ajuste fino.
4. Adicionar estado de jogo mínimo (`PLAYING`, `POINT_SCORED`).
5. Melhorar IA com velocidade limitada, reduzindo movimentos instantâneos.
6. Garantir foco inicial do canvas (`requestFocus`) ao iniciar a janela.

## 7) Valor para portfólio
Como projeto de fundamentos, o valor é **bom para nível inicial** por mostrar:
- compreensão do ciclo de jogo,
- colisão e movimentação em 2D,
- organização básica orientada a objetos.

Para aumentar valor de portfólio sem inflar complexidade, basta adicionar: placar em tela, reset correto de rodada e um pequeno refinamento de arquitetura (estado de jogo + menos estáticos).

Projeto útil para demonstrar fundamentos de lógica, atualização por frame, colisão e estruturação básica de sistemas interativos em Java.
