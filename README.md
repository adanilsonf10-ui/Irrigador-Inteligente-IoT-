<div align="center">

# 🪴 Irrigador Inteligente IoT
### *Smart Irrigation Hub & Automation System*

[![Licença](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
[![GitHub Status](https://img.shields.io/badge/Status-Ativo%20%26%20Em%20Produ%C3%A7%C3%A3o-brightgreen.svg?style=for-the-badge)](#)
[![Plataforma](https://img.shields.io/badge/Plataforma-Smart%20Life%20%7C%20Tuya%20%7C%20Alexa-blue.svg?style=for-the-badge)](#)
[![Hardware](https://img.shields.io/badge/Hardware-12V%20DC%20%7C%20Bomba%20Dupla-orange.svg?style=for-the-badge)](#)

---

<p align="center">
  <b>Sistema de irrigação automática DIY de alto rendimento para 12 vasos de plantas.</b><br/>
  Projetado para zero desperdício de água, acionamento por inteligência de voz via Alexa, proteção elétrica com refrigeração passiva e arquitetura expansível para Home Assistant / ESP32.
</p>

[📌 Destaques](#-destaques-do-projeto) •
[🛠️ Hardware](#%EF%B8%8F-especifica%C3%A7%C3%B5es-de-hardware) •
[🤖 Automação](#-fluxo-de-automa%C3%A7%C3%A3o-alexa) •
[📐 Diagrama](#-arquitetura-do-sistema-diagrama) •
[🚀 Roadmap](#-roadmap-de-evolu%C3%A7%C3%A3o)

---

</div>

<br/>

## 📌 Destaques do Projeto

<table>
  <tr>
    <td width="50%">
      <h3>💧 Precisão Hidráulica</h3>
      <p>Micro-dosagem direcionada diretamente às raízes através de 12 gotejadores ajustáveis conectados por micro-tubos de 6mm, eliminando o desperdício por evaporação ou escorrimento.</p>
    </td>
    <td width="50%">
      <h3>⚡ Segurança Elétrica</h3>
      <p>Alimentação por fonte chaveada <i>Slim</i> de alumínio com dissipação de calor passiva, seccionada por tomada e chave dedicada para manutenção rápida e segura.</p>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>🗣️ Rotina de Voz e Clima</h3>
      <p>Integração com ecossistema Alexa para leitura prévia da previsão do tempo, notificações em tempo real e avisos sonoros de início e término da rega.</p>
    </td>
    <td width="50%">
      <h3>🛠️ Arquitetura Aberta (DIY)</h3>
      <p>Construído com componentes modulares e de baixo custo, pronto para migração local com microcontrolador ESP32 e integração ao CasaOS (Home Assistant).</p>
    </td>
  </tr>
</table>

<br/>

---

## 🛠️ Especificações de Hardware

| Componente | Categoria | Especificação Técnica | Função no Sistema |
| :--- | :---: | :--- | :--- |
| **Bomba de Água** | Hidráulica | Dupla Diafragma 12V DC / 6A | Sucção de água da caixa d'água e pressurização da rede |
| **Fonte Chaveada** | Elétrica | Slim Alumínio 12V DC / 10A | Conversão 110V/12V com refrigeração passiva reforçada |
| **Relé Wi-Fi** | Automação | Módulo Mini Smart (Smart Life / Tuya) | Controle chaveado da alimentação em alta precisão |
| **Manutenção** | Segurança | Tomada de Segurança + Chave Física | Seccionamento da rede elétrica para ajustes manuais |
| **Rede de Distribuição** | Hidráulica | Micro-tubos 6mm + 12 Gotejadores | Condução da água dosada por vaso |
| **Reservatório** | Reservatório | Caixa d'Água (Linha de Pressão) | Abastecimento contínuo por gravidade |

<br/>

---

## 🤖 Fluxo de Automação Alexa

> [!NOTE]  
> A irrigação ocorre em um ciclo preciso de **60 segundos**, combinando feedback sonoro e notificações no smartphone.

```mermaid
timeline
    title Ciclo de Execução Diária
    09:00 - Checagem do Clima : Leitura da probabilidade de chuva e temperatura local
    09:00 - Notificação por Voz : "Vou molhar as plantas do corredor agora às 9 horas"
    09:00 - Ligando a Água : Relé Wi-Fi aciona a Fonte Slim 12V
    09:01 - Irrigação Ativa : Bomba funciona por exatos 60 segundos nos 12 gotejadores
    09:01 - Confirmação : Relé desliga e Alexa avisa: "Acabei de regar as plantas e desliguei a água"
