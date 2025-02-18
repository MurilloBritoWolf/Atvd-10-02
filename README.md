# README - Atividade Prática com ADC no RP2040 e BitDogLab

## Objetivo
Esta atividade prática tem como objetivo consolidar os conceitos sobre o uso de conversores analógico-digitais (ADC) no RP2040 e explorar as funcionalidades da placa de desenvolvimento BitDogLab.

## Metas de Aprendizado
- Compreender o funcionamento do conversor analógico-digital (ADC) no RP2040.
- Utilizar PWM para controlar a intensidade de dois LEDs RGB com base nos valores do joystick.
- Representar a posição do joystick no display SSD1306 através de um quadrado móvel.
- Aplicar o protocolo de comunicação I2C para integração com o display.

## Descrição do Projeto
O projeto consiste na leitura dos valores analógicos do joystick e sua utilização para controlar LEDs RGB e um display SSD1306:

### Controle dos LEDs RGB
- **LED Azul**: O brilho será ajustado conforme o valor do eixo Y do joystick.
  - Joystick na posição central (2048) -> LED apagado.
  - Joystick para cima (valores menores) ou para baixo (valores maiores) -> brilho aumenta gradualmente.
  - Brilho máximo nos extremos (0 e 4095).
- **LED Vermelho**: Seguirá o mesmo princípio, mas de acordo com o eixo X.
  - Joystick na posição central (2048) -> LED apagado.
  - Joystick para esquerda (valores menores) ou direita (valores maiores) -> brilho aumenta gradualmente.
  - Brilho máximo nos extremos (0 e 4095).
- **Controle por PWM**: O PWM será utilizado para permitir uma variação suave na intensidade luminosa.

### Representação no Display SSD1306
- Um quadrado de **8x8 pixels** será desenhado no display, iniciando centralizado.
- A posição do quadrado será ajustada proporcionalmente às leituras do joystick.
- O protocolo **I2C** será usado para a comunicação com o display.

### Funcionalidades dos Botões
- **Botão do Joystick**:
  - Alterna o estado do **LED Verde** a cada pressionamento.
  - Modifica o estilo da borda do display para indicar o acionamento, alternando entre diferentes estilos.
- **Botão A**:
  - Ativa ou desativa os LEDs controlados por PWM a cada pressionamento.

## Componentes Utilizados
Os seguintes componentes estarão interconectados à placa BitDogLab:
- **LED RGB** (conectado às GPIOs 11, 12 e 13).
- **Botão do Joystick** (GPIO 22).
- **Joystick** (GPIOs 26 e 27 para X e Y).
- **Botão A** (GPIO 5).
- **Display SSD1306** (I2C - GPIO 14 e GPIO 15).

## Requisitos do Projeto
1. **Uso de Interrupções**: As funcionalidades dos botões devem ser implementadas utilizando rotinas de interrupção (IRQ).
2. **Debouncing**: Deve ser implementado tratamento de bouncing dos botões via software.
3. **Utilização do Display 128x64**: Devem ser aplicadas ferramentas gráficas para demonstrar compreensão do funcionamento do display e do protocolo I2C.
4. **Organização do Código**: O código deve ser bem estruturado e comentado para facilitar o entendimento.

## Considerações Finais
A implementação deste projeto permitirá uma compreensão mais aprofundada sobre ADCs, PWM, comunicação I2C e o uso de interrupções no RP2040.
Recomenda-se a documentação adequada do código e testes práticos para validar a funcionalidade de cada componente.

## Link do vídeo no YouTube
Link: https://youtube.com/shorts/12Tzrs7VNaQ?si=S6OzmaytZeqePyj6
