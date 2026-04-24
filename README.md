---

# 🔐 Monitoramento de Segurança com Suricata + Wazuh

Projeto prático de **detecção de ameaças em rede**, utilizando um IDS integrado a um SIEM para coleta, análise e visualização de eventos.

---

## 🎯 Objetivo

Implementar um ambiente funcional de monitoramento capaz de:

* Detectar atividades suspeitas em rede
* Correlacionar eventos em um SIEM
* Simular cenários de ataque
* Gerar alertas para análise

---

## 🧠 Tecnologias Utilizadas

* Suricata — detecção de tráfego e ameaças
* Wazuh — ingestão e análise de logs
* Nmap — simulação de varredura de portas
* Linux (Debian)

---

## 🏗️ Arquitetura

```text
Tráfego de rede → Suricata → eve.json → Wazuh → Dashboard
```

---

## 📁 Estrutura do Projeto

```text
suricata-wazuh/
├── config/
│   ├── suricata.yaml
│   └── ossec.conf
├── rules/
│   └── local.rules
├── logs/ (ignorado no versionamento)
└── README.md
```

---

## ⚙️ Configuração do Ambiente

* Configuração do Suricata para monitoramento da interface de rede
* Integração do arquivo `eve.json` com o Wazuh
* Ajustes no parsing de logs JSON
* Criação de regras customizadas para detecção de eventos

---

## 🔍 Regras Implementadas

Regras customizadas utilizadas no projeto:

```text
alert icmp any any -> any any (msg:"ICMP PING DETECTADO"; sid:1000001; rev:1;)
alert tcp any any -> any any (msg:"TCP SYN SCAN DETECTADO"; flags:S; threshold:type threshold, track by_src, count 5, seconds 10; sid:1000002; rev:1;)
alert http any any -> any any (msg:"ACESSO HTTP DETECTADO"; sid:1000003; rev:1;)
alert dns any any -> any any (msg:"CONSULTA DNS DETECTADA"; sid:1000004; rev:1;)
```

---

## 🚨 Cenários de Ataque Simulados

### 🔎 Reconhecimento de rede (SYN Scan)

```bash
nmap -sS -p- <IP>
```

---

### 🌐 Consultas DNS

```bash
dig google.com
```

---

### 🔐 Tentativas de conexão

```bash
ssh <IP>
```

---

## 📊 Resultados

* Detecção de tráfego ICMP (ping)
* Identificação de consultas DNS
* Detecção de varredura SYN (Nmap)
* Monitoramento de tráfego HTTP
* Geração de alertas no Wazuh
* Visualização de eventos no dashboard

---

## 🧠 Desafios Enfrentados

* Configuração correta da interface de rede no Suricata
* Problemas de parsing JSON no Wazuh
* Ajuste de regras para diferentes protocolos
* Delay na ingestão de eventos no SIEM
* Integração entre IDS e SIEM

---

## 🚀 Aprendizados

* Funcionamento prático de um IDS integrado a um SIEM
* Criação e validação de regras de detecção
* Simulação de ataques de rede
* Troubleshooting em ambiente de segurança
* Análise de eventos em tempo quase real

---

## 🔥 Próximos Passos

* Simulação de brute force SSH
* Integração com MITRE ATT&CK
* Criação de dashboards personalizados
* Automação de alertas

---

## 💼 Sobre o Projeto

Projeto desenvolvido com foco em práticas de **Security Operations Center (SOC)**, simulando cenários de ataque e análise de eventos em um ambiente controlado.

---
