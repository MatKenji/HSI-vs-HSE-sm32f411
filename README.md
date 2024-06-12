# Comparação entre HSI e HSE no STM32F411

## Descrição do Projeto

Este projeto tem como objetivo comparar o desempenho dos osciladores HSI (High-Speed Internal) e HSE (High-Speed External) no microcontrolador STM32F411, medindo o tempo de execução de tarefas. O STM32F411 é um microcontrolador poderoso da STMicroelectronics, amplamente utilizado em aplicações embarcadas. A escolha do oscilador pode impactar significativamente o desempenho do sistema.

## Objetivos

- Entender as diferenças entre os osciladores HSI e HSE no STM32F411.
- Medir o tempo de execução de várias tarefas utilizando HSI e HSE.
- Avaliar o impacto da escolha do oscilador no desempenho do sistema.

## High-Speed Internal (HSI) Oscillator

O HSI é um oscilador interno que opera tipicamente a 16 MHz. Ele é conveniente porque não requer componentes externos, oferecendo simplicidade no design do hardware. No entanto, pode ter variações de frequência devido a fatores como temperatura e tensão de alimentação.

### Vantagens do HSI

- Não necessita de componentes externos.
- Menor custo e simplicidade no design.
- Rápida inicialização.

### Desvantagens do HSI

- Menor precisão em comparação com HSE.
- Pode ser influenciado por variações de temperatura e tensão.

## High-Speed External (HSE) Oscillator

O HSE é um oscilador externo que utiliza um cristal ou ressonador externo. Ele pode operar em frequências mais altas e oferece maior precisão e estabilidade em comparação com o HSI.

### Vantagens do HSE

- Alta precisão e estabilidade.
- Menor variação de frequência com temperatura e tensão.
- Permite frequências de operação mais altas.

### Desvantagens do HSE

- Requer componentes externos (cristal/ressonador).
- Pode aumentar o custo e a complexidade do design.
- Maior tempo de inicialização comparado ao HSI.

## Metodologia de Comparação

1. **Configuração do Hardware**: Utilizar uma placa de desenvolvimento com o STM32F411 configurado para alternar entre HSI e HSE.
2. **Medição de Tempo**: Implementar código para medir o tempo de execução de várias tarefas com ambos os osciladores.
3. **Análise dos Dados**: Comparar os tempos de execução para avaliar o impacto de cada oscilador no desempenho do sistema.

## Resultados Esperados

- **Desempenho**: Espera-se que o HSE ofereça melhor desempenho em termos de tempo de execução devido à sua maior precisão e estabilidade.
