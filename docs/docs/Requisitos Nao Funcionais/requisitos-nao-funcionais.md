---
title: Requisitos Não Funcionais
---


&emsp; Requisitos não funcionais são especificações que descrevem como um sistema deve se comportar em relação a desempenho, segurança, confiabilidade e usabilidade. Eles complementam os requisitos funcionais, garantindo que suas funções sejam executadas de forma eficiente, segura e adequada. 

&emsp;  No contexto do projeto do Amplificador de Sinais, estes requisitos são essenciais para servir como referência para o desenvolvimento do projeto, garantindo que todas as funcionalidades apresentadas ocorram de forma otimizada e que o projeto final apresente resultados de qualidade.

&emsp;  Os requisitos não funcionais a seguir definem as propriedades esperadas do amplificador de sinais mioelétricos, garantindo sua qualidade, desempenho e possibilidade de expansão futura.


## Requisitos Não Funcionais

| Código  | Requisito                                                      |
|---------|----------------------------------------------------------------|
| RNF01   | Captação de sinais mioelétricos com sensibilidade adequada     |
| RNF02   | Amplificação programável com ajuste de ganho                   |
| RNF03   | Saída compatível com microcontroladores (ESP-32)               |
| RNF04   | Filtros analógicos para redução de ruído e interferência       |
| RNF05   | Segurança elétrica e precisão na amplificação                  |
| RNF06   | Integração futura com dashboards de visualização               |

---

### Detalhamento dos Requisitos

####  RNF01 – Captação de sinais mioelétricos com sensibilidade adequada
- O sistema deve captar mesmo os sinais mioelétricos mais fracos provenientes da atividade muscular.
- Os eletrodos utilizados devem garantir baixo ruído e boa aderência à pele.

#### RNF02 – Amplificação programável com ajuste de ganho
- A placa deve permitir o controle do ganho de amplificação via microcontrolador.
- A faixa de ganho deve ser ajustável conforme a aplicação e o tipo de sinal muscular.

#### RNF03 – Saída compatível com microcontroladores (ESP-32)
- A saída do sinal amplificado deve operar com níveis de tensão compatíveis com o do ESP-32 (tensão máxima de 3.3V).
- O sinal deve ser entregue com estabilidade suficiente para leitura analógica confiável.

#### RNF04 – Filtros analógicos para redução de ruído e interferência
- O circuito deve possuir filtros para diminuir interferências da rede elétrica e sinais fracos.

#### RNF05 – Segurança elétrica e precisão na amplificação
- A placa deve operar com segurança, implementando uma proteção contra sobrecorrente e sobretensão.
- A amplificação deve preservar a integridade do sinal original com o mínimo de distorção.

#### RNF06 – Integração futura com dashboards de visualização
- A arquitetura do sistema deve prever a possibilidade de transmissão de dados para sistemas externos.
- É necessário garantir que os dados amplificados possam ser visualizados em tempo real em um dashboard simples.

---

&emsp; Cumprir estes requisitos é essencial para a entrega de um projeto funcional e otimizado, que não apenas atenda as demandas do projeto atual mas que também consiga ser expandido no futuro. 