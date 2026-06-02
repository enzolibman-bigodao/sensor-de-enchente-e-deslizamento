
# 🛰️ EcoSat Shield - Sistema Inteligente de Prevenção de Enchentes e Deslizamentos

> **Status do Projeto:** 🚀 Protótipo Funcional (Simulado)

O **EcoSat Shield** é uma solução tecnológica desenhada para mitigar os impactos de desastres naturais (enchentes e deslizamentos de terra) no Brasil. O sistema combina o poder do sensoriamento remoto (dados de satélites como NASA, INPE e Copernicus) com Inteligência Artificial e monitoramento IoT local para proteger populações vulneráveis e auxiliar a gestão pública na tomada de decisões rápidas.

Este repositório contém o protótipo eletrônico do sistema, desenvolvido utilizando a plataforma **Arduino** em ambiente de simulação.

---

## 📌 Problema Real

No Brasil, os eventos climáticos extremos causam anualmente perdas de vidas, destruição de moradias e prejuízos milionários. A falta de monitoramento em tempo real afeta principalmente comunidades periféricas e cidades com infraestrutura fragilizada. O EcoSat Shield atua na **antecipação do risco**, transformando dados ambientais em alertas salvadores de vidas.

---

## ⚙️ Como o Protótipo Funciona

Como não é possível conectar o simulador diretamente a um satélite em tempo real, este protótipo utiliza **componentes eletrônicos para simular as variáveis da natureza e do espaço**:

* **Nível do Rio (Sensor Ultrassônico HC-SR04):** Mede a proximidade da água. Conforme a água sobe, a distância diminui, indicando risco de enchente.
* **Saturação do Solo / Dados de Satélite (Potenciômetro):** Simula a análise de umidade do solo enviada por satélites de sensoriamento remoto. Níveis altos indicam risco de deslizamento em encostas.
* **Interface de Alerta (LEDs e Buzzer):** * 🟢 **Verde (Seguro):** Condições normais.
    * 🟡 **Amarelo (Atenção):** Elevação de rios ou solo úmido.
    * 🔴 **Vermelho (Alerta Máximo):** Risco iminente de desastre. O alarme sonoro (Buzzer) é acionado para evacuação.

---

## 🛠️ Tecnologias e Componentes

### Hardware (Simulado)
* 1x Arduino Uno
* 1x Sensor de Distância Ultrassônico (HC-SR04)
* 1x Potenciômetro (Simulador de saturação de solo)
* 3x LEDs (Verde, Amarelo e Vermelho)
* 3x Resistores de 220 Ω
* 1x Buzzer Piezoelétrico
* Protoboard e Jumpers

### Software e Ferramentas
* **Ambiente de Simulação:** [Wokwi](https://wokwi.com/) / [Tinkercad](https://www.tinkercad.com/)
* **Linguagem:** C++ (Arduino IDE)

---

## 🚀 Como Executar o Projeto

Você pode testar este projeto diretamente no seu navegador através do simulador de sua preferência:

1.  Acesse o [Wokwi](https://wokwi.com/) ou [Tinkercad](https://www.tinkercad.com/).
2.  Monte o circuito seguindo a lógica dos pinos definida no código (ou utilize o link do projeto simulado, caso possua).
3.  Copie o código fonte disponível no arquivo `src/ecosat_shield.ino` deste repositório e cole na aba de programação do simulador.
4.  Inicie a simulação.
5.  **Para testar:**
    * Altere a distância no Sensor Ultrassônico para simular a subida do rio.
    * Gire o Potenciômetro para simular o aumento da umidade do solo detectada pelo satélite.
    * Abra o **Monitor Serial** para acompanhar os logs em tempo real.

---

## 🌍 Conexão com os Objetivos de Desenvolvimento Sustentável (ODS)

Este projeto está diretamente alinhado com a Agenda 2030 da ONU:
* **ODS 9:** Indústria, Inovação e Infraestrutura.
* **ODS 11:** Cidades e Comunidades Sustentáveis.
* **ODS 13:** Ação Contra a Mudança Global do Clima.

---

## 👥 Integrantes do Grupo

* [Seu Nome] - RM: XXXXX
* [Nome do Colega] - RM: XXXXX
* [Nome do Colega] - RM: XXXXX
