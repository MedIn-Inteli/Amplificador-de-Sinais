## 1. OpenEMG – Charles' Labs
### Descrição: 
Projeto educacional que visa a simplicidade na construção de um sensor EMG utilizando componentes acessíveis, com documentação clara e ideal para fins didáticos ou prototipagem rápida.

### Aplicação da Tecnologia:
- Utiliza o **amplificador operacional LM324** em configuração diferencial.
- Circuito contém **filtros passa-alta e passa-baixa** para remoção de ruídos (como interferência de 60 Hz).
- Possui **etapa de retificação e suavização** para facilitar a leitura dos sinais por microcontroladores.
- Apresenta o sinal EMG retificado como saída analógica “limpa”, ideal para testes iniciais.

### Nível de Complexidade: Baixo.

### 🔧 Reaproveitamento para o Seu Projeto:

#### ✔️ Topologia básica do circuito de amplificação analógica:
- Divide o processamento em **estágios bem definidos**: pré-amplificação, filtragem, retificação e suavização.
- Circuito analógico simples e eficaz para sinais de baixa amplitude, usando componentes comuns.

➡️ **Aplicação direta:** Pode ser usado como **base para os primeiros protótipos** do seu projeto, ideal para validar a captura de sinais mioelétricos antes da implementação do controle digital de ganho.

#### ✔️ Filtros analógicos com componentes discretos (RC):
- Filtros passa-alta e passa-baixa com resistores e capacitores, ajustados para frequências relevantes ao EMG (10–500 Hz).

➡️ **Aplicação prática:** Esses filtros são úteis para eliminar ruídos como tremores musculares (<10 Hz) e interferência de rede elétrica (60 Hz).
Você pode replicar ou adaptar esses filtros na entrada do seu sistema para **pré-condicionar os sinais antes da digitalização**.

#### ✔️ Etapa de retificação e suavização:
- Converte o sinal EMG de AC para uma forma mais próxima da corrente contínua (DC), facilitando a detecção por microcontroladores que não realizam leitura de sinais bipolares diretamente.

➡️ **Aplicação adaptada:** Útil como backup caso sua leitura A/D apresente ruído ou falha. Também pode ser integrada em modos de operação “simples” ou para debug.

#### ✔️ Código e layout em software open source (KiCad):
- Circuito e layout de PCB disponíveis gratuitamente com documentação clara.

➡️ **Aplicação direta:** O layout serve como referência para **roteamento de trilhas sensíveis**, **aterramento adequado** e separação entre a etapa de amplificação e o restante da placa. Você pode importar o projeto no KiCad e adaptar para o seu design final de PCB.

#### ✔️ Facilidade de prototipagem:
- Projeto ideal para testes rápidos com sensores reais, conectando diretamente ao Arduino ou outras placas.

➡️ **Aplicação prática:** Pode ser usado como bancada de teste para os **eletrodos e medições iniciais de EMG**, validando a performance do hardware antes de avançar para uma arquitetura mais complexa.


## 2. PsyLink – Hackaday
### Descrição:
Interface neural open source para controle de dispositivos via sinais EMG, com foco em aplicações como jogos e interfaces homem-máquina.

### Aplicação da Tecnologia:
- Utiliza o **amplificador de instrumentação INA128** para amplificação de sinais EMG.
- Integra um **Arduino Nano 33 BLE Sense** para processamento e transmissão dos dados via Bluetooth.
- Emprega **aprendizado de máquina** para interpretação dos sinais musculares.
- Projeto modular entre hardware analógico e processamento digital.

### Nível de Complexidade: Médio a alto.

### 🔧 Reaproveitamento para o Seu Projeto:

#### ✔️ Amplificação com INA128:
- O **INA128** oferece alto CMRR (Rejeição de Modo Comum), essencial para lidar com ruídos típicos de sinais mioelétricos.
- Permite **ajuste de ganho via resistor externo** — ideal para adaptar o circuito a diferentes aplicações biomédicas.
- É altamente estável, com **baixo offset de entrada** e **baixo ruído**, características fundamentais para capturar sinais EMG de baixa amplitude.
- Pode ser substituído pelo **INA333** em versões de baixo consumo ou compactas, sem perder desempenho biomédico.

