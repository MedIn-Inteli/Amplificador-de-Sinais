1. OpenEMG – Charles' Labs
Descrição: Projeto educacional que visa a simplicidade na construção de um sensor EMG utilizando componentes acessíveis.

Aplicação da Tecnologia:

Utiliza o amplificador operacional LM324 em configuração diferencial.

Inclui filtros passa-alta e passa-baixa para isolamento de ruídos.

Possui etapa de retificação e suavização para facilitar a leitura por microcontroladores.

Nível de Complexidade: Baixo.

🔧 Reaproveitamento para o Seu Projeto:
Topologia básica do circuito de amplificação analógica:

Ideal como primeiro protótipo ou para compreender a lógica de separação dos estágios (pré-amplificação, filtragem, retificação).

Pode ser usado para testes iniciais com sensores e simulações.

Filtros passa-alta e passa-baixa com componentes discretos:

Você pode replicar as ideias de filtragem analógica para eliminar ruído de linha (60 Hz) e tremores musculares de baixa frequência.

Ótimo ponto de partida antes de usar filtros digitais.

Etapa de retificação e suavização:

Útil para criar saídas compatíveis com entradas analógicas de microcontroladores.

Serve como backup em caso de falha na digitalização direta.

Código e layout em software open source (KiCad):

Reaproveitamento direto no seu fluxo de desenvolvimento com PCB.

Inspiração para traçado de pistas e separação de blocos funcionais.



2. PsyLink – Hackaday
Descrição: Interface neural open source para controle de dispositivos via sinais EMG, com foco em aplicações como jogos e interfaces homem-máquina.

Aplicação da Tecnologia:

Utiliza o amplificador de instrumentação INA128 para amplificação de sinais EMG.

Integra um Arduino Nano 33 BLE Sense para processamento e transmissão dos dados via Bluetooth.

Emprega aprendizado de máquina para interpretação dos sinais musculares.
Hackaday

Nível de Complexidade: Médio a alto.

🔧 Reaproveitamento para o Seu Projeto:
Uso do INA128 como amplificador de instrumentação:

Esse CI é estável, com baixo ruído, ideal para sinais bioelétricos fracos como EMG.

Permite ganho definido por resistor externo (ajustável ou controlado por relés/digitalmente).

Relevante para atingir alta precisão e baixa distorção, conforme requerido.

Integração com Arduino Nano 33 BLE Sense:

Mostra como integrar sensores EMG com microcontroladores modernos com Bluetooth LE e sensores adicionais.

Pode servir como exemplo para transmitir dados EMG sem fio a dispositivos móveis ou PCs médicos.

Treinamento de algoritmos simples de machine learning:

Os sinais captados podem ser armazenados e usados para detecção de padrões (ex: reabilitação, próteses).

Viável em seu projeto se houver a ideia de adicionar interpretação automática no futuro.

Projeto modular (placa + microcontrolador externo):

Você pode replicar esse modelo para tornar sua plataforma reprogramável e atualizável.


3. SHIELD-EKG-EMG – Olimex
Descrição: Shield open source para placas Arduino, permitindo a captura de sinais EMG e ECG com amplificação e filtragem adequadas.

Aplicação da Tecnologia:

Utiliza amplificador de instrumentação seguido por amplificador operacional com ganho ajustável e filtro "Besselworth" de 3ª ordem.

Ganho total configurável, com possibilidade de ajuste via trimpot.

Compatível com diferentes placas de desenvolvimento, como OLIMEXINO e Arduino.

Nível de Complexidade: Médio.

🔧 Reaproveitamento para o Seu Projeto:
Arquitetura completa de hardware biomédico validada:

Inclui proteção de entrada, filtragem de ruído e segurança elétrica — essenciais em aplicações clínicas.

Inspiração direta para replicar no layout da sua PCB.

Ajuste de ganho via trimpot:

Pode ser replicado com potenciômetros digitais ou DACs se desejar ajuste programável.

Filtro Bessel de 3ª ordem:

Filtragem analógica eficaz com mínima distorção de fase — ideal para sinais EMG que precisam preservar forma de onda.

Pode ser adaptado diretamente ao seu circuito.

Compatibilidade com Arduino:

Serve de base para testes rápidos de aquisição de dados antes da versão final embarcada.

Layout da PCB e esquemático open source:

Excelente recurso para entender rastreamento de sinais analógicos sensíveis em placas pequenas.


4. OpenBCI
Descrição: Plataforma open source para aquisição de sinais biopotenciais, incluindo EMG, EEG e ECG, com foco em aplicações de interface cérebro-computador.

Aplicação da Tecnologia:

Utiliza o CI ADS1299 da Texas Instruments, que integra amplificadores de instrumentação e conversores A/D de 24 bits.

Permite ganho ajustável via comandos digitais, oferecendo alta precisão na captura de sinais.

Compatível com software open source para visualização e análise dos dados.
Wikipedia

Nível de Complexidade: Alto.

🔧 Reaproveitamento para o Seu Projeto:
Uso do CI ADS1299 (da Texas Instruments):

Ideal para leitura de sinais EMG/EEG com ganho programável digitalmente.

Possui 8 canais com resolução de 24 bits e front-end biomédico integrado.

Perfeito se o projeto exigir múltiplos canais com configuração por software — atende diretamente seu requisito de ajuste programável de ganho.

Design multicamada de PCB:

Considera blindagem, aterramento adequado e separação de trilhas sensíveis, essencial para evitar interferência em sinais muito fracos.

Você pode estudar esse layout como referência para sua própria placa.

Interface via Bluetooth ou USB:

Possibilidade de se comunicar com computadores e softwares de análise biomédica em tempo real.

Boa ideia para modularizar sua plataforma: modo aquisição local + modo transmissão.

Softwares complementares open source (GUI, drivers, APIs):

Pode reutilizar interfaces para visualização de sinais EMG captados.

Inspiração para construção de painel de controle com ajuste de ganho em tempo real.


5. EMG Armband – GitHub
Descrição: Projeto de uma pulseira EMG que capta sinais musculares para controle de dispositivos, utilizando aprendizado de máquina para interpretação dos dados.

Aplicação da Tecnologia:

Utiliza amplificador de instrumentação INA128 ou INA333 para amplificação dos sinais EMG.

Integra microcontrolador ESP32 para aquisição e processamento dos dados.

Emprega modelos de aprendizado de máquina para reconhecimento de gestos.

Nível de Complexidade: Médio a alto.

🔧 Reaproveitamento para o Seu Projeto:
Formato wearable (pulseira com múltiplos canais EMG):

Oferece inspiração para formato compacto e embutido — útil se pensar em aplicações como controle de próteses ou avaliação muscular portátil.

INA128/INA333 para amplificação diferencial:

São chips de instrumentação populares, com boa relação custo-benefício e desempenho clínico.

Incluem proteção contra offset e bom CMRR (Common Mode Rejection Ratio), crítico em EMG.

Uso de ESP32 como unidade central de aquisição e transmissão:

Processador dual-core com Wi-Fi e BLE integrados.

Se seu projeto incluir conectividade sem fio, essa integração serve de referência prática.

Classificação de sinais via IA (Python + TensorFlow Lite):

Inspiração para futuros aprimoramentos na interpretação de gestos, fadiga ou esforço muscular.

Pode ser implementado como módulo opcional se o foco for clínico ou assistivo.

PCB open source com documentação detalhada:

Facilita replicar partes do hardware (como o front-end analógico) para testes ou integração direta.
