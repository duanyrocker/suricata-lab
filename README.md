# 🛡️ Suricata Lab - Detecção de Intrusão (IDS)

## 📌 Sobre o Projeto

Este projeto demonstra a implementação prática do **Suricata** como sistema de detecção de intrusão (IDS), com foco em monitoramento de tráfego de rede e identificação de atividades suspeitas através de regras customizadas.

---

## 🧠 Objetivo

* Implementar um IDS funcional utilizando Suricata
* Criar e testar regras personalizadas
* Monitorar tráfego de rede em tempo real
* Detectar eventos como ping (ICMP) e atividades suspeitas

---

## 🏗️ Arquitetura do Lab

* 💻 Máquina virtual (VirtualBox)
* 🐧 Sistema Linux
* 🌐 Interface de rede: `enp0s3`
* 🔐 Monitoramento em tempo real com Suricata

---

## 📁 Estrutura do Projeto

```bash
suricata-lab/
│
├── config/
│   └── suricata.yaml
│
├── rules/
│   └── local.rules
│
└── README.md
```

---

## ⚙️ Tecnologias Utilizadas

* Suricata (IDS/IPS)
* Linux
* Git & GitHub

---

## 🚀 Como Executar

### 1. Clonar o repositório

```bash
git clone https://github.com/duanyrocker/suricata-lab.git
cd suricata-lab
```

---

### 2. Executar o Suricata

```bash
sudo suricata -c config/suricata.yaml -i enp0s3
```

> ⚠️ Ajuste a interface de rede conforme seu ambiente

---

## 🧪 Testes Realizados

### ✔️ Detecção de Ping (ICMP)

Foi criada uma regra personalizada para detectar tráfego ICMP:

```bash
alert icmp any any -> any any (msg:"Ping detectado"; sid:1000001; rev:1;)
```

### 🔎 Simulação

Em outro terminal:

```bash
ping 8.8.8.8
```

---

## 📊 Resultados

O Suricata gerou alertas com sucesso:

```bash
[**] [1:1000001:1] Ping detectado [**]
```

Os logs são armazenados em:

* `fast.log`
* `eve.json`
* `stats.log`

> ⚠️ Logs não são versionados no repositório

---

## 🔐 Boas Práticas Aplicadas

* Uso de `.gitignore` para evitar dados sensíveis
* Organização modular (`config/`, `rules/`)
* Separação de configuração e regras
* Testes práticos de detecção

---

## 🚀 Possíveis Melhorias

* Integração com ELK Stack (SIEM)
* Dashboard com Grafana
* Execução via Docker
* Implementação como IPS (modo inline)

---

## 👩‍💻 Autora

**Duany Rocker**
Analista de Segurança Júnior em formação

---

## ⭐ Considerações

Este projeto demonstra habilidades práticas em:

* Segurança de redes
* Análise de tráfego
* Detecção de ameaças
* Configuração de ferramentas de segurança

---
