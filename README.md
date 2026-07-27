# Laboratório de Monitoramento com Zabbix e Grafana

## 📖 Sobre o projeto

Este projeto apresenta a implementação de um ambiente de monitoramento utilizando **Zabbix 7.4** e **Grafana** sobre o **Debian GNU/Linux 13 (Trixie)**.

O objetivo foi desenvolver um laboratório funcional para monitorar um servidor Linux, utilizando o próprio sistema operacional como host monitorado. Durante o projeto foram realizadas a instalação, configuração e integração das ferramentas, permitindo visualizar métricas do sistema em tempo real através de dashboards.

---

## 🎯 Objetivos

- Implementar um servidor de monitoramento utilizando o Zabbix.
- Configurar o banco de dados MariaDB.
- Monitorar um servidor Debian utilizando o Zabbix Agent.
- Integrar o Zabbix ao Grafana.
- Criar dashboards para visualização das métricas.
- Documentar todo o processo de implantação.

---

## 🖥️ Ambiente utilizado

| Componente | Versão |
|------------|---------|
| Sistema Operacional | Debian GNU/Linux 13 (Trixie) |
| Banco de Dados | MariaDB |
| Servidor Web | Apache2 |
| Linguagem | PHP |
| Monitoramento | Zabbix Server 7.4 |
| Agente | Zabbix Agent |
| Dashboard | Grafana |

---

## 📌 Host monitorado

Durante este laboratório foi monitorado apenas um host.

| Host | Descrição |
|------|-----------|
| VM_Debian13 | Servidor Debian responsável por executar o Zabbix Server, Zabbix Agent, MariaDB e Grafana. |

---

## 🏗️ Arquitetura do laboratório

```text
                 +----------------------+
                 |   VM Debian 13       |
                 |     VM_Debian13      |
                 +----------+-----------+
                            |
                     Zabbix Agent
                            |
                     Zabbix Server
                            |
                        MariaDB
                            |
                    Apache2 + PHP
                            |
                  Interface Web Zabbix
                            |
              Plugin Grafana-Zabbix
                            |
                         Grafana
                            |
                       Dashboard
```

Neste laboratório, todos os componentes foram instalados na mesma máquina virtual Debian 13. O Zabbix Agent coleta as métricas do sistema e as envia ao Zabbix Server, que armazena os dados no MariaDB. O Grafana consome essas informações por meio da API do Zabbix e apresenta as métricas em dashboards.