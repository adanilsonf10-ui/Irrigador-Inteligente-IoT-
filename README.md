# 🪴 Irrigador Inteligente IoT (Smart Irrigation Hub)

Projeto de automação residencial de **baixo custo, alta eficiência e zero desperdício de água** para rega automática de plantas. Desenvolvido com acionamento inteligente via assistente virtual (Alexa), proteção elétrica reforçada e infraestrutura para futura integração local.

---

## 🎯 Objetivos do Projeto

* **Rega Autônoma:** Garantir a irrigação diária dos vasos sem intervenção manual.
* **Economia de Água:** Micro-dosagem direcionada diretamente às raízes através de gotejadores.
* **Segurança e Durabilidade:** Proteção contra aquecimento excessivo e facilidade de seccionamento para manutenção.
* **Baixo Custo (DIY):** Utilização de componentes de fácil acesso e excelente custo-benefício.

---

## 🛠️ Componentes do Hardware

| Componente | Especificação Tecnológica | Função no Sistema |
| :--- | :--- | :--- |
| **Bomba de Água** | Dupla Diafragma de Pulverização (Mini 12V / 6A) | Pressurização e sucção da água do reservatório |
| **Fonte de Alimentação** | Chaveada Slim de Alumínio 12V DC / 10A | Refrigeração passiva pelo corpo e conversão de energia |
| **Relé Wi-Fi** | Relé Mini Smart (Smart Life / Tuya) | Controle ON/OFF automatizado e via Wi-Fi |
| **Proteção / Chaveamento** | Tomada e Chave de Seccionamento | Desligamento rápido para manutenção com segurança |
| **Rede Hidráulica** | Micro-tubos 6mm + 12 Gotejadores | Distribuição de água micro-dosada para 12 vasos |
| **Reservatório** | Caixa d'Água (Torneira Aberta) | Abastecimento contínuo e gravitacional para a bomba |

---

## 🤖 Rotina de Automação na Alexa

A irrigação é executada automaticamente através de uma rotina diária inteligente:

1. **Previsão do Tempo:** A Alexa lê a probabilidade de chuva e temperatura local no início.
2. **Aviso Sonoro e Notificação:** Envia notificação no celular e anuncia por voz: *"Vou molhar as plantas do corredor agora às 9 horas"*.
3. **Acionamento:** O Relé Wi-Fi liga a alimentação da fonte de 12V.
4. **Irrigação Dosada:** A bomba funciona por exatos **60 segundos** alimentando os 12 gotejadores.
5. **Confirmação e Término:** O relé desliga e a Alexa confirma por voz: *"Acabei de regar as plantas e desliguei a água"*.

---

## 📐 Diagrama Elétrico e Hidráulico

```mermaid
graph TD
    classDef rede fill:#ffebee,stroke:#c62828,stroke-width:2px,color:#b71c1c;
    classDef fonte fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#1b5e20;
    classDef rele fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#0d47a1;
    classDef carga fill:#fff3e0,stroke:#ef6c00,stroke-width:2px,color:#e65100;
    classDef hidraulica fill:#e0f7fa,stroke:#00838f,stroke-width:2px,color:#006064;

    subgraph ENERGIA ["⚡ Alimentação Elétrica"]
        AC["Rede Elétrica 110V AC"] ::: rede
        TOMADA["Tomada de Segurança / Chave de Manutenção"] ::: rede
    end

    subgraph AUTOMACAO ["🤖 Controle Inteligente"]
        RELE["Relé Wi-Fi Inteligente Mini (Smart Life/Tuya)"] ::: rele
    end

    subgraph CONVERSAO ["💡 Conversão de Potência"]
        FONTE["Fonte Slim de Alumínio 12V 10A<br/><i>(Corpo em alumínio para refrigeração passiva)</i>"] ::: fonte
    end

    subgraph CARGA ["💧 Sistema de Bombeamento"]
        BOMBA["Bomba Dupla Diafragma 12V 6A"] ::: carga
    end

    subgraph HIDRAULICA ["🌿 Rede Hidráulica"]
        CAIXA[("Caixa d'Água (Torneira Aberta)")] ::: hidraulica
        TUBOS["Micro-tubos 6mm"] ::: hidraulica
        VASOS["12 Gotejadores / Vasos de Plantas"] ::: hidraulica
    end

    %% Ligações Elétricas
    AC ==>|110V| TOMADA
    TOMADA ==>|Fase / Neutro| RELE
    RELE ==>|110V Comutado| FONTE
    FONTE ==>|12V DC Positivo / Negativo| BOMBA

    %% Ligações Hidráulicas
    CAIXA -->|Sucção de Água| BOMBA
    BOMBA -->|Água Pressurizada| TUBOS
    TUBOS -->|Irrigação Dosada 1 min| VASOS
```

