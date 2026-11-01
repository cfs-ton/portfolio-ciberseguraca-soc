# 🛡️ Portfólio de Cibersegurança — SOC N1

Olá! Seja bem-vindo(a) ao meu portfólio de Segurança da Informação.

Sou estudante de Análise e Desenvolvimento de Sistemas (ADS) e estou desenvolvendo meus conhecimentos na área de Cibersegurança, com foco em monitoramento de segurança, análise de logs e atuação como Analista SOC N1.

## 🎯 Objetivo

Desenvolver habilidades práticas em Segurança da Informação, monitoramento de eventos, análise de tráfego de rede e investigação inicial de incidentes.

## 🧰 Ferramentas e tecnologias em estudo

- Linux (Ubuntu e Kali Linux)
- Windows 10
- Wireshark
- Nmap
- VirusTotal
- Python
- Git e GitHub
- VirtualBox
- TryHackMe

## 🔬 Projetos práticos

Os projetos serão desenvolvidos em laboratório próprio, com foco em aprendizado e documentação técnica.

### 01 — Análise de Rede
- Reconhecimento de dispositivos em laboratório.
- Identificação de portas e serviços.
- Captura e análise de tráfego com Wireshark.

### 02 — Análise de Logs
- Investigação de eventos do Windows.
- Análise de tentativas de autenticação.
- Documentação de evidências.

### 03 — Analisador de Logs com Python
- Leitura de arquivos de log.
- Identificação de padrões de eventos.
- Geração de relatórios automatizados.

## 📚 Conhecimentos em desenvolvimento

- Fundamentos de redes TCP/IP.
- Protocolos DNS, HTTP e HTTPS.
- Segurança de sistemas Windows e Linux.
- Monitoramento e triagem de alertas.
- Fundamentos de resposta a incidentes.

## 📌 Sobre este portfólio

Este repositório reúne meus estudos, laboratórios, exercícios e projetos práticos desenvolvidos durante minha formação em Segurança da Informação.

Todos os testes são realizados em ambientes próprios ou autorizados.

---
**Objetivo profissional:** conquistar minha primeira oportunidade em Segurança da Informação, com foco em SOC N1.

---
## Lab 01 - 01/11/2026 - health Check + Recon

**Cenário:** VM com disco / em 90% (21G/25G)
**Ações SOC L1:**
- `sudo journalctl --vacuum-size=500M`- liberou 224MB
- `minikube delete --all --purge`- liberou 3GB
- Resultado: 70% (17G/25G) - 7.2G livres

**Scan Nmap:**
- `nmap -F localhost` -> 99 closed, 1 open 631/tcp CUPS 2.4
- `ss -tulpn | grep 631` -> cupsd pid 1289 só em 127.0.0.1
- Risco: Baixo

**Análise de log:**
- `grep -E Failed|Accepted /var/log/auth.log` -> 0 brute force
- Falso positivo org.bluez VirtualBox
