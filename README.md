# 🛰️ EcoSat Shield - Sistema Inteligente de Prevenção de Enchentes e Deslizamentos

Este repositório contém o código fonte e a documentação do protótipo eletrônico do **EcoSat Shield**, um sistema integrado de monitoramento preventivo que une o conceito de sensoriamento remoto (dados espaciais) e Internet das Coisas (IoT) para salvar vidas e mitigar desastres climáticos.

---

## 📝 Descrição do Projeto

No Brasil, eventos climáticos extremos como enchentes e deslizamentos de terra causam perdas humanas irreparáveis, destruição de moradias e prejuízos econômicos bilionários para os municípios. O impacto é severamente agravado em comunidades periféricas e áreas com infraestrutura fragilizada que carecem de monitoramento em tempo real.

O **EcoSat Shield** propõe uma abordagem preventiva: em vez de apenas reagir ao desastre, o sistema analisa dados ambientais críticos para antecipar o risco. O protótipo desenvolvido em ambiente de simulação representa a camada física (Edge Computing) do projeto, coletando dados locais que, em um cenário real, seriam cruzados via nuvem com modelos de Inteligência Artificial e dados de constelações de satélites (como NASA, INPE e Copernicus).

---

## 🎯 Objetivo da Solução

O objetivo principal deste projeto é mapear riscos ambientais em tempo real e fornecer respostas automáticas visuais e sonoras antes que os desastres aconteçam. O sistema visa:
* Monitorar continuamente o nível de rios e córregos urbanos.
* Simular a detecção de saturação de água no solo em encostas (dados comumente validados por sensoriamento remoto de satélites).
* Alertar de forma imediata e visual a população local e os órgãos de Defesa Civil através de um sistema de triagem por cores (semáforo de risco) e alarmes sonoros em caso de evacuação iminente.

---

## 🛠️ Componentes Utilizados

Para a construção e simulação deste circuito, foram selecionados os seguintes componentes no simulador (Wokwi/Tinkercad):

* **1x Placa Microcontroladora:** Arduino Uno R3 (Cérebro do processamento local).
* **1x Sensor de Distância Ultrassônico (HC-SR04):** Utilizado para medir, por meio de ondas sonoras, a distância da lâmina d'água e determinar o nível do rio.
* **1x Potenciômetro Linear (10kΩ):** Utilizado para simular a entrada de dados analógicos de umidade e saturação do solo (representando as leituras de sensoriamento remoto por satélite).
* **3x LEDs (Verde, Amarelo e Vermelho):** Indicadores visuais do status de risco atual da região monitorada.
* **3x Resistores (220 Ω):** Componentes de proteção para limitar a corrente elétrica nos LEDs.
* **1x Buzzer Piezoelétrico:** Emissor sonoro para alertas de emergência e evacuação (Alarme).
* **Protoboard e Fios de Conexão (Jumpers):** Para a estruturação e interconexão do circuito.

---

## 🔌 Estrutura do Circuito (Mapeamento de Pinos)

O circuito foi interconectado utilizando a seguinte padronização de pinos no Arduino:

* **Sensor Ultrassônico HC-SR04:**
  * `VCC` -> Conectado ao pino **5V**
  * `GND` -> Conectado ao pino **GND**
  * `Trig` (Gatilho) -> Conectado ao **Pino Digital 2**
  * `Echo` (Resposta) -> Conectado ao **Pino Digital 3**
* **Potenciômetro:**
  * Terminal Esquerdo -> Conectado ao pino **GND**
  * Terminal Direito -> Conectado ao pino **5V**
  * Terminal Central (Sinal) -> Conectado ao **Pino Analógico A0**
* **Indicadores Visuais (LEDs):**
  * LED Verde (Seguro) -> Conectado ao **Pino Digital 4** (via resistor de 220 Ω)
  * LED Amarelo (Atenção) -> Conectado ao **Pino Digital 5** (via resistor de 220 Ω)
  * LED Vermelho (Alerta) -> Conectado ao **Pino Digital 6** (via resistor de 220 Ω)
* **Indicador Sonoro:**
  * Buzzer (+) -> Conectado ao **Pino Digital 7**
  * Buzzer (-) -> Conectado ao pino **GND**

---

## ⚙️ Explicação do Funcionamento

O algoritmo implementado no Arduino realiza a leitura cíclica dos sensores e aplica uma lógica de decisão baseada em três estados de criticidade:

1. **Estado Verde (Operação Segura):** O rio encontra-se em nível normal (distância do sensor alta) e o solo está seco/estável. O LED verde permanece aceso e nenhuma ação sonora é emitida.
2. **Estado Amarelo (Atenção):** Identificado quando o nível do rio começa a subir **OU** quando a saturação do solo atinge níveis moderados (simulado pelo potenciômetro). O LED amarelo acende, indicando que a Defesa Civil deve entrar em prontidão e monitorar de perto a área.
3. **Estado Vermelho (Alerta Máximo / Evacuação):** Ativado quando o nível do rio atinge o limite crítico de transbordamento **OU** quando o solo está completamente encharcado (alto risco de deslizamento de terra). O LED vermelho acende e o Buzzer dispara um sinal sonoro intermitente contínuo, orientando a evacuação imediata da população através das rotas de fuga.

Todas as leituras de distância (em centímetros) e umidade (em porcentagem calculada de 0 a 100%) são transmitidas continuamente via comunicação serial para fins de auditoria e monitoramento de dados.

