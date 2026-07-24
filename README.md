# 🛡️ SOC Lab: Monitoramento de Endpoint Linux & Análise de Events com Wazuh SIEM

## 🎯 Sobre o Projeto
Este projeto consiste na construção de um **Home Lab defensivo (Blue Team)** focado no monitoramento contínuo de endpoints e na análise centralizada de logs. 

O servidor SIEM foi implantado a partir de uma instalação minimalista (**Debian Netinst**), priorizando a redução da superfície de ataque do SO e o controle total dos serviços de infraestrutura. O ambiente monitorado conta com um endpoint **Kali Linux** integrado via **Wazuh Agent**, permitindo a detecção em tempo real de eventos críticos do sistema.

---

## 📐 Arquitetura do Ambiente

| Componente | Função | SO / Tecnologia |
| :--- | :--- | :--- |
| **Servidor SIEM** | Coleta, parsing, correlação de logs e Dashboard | **Debian GNU/Linux** (Netinst) + Wazuh Server v4.x |
| **Endpoint Monitorado** | Agente de coleta de auditoria e eventos | **Kali Linux** + Wazuh Agent |
| **Coleta de Dados** | Logs de autenticação, comandos `sudo` e `syslog` | Log Collector Native / Agent Channel |

---

## 🛠️ Configuração e Implantação

### 1. Hardening e Servidor SIEM (Debian Netinst)
* **Instalação Minimalista:** Utilização do ISO `netinst` para manter apenas pacotes estritamente necessários ao funcionamento do Wazuh SIEM.
* **Rede & Serviços:** Configuração de IP estático, gerenciamento de serviços via `systemd` e liberação seletiva de portas locais para os agentes.
* **Deploy do Wazuh:** Instalação e parametrização do Wazuh Indexer, Manager e Dashboard.

### 2. Integração do Endpoint (Kali Linux)
* Instalação e pareamento do **Wazuh Agent** no Kali Linux.
* Configuração do envio de logs do sistema (`syslog`, `/var/log/auth.log`).
* Auditoria de elevação de privilégios e execução de comandos via `sudo`.

---

## 🔍 Cenários de Monitoramento & Casos de Uso

1. **Auditoria de Autenticação (`auth.log`):**
   * Detecção de falhas de autenticação e tentativas de acesso local/remoto (SSH).
2. **Monitoramento de Elevação de Privilégios:**
   * Alertas para execução não autorizada ou atípica de comandos com `sudo`.
3. **Análise de Integridade de Arquivos (FIM):**
   * Rastreamento de alterações em diretórios críticos do sistema (ex: `/etc/passwd`, `/etc/shadow`, `/etc/sudoers`).

---

## 💡 Competências Técnicas Demonstradas

* **Administração de Sistemas Linux:** Instalação enxuta (Debian Netinst), navegação avançada em terminal, gestão de serviços (`systemctl`) e pacotes (`apt`).
* **SIEM & Resposta a Incidentes:** Implementação de SIEM open-source, criação e ajuste de regras de detecção.
* **Análise de Logs de Segurança:** Interpretação de `syslog`, arquivos de auditoria e padrões de eventos no ecossistema Linux.
* **Segurança de Redes:** Entendimento de portas de comunicação entre agentes e servidor SIEM em rede local.

---

## 👤 Autor

**Khalil Sousa Pellegrini**  
*Estudante de Técnico em Redes de Computadores no Instituto Federal do Tocantins (IFTO)*  
* Foco em **Segurança da Informação / SOC N1 / Blue Team**  
* LinkedIn: www.linkedin.com/in/khalil-sousa-pellegrini-8a70852b0  
* GitHub: https://github.com/Khalil-Pellegrini
