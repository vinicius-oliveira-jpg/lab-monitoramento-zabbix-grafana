# Instalação do Grafana

## Objetivo

O Grafana foi utilizado neste laboratório como ferramenta de visualização, permitindo a criação de dashboards para acompanhamento das métricas coletadas pelo Zabbix.

## Instalação

A instalação do Grafana foi realizada no mesmo servidor Debian 13 utilizado pelo Zabbix Server.

> Nesta etapa são utilizados os comandos referentes ao método de instalação escolhido no ambiente.

Após a instalação do pacote, o serviço do Grafana deve ser iniciado.

## Iniciando o serviço do Grafana

Habilite o serviço para iniciar automaticamente com o sistema:

```bash
sudo systemctl enable grafana-server
```

Inicie o serviço:

```bash
sudo systemctl start grafana-server
```

## Verificando o serviço

Confirme se o Grafana está em execução:

```bash
sudo systemctl status grafana-server
```

Resultado esperado:

```text
Active: active (running)
```

## Acessando o Grafana

O acesso ao Grafana é realizado pelo navegador através da porta padrão:

```text
http://192.168.10.110:3000
```

No primeiro acesso é apresentada a tela de autenticação do Grafana.

Credenciais iniciais:

```text
Usuário: admin
Senha: admin
```

Após o primeiro login, a senha do usuário administrador deve ser alterada.

## Dashboard do Grafana

Após a instalação e configuração, o Grafana ficou disponível para criação dos dashboards de monitoramento utilizando os dados coletados pelo Zabbix.

Dashboard criado no laboratório:

![Dashboard Grafana](../imagens/11-Dashboards-Grafana.png)

## Conclusão

Com o Grafana instalado e funcionando, o próximo passo foi realizar a integração com o Zabbix para permitir a consulta das métricas coletadas pelo servidor.