➡️ **Aplicação direta:** Excelente referência para o seu front-end de aquisição, especialmente se desejar implementar controle digital de ganho por resistor programável (usando DACs ou potenciômetros digitais).

#### ✔️ Arquitetura modular:
- A separação clara entre **placa analógica** (amplificador e filtros) e **microcontrolador com BLE** facilita a manutenção, reprogramação e upgrades do sistema.
- Possibilita que você implemente uma **interface padronizada na PCB** para conectar diferentes módulos de aquisição e controle.

➡️ **Aplicação direta:** Reaproveitamento da abordagem modular para tornar sua plataforma escalável e flexível — seja para uso com ESP32, STM32 ou outros microcontroladores.

#### ✔️ Integração com BLE (Bluetooth Low Energy):
- Mostra como a leitura de sinais mioelétricos pode ser transmitida em tempo real via BLE.
- Permite comunicação com apps móveis, softwares médicos ou painéis de monitoramento.

➡️ **Aplicação futura:** Pode ser incorporado ao seu projeto se desejar tornar o dispositivo sem fio ou adicionar um modo de transmissão para visualização remota dos sinais.

#### ✔️ Aprendizado de máquina para classificação:
- Treina modelos simples para identificar gestos ou padrões de ativação muscular a partir dos sinais captados.

➡️ **Aplicação futura:** Essa abordagem pode ser integrada ao seu sistema como módulo de interpretação para reabilitação ou controle de dispositivos assistivos (ex: próteses, exoesqueletos).

#### ✔️ Código e esquemáticos open source:
- Disponíveis no Hackaday.io e GitHub, incluindo layout de PCB, documentação do circuito e firmware.

➡️ **Aplicação direta:** Referência prática para topologia do amplificador, filtragem, conexão com microcontrolador e estrutura de software embarcado.


## 3. SHIELD-EKG-EMG – Olimex
### Descrição:
Shield open source para placas Arduino, permitindo a captura de sinais EMG e ECG com amplificação e filtragem adequadas.

### Aplicação da Tecnologia:
- Utiliza **amplificador de instrumentação** seguido por amplificador operacional com ganho ajustável.
- Emprega **filtro Bessel de 3ª ordem**, preservando a forma de onda dos sinais.
- Compatível com placas como **OLIMEXINO** e **Arduino Uno**, facilitando prototipagem.

### Nível de Complexidade: Médio.

### 🔧 Reaproveitamento para o Seu Projeto:

#### ✔️ Arquitetura de hardware validada para biossinais:
- O circuito possui proteção de entrada, filtragem, e isolamento galvânico, essenciais para segurança em aplicações biomédicas.
- Design robusto e testado por comunidades médicas e educacionais.

➡️ **Aplicação direta:** Você pode adaptar o design como base para garantir segurança elétrica e qualidade de sinal na sua PCB personalizada.

#### ✔️ Ajuste de ganho via trimpot:
- Ganho do amplificador pode ser ajustado manualmente com trimpots.

➡️ **Aplicação adaptada:** Pode ser substituído por **potenciômetros digitais** ou **DACs**, permitindo o ajuste programável de ganho proposto no seu projeto.

#### ✔️ Filtro Bessel de 3ª ordem:
- Filtragem analógica eficaz com **baixa distorção de fase**, ideal para sinais mioelétricos.

➡️ **Aplicação direta:** Pode ser integrado como pré-processamento analógico antes da conversão A/D, melhorando a qualidade do sinal antes de chegar ao microcontrolador.

#### ✔️ Compatibilidade com Arduino:
- Interface simples com microcontroladores Arduino facilita testes e debugging.

➡️ **Aplicação prática:** Pode ser usada para testes preliminares de aquisição antes da integração completa do sistema embarcado.

#### ✔️ Esquemático e layout open source:
- Totalmente documentado com arquivos disponíveis no site da Olimex.

➡️ **Aplicação direta:** Referência útil para roteamento de trilhas analógicas sensíveis em sua PCB, especialmente na separação de blocos (alimentação, amplificação, filtragem).


## 4. OpenBCI
### Descrição:
Plataforma open source de aquisição de sinais biopotenciais (EMG, EEG, ECG), com foco em aplicações de interface cérebro-computador.

