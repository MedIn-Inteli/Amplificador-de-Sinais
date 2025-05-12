# Arquitetura Inicial

A arquitetura do projeto, consiste em um forma de documentar e demonstrar quais são as técnicas e padrões utilizados para desenvolver uma aplicação, a proposta de arquitetura pode ser utilizada como planejamento do que deve ser desenvolvido para garantir o funcionamento do projeto, levando em consideração diversos fatores como regras de negócios e restrições técnicas, uma vez que ela descreve todos os componentes que fazem parte do sistema.

## Diagrama de arquitetura

<p style={{textAlign: 'center'}}>Figura 1 - Diagrama de Blocos da Arquitetura</p>

<div style={{textAlign: 'center'}}>

![Descrição da Imagem](/img/Arquitetura/diagrama_arquitetura_inicial.png)

</div>

<p style={{textAlign: 'center'}}>Fonte: Elaboração própria (2025)</p>

## Descrição da arquitetura

- **IN:** Representa o sinal de entrada do circuito
- **OUT:** Representa o sinal de saída do circuito

#### Circuito de captura e limpeza de sinal

- **Entrada do sinal mioelétrico original:** O sinal mioelétrico de entrada. Neste momento o sinal está inalterado e exatamente igual ao momento em que ele foi captado.

- **Circuito de filtros do sinal mioelétrico original:** Este circuito tem a função de filtrar o sinal original, uma vez que, ao captar o sinal, podem ocorrer interferências que geram ruídos no sinal, os filtros possuem a capacidade de remover, ou ao menos diminuir, o ruído do sinal, visando enviar um sinal limpo e claro.

#### Circuito de amplificação do sinal

- **Circuito de pré amplificação de baixos ruídos:** Este circuito é responsável por amplificar o sinal mioelétrico captado inicialmente, garantindo que o ganho seja suficiente para posterior processamento, enquanto minimiza a introdução de ruídos adicionais. Ele é projetado para preservar a integridade do sinal original.

- **Circuito de amplificação programável do sinal:** Este circuito permite ajustar dinamicamente o fator de amplificação do sinal, de acordo com as necessidades específicas da aplicação. A variação do ganho é controlada pelo microcontrolador, permitindo que o usuário altere o fator de amplificação conforme sua necessidade, através do firmware gravado no microcontrolador.

- **Circuito de filtragem Off Set/DC:** Este circuito remove componentes de corrente contínua (DC) ou offsets indesejados presentes no sinal amplificado. Ele garante que o sinal final esteja em um nível de referência adequado, evitando erros ou a transmissão inadequada de sinais para as próximas etapas.

#### Circuito de saída e transmissão do sinal

- **Circuito de filtros do sinal mioelétrico amplificado:** Este circuito tem a função de filtrar o sinal mioelétrico amplificado, uma vez que, ao alterar o sinal, podem ocorrer interferências que geram ruídos no sinal, os filtros possuem a capacidade de remover, ou ao menos diminuir, o ruído do sinal, visando torná-lo limpo e claro.

- **Saída do sinal mioelétrico amplificado:** Esta etapa representa o ponto final do circuito, onde o sinal mioelétrico amplificado e filtrado é disponibilizado para ser utilizado em aplicações externas, como dispositivos de análise, sistemas de controle ou interfaces de comunicação, assim como o sinal amplificado é passado para o microcontrolador.

#### Microcontrolador (ESP-32)

- **Recebimento do sinal mioelétrico original:** O microcontrolador recebe o sinal mioelétrico captado diretamente do circuito de entrada, permitindo que ele seja processado ou armazenado conforme necessário.

- **Transmissão de dados via WiFi ou Bluetooth:** O ESP-32 possui compatibilidade nativa para transmissão de dados via WiFi e Bluetooth, permitindo que o usuário transmita dados sem a necessidade de um sistema cabeado. Garantindo maior compatibilidade e flexibilidade para o sistema, facilitando o acesso aos dados.

- **Determinação do fator de amplificação do sinal:** Através do firmware, o microcontrolador tem a capacidade de ajustar dinamicamente o fator de amplificação do sinal. Isso permite personalizar o ganho do sinal de acordo com as necessidades específicas da aplicação.

- **Processamento do sinal, conforme firmware do usuário:** O ESP-32 realiza o processamento do sinal mioelétrico de acordo com o firmware programado pelo usuário. Isso pode incluir análises, transformações ou outras operações específicas para a aplicação.

- **Recebimento do sinal mioelétrico amplificado:** Após o sinal ser amplificado e filtrado, o microcontrolador recebe o sinal final para realizar etapas adicionais de processamento ou para preparar sua transmissão para outros sistemas.

## Conclusão

Sendo assim, é possível concluir que a proposta de arquitetura inicial do sistema, junto ao diagrama que a representa, é essencial para definir o objetivo do projeto, além de apresentar em um contexto macro como o sistema será divido e como cada uma dessas partes se conecta e se comunica.
