# PongGame

## Descrição breve
Projeto simples de Pong em Java, com renderização 2D usando AWT/Swing, controle do jogador por teclado e um oponente automatizado.

## Objetivo de estudo
Praticar fundamentos de desenvolvimento de jogos com Java:
- loop de jogo (`tick` + `render`),
- entrada por teclado,
- movimentação em tempo real,
- colisão básica com `Rectangle`.

## Conceitos aplicados
- Game loop com atualização em ~60 FPS.
- Double/triple buffering com `BufferStrategy`.
- Detecção de colisão entre bola e raquetes.
- IA simples para seguir a bola no eixo X.
- Uso de trigonometria (`sin`/`cos`) para direção da bola.

## Tecnologias
- Java
- AWT (`Canvas`, `Graphics`, `Color`, `Rectangle`)
- Swing (`JFrame`)

## Como rodar
### Pré-requisitos
- JDK 8+ instalado

### Execução
```bash
javac -d bin src/*.java
java -cp bin Game
```

## Limitações
- Não há placar persistente na tela.
- Reinício de ponto é feito por `new Game()` dentro da lógica da bola.
- Não existe menu, pausa ou níveis de dificuldade.
- Estrutura em classes estáticas globais (`Game.player`, `Game.enemy`, `Game.ball`), adequada para estudo, mas pouco escalável.

## Aprendizados
Este projeto é útil para consolidar lógica de atualização/renderização, input e colisão em jogos 2D. Também evidencia pontos importantes de arquitetura para evolução futura (estado do jogo, reinício de rodada, desacoplamento entre entidades e motor principal).