### Aplicação da Tecnologia:
- Utiliza o **ADS1299 da Texas Instruments**, que integra amplificadores de instrumentação e conversores A/D de 24 bits.
- Oferece **ganho programável via SPI** com comandos digitais.
- Compatível com software open source para visualização e análise em tempo real.
- Interface com computador via **USB ou Bluetooth**.

### Nível de Complexidade: Alto.

### 🔧 Reaproveitamento para o Seu Projeto:

#### ✔️ Uso do CI ADS1299:
- Circuito integrado específico para biossinais, com **amplificação de instrumentação interna** e **ganho programável digitalmente**.

➡️ **Aplicação direta:** Se sua plataforma exigir múltiplos canais com controle de ganho por software, o ADS1299 é uma solução completa e profissional.

#### ✔️ Conversão A/D de alta resolução:
- Possui resolução de **24 bits**, adequada para detecção de microvariações em sinais mioelétricos.

➡️ **Aplicação relevante:** Garante precisão elevada, útil em ambientes clínicos ou aplicações que exigem alto rigor.

#### ✔️ Layout multicamada e proteção de ruído:
- PCB com separação de trilhas analógicas e digitais, aterramento adequado e blindagem.

➡️ **Aplicação direta:** Excelente referência para seu projeto de layout de PCB, garantindo integridade dos sinais captados.

#### ✔️ Comunicação com computador via USB/Bluetooth:
- Sistema modular de aquisição e envio para software de análise.

➡️ **Aplicação futura:** Base para implementar modo de visualização externa dos sinais ou integração com sistemas de prontuário eletrônico.

#### ✔️ Softwares e APIs open source:
- Interface gráfica (GUI), APIs para Python, processamento em tempo real.

➡️ **Aplicação direta:** Você pode reutilizar ou adaptar essas interfaces para testes e calibração do ganho programável no seu projeto.


## 5. EMG Armband – GitHub
### Descrição:
Projeto de uma pulseira EMG que capta sinais musculares para controle de dispositivos, utilizando aprendizado de máquina para interpretação dos dados.

### Aplicação da Tecnologia:
- Utiliza amplificador de instrumentação **INA128 ou INA333**.
- Integra o **ESP32** como microcontrolador central para aquisição, processamento e comunicação sem fio.
- Emprega **modelos de aprendizado de máquina** (Python/TensorFlow Lite) para identificar gestos musculares.

### Nível de Complexidade: Médio a alto.

### 🔧 Reaproveitamento para o Seu Projeto:

#### ✔️ Amplificação com INA128/INA333:
- Amplificadores diferenciais precisos com **bom CMRR** e **offset muito baixo**, ideais para sinais mioelétricos.
- INA333 tem vantagem em baixo consumo, útil para dispositivos portáteis.

➡️ **Aplicação direta:** Excelente escolha de amplificador para sua plataforma PCB, com possibilidade de ajuste de ganho via resistor externo (ou por chaveamento digital).

#### ✔️ Formato wearable com múltiplos canais:
- Arquitetura orientada a portabilidade e múltiplas leituras simultâneas.

➡️ **Aplicação inspiradora:** Pode ser adaptado para aplicações de reabilitação, próteses, ou sensores vestíveis clínicos.

#### ✔️ Uso do ESP32:
- Microcontrolador poderoso com **Wi-Fi, BLE e dois núcleos**, capaz de fazer aquisição + pré-processamento.

➡️ **Aplicação prática:** Boa alternativa ao Arduino se o seu projeto demandar comunicação sem fio e processamento mais intenso.

#### ✔️ Reconhecimento de padrões com IA:
- Classificação de gestos, esforço ou fadiga com bibliotecas leves embarcadas.

➡️ **Aplicação futura:** Módulo de machine learning pode ser adicionado em versões avançadas para interpretar sinais de forma autônoma.

#### ✔️ PCB open source com documentação:
- Design completo disponível no GitHub, com esquemáticos, layouts e instruções de montagem.

➡️ **Aplicação direta:** Inspiração prática para replicar topologia de amplificação, filtragem e layout em seu próprio projeto PCB.

