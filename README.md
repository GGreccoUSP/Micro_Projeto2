# Entrega final - Projeto 2
O projeto teve seu código desenvolvido e testado na IDE MikroC, e seu circuito esquemático realizado na plataforma simulide. Ele implementa, em C para o microcontrolador PIC18F4550, o display (em LCD 16x2) de duas possíveis contagens regressivas (longa e curta), bem como o display da temperatura a partir de um potenciômetro e o acionamento de um LED, caso a temperatura ultrapasse um limiar determinado.

Funcionalidades Principais do sistema:


--Temporizador Regressivo

O sistema possui dois modos de operação:

RB0 (INT0): inicia uma contagem regressiva de 60 segundos;
RB1 (INT1): inicia uma contagem regressiva de 10 segundos.

A contagem é controlada por interrupções e temporizadores internos (Timer0 e Timer1), garantindo precisão temporal sem bloquear a execução do programa principal.


--Monitoramento de Temperatura

A temperatura é adquirida pelo canal analógico AN0 (RA0) através do conversor ADC de 10 bits do PIC.

Características:

Leitura contínua da temperatura;
Conversão sem uso de variáveis do tipo float;
Resolução de 0,1 °C;
Faixa limitada entre 0 °C e 100 °C;
Exibição em tempo real no LCD.


--Controle da Resistência (LED)

Um LED conectado ao pino RC0 simula a resistência de um forno:

Temperatura > 50 °C → LED ligado;
Temperatura ≤ 50 °C → LED desligado.

Por fim, a imagem abaixo mostra o esquemático realizado na plataforma simulide, com o mapeamento de pinos indicado no início do código (src).
<img width="1363" height="854" alt="image" src="https://github.com/user-attachments/assets/49385b36-6e6a-4112-8a6f-3600954c84f9" />
