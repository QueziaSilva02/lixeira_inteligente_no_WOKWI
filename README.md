# Lixeira_inteligente_no_WOKWI

# 🗑️ EcoBin IoT — Lixeira Inteligente para Smart Cities

O **EcoBin IoT** é uma solução de Internet das Coisas (IoT) desenvolvida para otimizar a logística de gestão e recolha de resíduos sólidos urbanos no contexto das Cidades Inteligentes (Smart Cities)[cite: 3]. O sistema afere continuamente o nível de preenchimento do recipiente, exibindo a ocupação localmente via LEDs e enviando os dados em tempo real para a plataforma em nuvem **ThingSpeak**[cite: 3].

---

## 👨‍💻 Autores & Instituição

**Instituição:** Escola SENAI "A. Jacob Lafer" (Santo André/SP)[cite: 1, 2]
**Curso:** Técnico em Desenvolvimento de Sistemas — 3º Semestre / 2026[cite: 2]
**Disciplina:** Fundamentos de IoT[cite: 2]
**Professor Orientador:** Denani[cite: 2]
**Integrantes do Grupo:**
  * Quezia da Paz Brito Silva[cite: 1, 2]
  * Othávio Kauan Gomes Corrêa[cite: 1, 2]
  * Arthur Ribeiro de Azevedo[cite: 1, 2]
  * Ana Paula Lima Ferreira[cite: 1, 2]

---

## 📌 Problema e Solução

**Problema:** A recolha tradicional de lixo utiliza rotas fixas e horários rígidos[cite: 5]. Isso causa deslocamentos ineficientes de caminhões para recolher lixeiras vazias ou resulta no transbordo de recipientes sobrecarregados[cite: 5].
**Solução:** O **EcoBin** utiliza um sensor ultrassônico instalado na tampa da lixeira para medir a distância até aos resíduos e calcular a percentagem de ocupação[cite: 6]. As métricas são enviadas via Wi-Fi/HTTP para a nuvem, permitindo o planeamento de rotas de recolha dinâmicas baseadas em dados reais[cite: 3, 6].

---

## 🛠️ Tecnologias e Componentes

### **Hardware & Componentes**[cite: 8, 9]
**Placa ESP32 (NodeMCU):** Processamento embarcado e conectividade Wi-Fi[cite: 7, 8].
**Sensor Ultrassônico HC-SR04:** Medição de distância/nível de resíduos[cite: 7, 8].
**LEDs (Verde, Amarelo, Vermelho):** Sinalização visual local[cite: 6, 7, 8, 9].
**Resistores de 220Ω (x3):** Proteção dos LEDs[cite: 9, 10].
**Protoboard & Jumpers:** Conexão e montagem do circuito.
**Fonte de Alimentação 5V 2A / Plug P4:** Alimentação do sistema[cite: 9].

### **Software & Nuvem**[cite: 3, 7]
**Linguagem:** C / C++ (Arduino IDE)[cite: 10]
**Plataforma Cloud:** ThingSpeak (Telemetria e gráficos em tempo real)[cite: 7, 16]
**Simulador:** Wokwi Simulator[cite: 3, 10]

---

## 🚥 Lógica dos LEDs de Sinalização

O estado de ocupação é indicado visualmente pelos LEDs na lixeira[cite: 6]:
🟢 **LED Verde (<= 50%):** Nível de ocupação normal / Capacidade adequada[cite: 6, 14].
🟡 **LED Amarelo (51% a 80%):** Nível de atenção / Alerta preventivo[cite: 6, 14, 15].
🔴 **LED Vermelho (> 80%):** Nível crítico / Lixeira cheia (necessidade imediata de recolha)[cite: 6, 15].

---

## 🔌 Esquema de Ligação (Pinout)

**Sensor HC-SR04:**
  * VCC ➔ **5V** do ESP32[cite: 10]
  * GND ➔ **GND** do ESP32[cite: 10]
  * TRIG ➔ **GPIO 5**[cite: 10]
  * ECHO ➔ **GPIO 18**[cite: 10]
**LEDs Indicadores (Anodo com Resistor 220Ω):**
  * LED Verde ➔ **GPIO 2**[cite: 10]
  * LED Amarelo ➔ **GPIO 4**[cite: 10]
  * LED Vermelho ➔ **GPIO 15**[cite: 10]
  * *Catodos de todos os LEDs ligados ao **GND***[cite: 10].

🔗 **Link do Circuito Simulado no Wokwi:** [Ver Simulação no Wokwi](https://wokwi.com/projects/476143281070437377)[cite: 10]

---

## 💻 Código-Fonte (C/C++)
