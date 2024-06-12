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

![image](https://github.com/MatKenji/HSI-vs-HSE-sm32f411/assets/169562589/c044afe8-c4da-4752-bf0d-18ea25366d05)

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

- O PLL é utilizado para multiplicar a frequência do oscilador de entrada (HSI ou HSE) para atingir a frequência máxima de operação do microcontrolador. No STM32F411, o PLL pode ser configurado para atingir uma frequência de até 100 MHz.

![image](https://github.com/MatKenji/HSI-vs-HSE-sm32f411/assets/169562589/80f8e1f9-7e41-45c6-8169-3bff7c854ba9)


### Vantagens do PLL

- Permite atingir a frequência máxima de operação.
- Melhora o desempenho do sistema ao aumentar a frequência do clock.

### Desvantagens do PLL

- Maior consumo de energia.
- Configuração mais complexa.

![image](https://github.com/MatKenji/HSI-vs-HSE-sm32f411/assets/169562589/c984aa8a-80d3-4b01-ade6-512f0cbecfbe)


## Metodologia de Comparação

1. **Configuração do Hardware**: Utilizar uma placa de desenvolvimento com o STM32F411 configurado para alternar entre HSI e HSE.
2. **Medição de Tempo**: Implementar código para medir o tempo de execução de várias tarefas com ambos os osciladores.
3. **Análise dos Dados**: Comparar os tempos de execução para avaliar o impacto de cada oscilador no desempenho do sistema.

## Resultados Esperados
| Tarefa   | Tempo de Execução com HSI (ms)| Tempo de Execução com HSE (ms)  |            PLL (ms)             |
|--------  |-------------------------------|-------------------------------- |-------------------------------- |
| Tarefa 1 | 483 248                       | 755 992                         | 3 028 705                       |
| Tarefa 2 | 483 249                       | 755 998                         | 3 028 712                       |
| Tarefa 3 | 483 248                       | 755 999                         | 3 028 713                       |
| Tarefa 4 | 483 249                       | 755 999                         | 3 028 712                       |
| Tarefa 5 | 483 248                       | 755 998                         | 3 028 709                       |

## Análise dos Resultados

Os resultados simulados indicam que o uso do HSE com PLL proporciona um desempenho ligeiramente melhor em termos de tempo de execução das tarefas em comparação com o HSI com PLL. Esta melhoria pode ser atribuída à maior precisão e estabilidade do HSE, resultando em uma operação mais eficiente do microcontrolador.

- **Nota:** Os arquivos de código fornecidos neste repositório foram desenvolvidos usando STM32CubeIDE. Devido a limitações de minha experiência com o STM32CubeIDE, a importação direta do projeto para o Git pode não ter sido feita da maneira mais eficiente ou padronizada. 

