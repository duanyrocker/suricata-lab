# 🛡️ Projeto Suricata - IDS/IPS

## 📌 Sobre o Projeto

Este projeto tem como objetivo implementar e testar o **Suricata** como sistema de detecção e prevenção de intrusões (IDS/IPS), permitindo a análise de tráfego de rede e identificação de atividades suspeitas.

---

## 🧠 O que é o Suricata?

O Suricata é uma ferramenta open-source de segurança de rede que atua como:

* 🔍 IDS (Intrusion Detection System)
* 🚫 IPS (Intrusion Prevention System)
* 📊 Analisador de tráfego em tempo real

---

## 🎯 Objetivo

* Monitorar tráfego de rede
* Detectar atividades maliciosas
* Criar e testar regras personalizadas
* Gerar alertas de segurança

---

## 🏗️ Estrutura do Projeto

```
projeto-suricata/
│
├── config/
│   └── suricata.yaml
│
├── rules/
│   └── local.rules
│
├── logs/              # não versionado
│
├── scripts/           # opcional
│
├── .gitignore
└── README.md
```

---

## ⚙️ Tecnologias Utilizadas

* Suricata
* Linux
* Git & GitHub
* Regras customizadas IDS/IPS

---

## 🚀 Como Executar

### 1. Clonar o repositório

```
git clone git@github.com:SEU_USUARIO/projeto-suricata.git
cd projeto-suricata
```

---

### 2. Executar o Suricata

```
sudo suricata -c config/suricata.yaml -i enp0s3
```

> ⚠️ Substitua `enp0s3` pela sua interface de rede

---

## 🧪 Testes Realizados

### ✔️ Teste de Ping (ICMP)

* Geração de tráfego ICMP
* Detecção via regra personalizada

### ✔️ Análise de tráfego

* Monitoramento em tempo real
* Geração de alertas

---

## 📊 Logs e Alertas

Os alertas são gerados em arquivos como:

* `fast.log`
* `eve.json`
* `stats.log`

> ⚠️ Esses arquivos não são versionados no Git

---

## 🧩 Exemplo de Regra

```
alert icmp any any -> any any (msg:"Ping detectado"; sid:1000001;)
```

---

## 🌐 Ambiente

* Máquina Virtual (VirtualBox)
* Sistema Linux
* Rede NAT / Bridge

---

## 🔐 Boas Práticas Aplicadas

* Uso de `.gitignore` para evitar logs
* Organização modular do projeto
* Configuração separada (`config/`)
* Regras customizadas

---

## 🚀 Melhorias Futuras

* Integração com ELK Stack
* Dashboard com Grafana
* Automação com scripts
* Deploy com Docker

---

## 👩‍💻 Autora

Projeto desenvolvido por **Duany Rocker**

---

## ⭐ Contribuição

Sinta-se à vontade para contribuir ou sugerir melhorias!