---

## 🚀 Instruções de Execução

Para testar e rodar o projeto no simulador, siga o passo a passo abaixo:

1. Acesse o ambiente do simulador utilizado (como o **Wokwi** ou o **Tinkercad**).
2. Monte o circuito físico respeitando rigorosamente as conexões descritas na seção **Estrutura do Circuito**.
3. Crie um arquivo de código, copie o script disponível na seção de Código Fonte abaixo e cole no editor do simulador.
4. Clique em **Iniciar Simulação**.
5. Abra a janela do **Monitor Serial** (Serial Monitor) para acompanhar os dados textuais gerados.
6. **Interação para testes:**
   * Clique sobre o Sensor Ultrassônico e altere o controle deslizante de distância. Aproxime o obstáculo para simular a cheia do rio.
   * Gire o Potenciômetro para a direita para simular o aumento de umidade acumulada na encosta de terra.
   * Observe a transição automática dos LEDs e o acionamento do Buzzer quando os limites forem ultrapassados.

---NOME DO INTEGRANTE: ENZO LEME GOMES RM : 572148
---LINK DO TINKERCARD:https://www.tinkercad.com/things/4Li7XwwTO6D/editel?sharecode=cIr--7wW8voahSK9GSGisyA6YEt1dO6PExUVShPkcCA

## 💻 Código Fonte do Projeto

O código abaixo deve ser salvo com a extensão `.ino` (ex: `ecosat_shield.ino`) para execução na IDE do Arduino ou nos simuladores:

```cpp
/**
 * EcoSat Shield - Sistema de Prevenção de Enchentes e Deslizamentos
 * Código Fonte do Protótipo IoT
 */

// Definição dos pinos dos sensores
const int PIN_TRIG = 2;
const int PIN_ECHO = 3;
const int PIN_POT_SOLO = A0;

// Definição dos pinos de saída (Atuadores e Indicadores)
const int LED_VERDE = 4;
const int LED_AMARELO = 5;
const int LED_VERMELHO = 6;
const int BUZZER = 7;

void setup() {
  // Inicialização da comunicação serial
  Serial.begin(9600);
  
  // Configuração dos modos dos pinos
  pinMode(PIN_TRIG, OUTPUT);
  pinMode(PIN_ECHO, INPUT);
  
  pinMode(LED_VERDE, OUTPUT);
  pinMode(LED_AMARELO, OUTPUT);
  pinMode(LED_VERMELHO, OUTPUT);
  pinMode(BUZZER, OUTPUT);
}

void loop() {
  // 1. Leitura do Sensor Ultrassônico (Nível do Rio)
  digitalWrite(PIN_TRIG, LOW);
  delayMicroseconds(2);
  digitalWrite(PIN_TRIG, HIGH);
  delayMicroseconds(10);
  digitalWrite(PIN_TRIG, LOW);
  
  long duracao = pulseIn(PIN_ECHO, HIGH);
  // Cálculo matemático para converter o tempo de resposta em centímetros
  int distanciaRio = duracao * 0.034 / 2; 
  
  // 2. Leitura do Potenciômetro (Saturação do Solo / Dados de Satélite)
  int leituraSolo = analogRead(PIN_POT_SOLO);
  // Conversão da leitura analógica (0 a 1023) para escala percentual (0 a 100%)
  int umidadeSolo = map(leituraSolo, 0, 1023, 0, 100);

  // Exibição dos dados coletados no Monitor Serial para diagnóstico
  Serial.print("Nivel do Rio (Distancia): ");
  Serial.print(distanciaRio);
  Serial.print(" cm | Umidade do Solo: ");
  Serial.print(umidadeSolo);
  Serial.println("%");

  // 3. Máquina de Estados da Lógica de Risco (EcoSat Shield)
  
  // CONDICIONAL VERMELHA: Rio transbordando (distância menor que 10cm) OU Solo saturado (> 80%)
  if (distanciaRio < 10 || umidadeSolo > 80) {
    digitalWrite(LED_VERDE, LOW);
    digitalWrite(LED_AMARELO, LOW);
    digitalWrite(LED_VERMELHO, HIGH);
    
    // Alarme sonoro intermitente de emergência
    tone(BUZZER, 1000); 
    delay(150);
    noTone(BUZZER);
    delay(150);
    
    Serial.println("[ALERTA CRÍTICO] Risco iminente constatado. Evacue a área!");
  } 
  // CONDICIONAL AMARELA: Nível de atenção mista de sensores
  else if ((distanciaRio >= 10 && distanciaRio <= 25) || (umidadeSolo > 50 && umidadeSolo <= 80)) {
    digitalWrite(LED_VERDE, LOW);
    digitalWrite(LED_AMARELO, HIGH);
    digitalWrite(LED_VERMELHO, LOW);
    noTone(BUZZER);
    
    Serial.println("[ATENÇÃO] Alteração nos índices ambientais. Monitorando anomalias.");
    delay(300);
  } 
  // CONDICIONAL VERDE: Ambiente estável e seguro
  else {
    digitalWrite(LED_VERDE, HIGH);
    digitalWrite(LED_AMARELO, LOW);
    digitalWrite(LED_VERMELHO, LOW);
    noTone(BUZZER);
    
    Serial.println("[STATUS] Sistema operando em condições normais de segurança.");
    delay(300);
  }
}
