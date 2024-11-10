# Projeto de Monitoramento de CO2 com Controle de Ventilador

## i) Descrição do Funcionamento e Uso

Este projeto é um sistema de monitoramento de CO2 utilizando o **ESP32** e o sensor **MQ-135**. O sistema é capaz de medir a concentração de CO2 no ambiente e acionar um ventilador quando o valor exceder um determinado limite (500 ppm). Além disso, o valor do CO2 é enviado para um servidor MQTT para monitoramento remoto.

### Funcionamento:
1. O ESP32 se conecta à rede Wi-Fi e ao servidor MQTT.
2. O sensor MQ-135 lê o valor do CO2.
3. O ventilador é acionado automaticamente se o nível de CO2 for superior a 500 ppm.
4. As leituras do sensor e o status do ventilador são publicados no servidor MQTT.

## ii) Software Desenvolvido e Documentação de Código

O software foi desenvolvido em **C++** usando o **Arduino IDE**. A comunicação é realizada via **Wi-Fi** e **MQTT**.

- **Bibliotecas Utilizadas:**
  - `WiFi.h`: Para conectar ao Wi-Fi.
  - `PubSubClient.h`: Para comunicação MQTT.

- **Funções principais:**
  - **setup_wifi()**: Conecta o ESP32 ao Wi-Fi.
  - **reconnect()**: Reconecta ao servidor MQTT.
  - **loop()**: Lê o valor do sensor e aciona o ventilador.

## iii) Descrição do Hardware Utilizado

- **Plataforma de Desenvolvimento:**
  - **ESP32**: Microcontrolador com Wi-Fi e Bluetooth.

- **Sensores:**
  - **MQ-135**: Sensor de CO2 e qualidade do ar.

- **Atuadores:**
  - **Ventilador** controlado via relé.

- **Outros Componentes:**
  - **Fonte de alimentação** para ESP32 e ventilador.

- **Peças Impressas em 3D (opcional):**
  - Suportes para o sensor e ESP32.

## iv) Documentação das Interfaces, Protocolos e Módulos de Comunicação

- **Wi-Fi (TCP/IP):** Usado para conectar o ESP32 à internet.
- **MQTT:** Usado para enviar os dados do sensor e o status do ventilador para o servidor.

**Serviço MQTT utilizado:**
- O servidor MQTT pode ser local ou na nuvem, como **Mosquitto** ou **HiveMQ**.

## v) Comunicação/Controle via Internet (TCP/IP) e Uso do Protocolo MQTT

- O projeto utiliza o **protocolo MQTT** para enviar dados de CO2 e status do ventilador para o servidor. O ESP32 se conecta à internet via **Wi-Fi** e publica os dados nos tópicos MQTT.

---

### Como Reproduzir o Projeto

1. **Conecte o ESP32 à sua rede Wi-Fi.**
2. **Configure um servidor MQTT** (pode ser local ou na nuvem).
3. **Conecte o sensor MQ-135 ao ESP32** e o ventilador ao pino de controle.
4. **Carregue o código no ESP32** utilizando o Arduino IDE.

### Requisitos de Software:

- **Arduino IDE** instalado.
- **Bibliotecas**: WiFi, PubSubClient.

---

## Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).

