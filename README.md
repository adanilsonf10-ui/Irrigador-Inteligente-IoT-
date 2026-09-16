<div align="center">

# 🪴 Irrigador Inteligente IoT
### *Smart Irrigation Hub & Automation System*

[![Licença](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Ativo%20%26%20Em%20Produ%C3%A7%C3%A3o-brightgreen.svg?style=for-the-badge)](#)
[![Plataforma](https://img.shields.io/badge/Plataforma-Smart%20Life%20%7C%20Tuya%20%7C%20Alexa-blue.svg?style=for-the-badge)](#)
[![Hardware](https://img.shields.io/badge/Hardware-12V%20DC%20%7C%20Bomba%20Dupla-orange.svg?style=for-the-badge)](#)

---

<p align="center">
  <b>Engenharia DIY de baixo custo e alta eficiência para irrigação automática de 12 vasos de plantas.</b><br/>
  Um projeto focado em zero desperdício de água, acionamento por inteligência de voz via Alexa, proteção elétrica com refrigeração passiva e arquitetura expansível para Home Assistant e ESP32.
</p>

[📌 Visão Geral](#-visao-geral-do-projeto) •
[🛠️ Hardware](#%EF%B8%8F-especificacoes-tecnicas-de-hardware) •
[🤖 Automação](#-fluxo-explicativo-da-automacao) •
[📸 Galeria](#-galeria-visual-do-projeto) •
[📐 Diagrama](#-arquitetura-do-sistema) •
[🚀 Roadmap](#-roadmap-de-evolucao)

---

</div>

<br/>

## 📌 Visão Geral do Projeto

<table>
  <tr>
    <td width="50%">
      <h3>💧 Precisão Hidráulica</h3>
      <p>Micro-dosagem direcionada diretamente às raízes através de <b>12 gotejadores ajustáveis</b> conectados por micro-tubos de 6mm, eliminando o desperdício por evaporação ou escorrimento superficial.</p>
    </td>
    <td width="50%">
      <h3>⚡ Segurança Elétrica Reforçada</h3>
      <p>Alimentação por <b>fonte chaveada Slim de alumínio (12V 10A)</b> com dissipação de calor 100% passiva, seccionada por tomada física e chave de emergência para manutenção rápida e segura.</p>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>🗣️ Rotina Inteligente por Voz e Clima</h3>
      <p>Integração total ao ecossistema Alexa para <b>checagem prévia da previsão do tempo</b>, envio de notificações no smartphone e feedback por voz antes e depois da rega.</p>
    </td>
    <td width="50%">
      <h3>🛠️ Arquitetura Acessível & Aberta</h3>
      <p>Construído com componentes modulares de fácil acesso, otimizado para operação em nuvem (Smart Life/Tuya) e estruturado para futura migração local via <b>ESP32 e Home Assistant (CasaOS)</b>.</p>
    </td>
  </tr>
</table>

<br/>

---

## 🛠️ Especificações Técnicas de Hardware

| Componente | Categoria | Especificação Técnica | Função Operacional no Sistema |
| :--- | :---: | :--- | :--- |
| **Bomba de Água** | Hidráulica | Mini Dupla Diafragma (12V DC / 6A) | Sucção da água da caixa e pressurização para a rede |
| **Fonte de Alimentação** | Elétrica | Chaveada Slim Alumínio (12V DC / 10A) | Conversão 110V/12V com refrigeração passiva em alumínio |
| **Relé Inteligente** | Automação | Módulo Mini Smart (Smart Life / Tuya) | Comutação da rede elétrica controlada via Wi-Fi |
| **Chave de Manutenção** | Segurança | Tomada Física + Chave de Seccionamento | Isolamento elétrico manual instantâneo do sistema |
| **Rede de Distribuição** | Hidráulica | Micro-tubos 6mm + 12 Gotejadores | Condução e rega localizada direta no solo dos vasos |
| **Reservatório** | Reservatório | Caixa d'Água (Linha de Pressão) | Abastecimento contínuo e gravitacional para a bomba |

<br/>

---

## 🤖 Fluxo Explicativo da Automação

> [!NOTE]  
> A irrigação ocorre em um ciclo diário automatizado de **exatos 60 segundos**, alinhando controle elétrico e confirmação sonora.

<details open>
<summary><b>🔍 Passo a Passo Detalhado do Ciclo Diário</b></summary>
<br/>

1. 🕒 **09:00 — Análise Meteorológica:** A Alexa consulta o serviço de clima e verifica a probabilidade de chuva do dia.
2. 🗣️ **09:00 — Alerta Sonoro:** A caixa Echo emite o aviso: *"Vou molhar as plantas do corredor agora às 9 horas"*.
3. ⚡ **09:00 — Acionamento Elétrico:** O Relé Wi-Fi chaveia a alimentação de 110V para a Fonte Slim de 12V.
4. 💧 **09:00 às 09:01 — Rega Pressurizada:** A bomba de diafragma opera por 60 segundos alimentando a rede de 12 gotejadores.
5. ✅ **09:01 — Finalização Segura:** O relé corta a energia da fonte e a Alexa confirma: *"Acabei de regar as plantas e desliguei a água"*.

</details>

<br/>

---

## 📸 Galeria Visual do Projeto

<div align="center">

| ⚡ Painel Elétrico & Fonte | 💧 Bomba & Linha de Pressão | 🌿 Vasos & Micro-Gotejadores |
| :---: | :---: | :---: |
| <img src="painel.jpg" width="260px" alt="Painel Elétrico" /> | <img src="bomba.jpg" width="260px" alt="Bomba de Água" /> | <img src="vasos.jpg" width="260px" alt="Gotejadores" /> |
| *Fonte Slim 12V e Relé Wi-Fi com proteção elétrica* | *Bomba Dupla Diafragma 12V 6A acoplada à tubulação* | *Rede de micro-tubos de 6mm irrigando 12 vasos* |

</div>

<br/>

---

## 📐 Arquitetura do Sistema

Abaixo está o diagrama do circuito elétrico e hidráulico em formato de imagem fixo, imune a erros de tradução de navegadores:

<div align="center">

![Esquema Elétrico e Hidráulico](esquema.png)

</div>

<br/>

---

## 🚀 Roadmap de Evolução

- [x] **Fase 1:** Montagem e testes do painel elétrico (Fonte Slim 12V 10A + Relé Wi-Fi + Tomada de Segurança).
- [x] **Fase 2:** Instalação da infraestrutura hidráulica (Bomba dupla diafragma, tubos 6mm e 12 gotejadores).
- [x] **Fase 3:** Configuração das rotinas de voz, checagem do clima e avisos sonoros na Alexa.
- [ ] **Fase 4 (Em breve):** Instalação de sensor capacitivo de umidade do solo para prevenção em dias chuvosos/úmidos.
- [ ] **Fase 5:** Gravação de firmware **ESPHome** em placa **ESP32** para controle local.
- [ ] **Fase 6:** Migração do controle da nuvem para o **Home Assistant** hospedado no servidor **CasaOS**.

---

<div align="center">

Desenvolvido com dedicação por **[Adanilson](https://github.com/adanilsonf10-ui)** 🚀  
*Se este projeto te ajudou ou te inspirou, considere deixar uma ⭐️ no repositório!*

</div>
