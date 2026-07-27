# Integração Grafana com Zabbix

## Objetivo

A integração entre o Grafana e o Zabbix foi realizada para permitir a utilização dos dados coletados pelo Zabbix Server na criação de dashboards de monitoramento.

## Instalação do plugin Zabbix

Para permitir a comunicação entre as ferramentas, foi utilizado o plugin do Zabbix para Grafana.

Instalação do plugin:

```bash
grafana-cli plugins install alexanderzobnin-zabbix-app
```

Após a instalação do plugin, reinicie o serviço do Grafana:

```bash
sudo systemctl restart grafana-server
```

## Habilitando o plugin no Grafana

No painel Web do Grafana, acesse:

```text
Administration
→ Plugins
→ Zabbix
```

Habilite o plugin instalado.

## Configurando a fonte de dados

No Grafana, acesse:

```text
Connections
→ Data sources
→ Add data source
→ Zabbix
```

Configure a conexão utilizando a API do Zabbix:

```text
URL:

http://localhost/zabbix/api_jsonrpc.php
```

Informe as credenciais de acesso ao Zabbix.

Após preencher os dados, utilize a opção:

```text
Save & Test
```

para validar a comunicação entre Grafana e Zabbix.

## Criação do dashboard

Após a integração, foram criados painéis para visualizar as métricas coletadas do servidor Debian.

Entre as informações monitoradas estão:

- Utilização de CPU;
- Memória RAM;
- Armazenamento;
- Tráfego de rede;
- Disponibilidade do host;
- Informações gerais do sistema.

Dashboard final:

![Dashboard Grafana](../imagens/11-Dashboards-Grafana.png)

## Conclusão

Com a integração concluída, o laboratório passou a disponibilizar uma visualização gráfica das métricas coletadas pelo Zabbix através dos dashboards do Grafana.

O ambiente final ficou composto por:

- Debian GNU/Linux 13;
- MariaDB;
- Zabbix Server 7.4;
- Zabbix Agent;
- Apache2;
- PHP;
- Grafana integrado ao Zabbix.