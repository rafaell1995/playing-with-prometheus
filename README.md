Para usar a configuração do Docker com Prometheus, Node Exporter e Grafana que você configurou para monitorar o uso de disco do seu servidor, siga os passos abaixo:

1.  Acesse o Prometheus:

    -   Abra um navegador e acesse `http://<seu-endereço-ip>:9090`, substituindo `<seu-endereço-ip>` pelo IP do seu servidor. Aqui, você pode ver se o Prometheus está coletando métricas do Node Exporter.

2.  Verifique as Métricas no Prometheus:

    -   No Prometheus, vá para a página "Graph" e insira consultas para verificar as métricas de uso de disco. Por exemplo, você pode usar uma consulta como `node_filesystem_avail_bytes` ou `node_filesystem_free_bytes` para verificar o espaço disponível no disco.

3.  Acesse o Grafana:

    -   Abra um navegador e acesse `http://<seu-endereço-ip>:3000`. Use o nome de usuário e senha padrão (`admin`/`admin`, a menos que você tenha mudado).

4.  Configure o Prometheus como Fonte de Dados no Grafana:

    -   No Grafana, vá para "Configuration" > "Data Sources" e adicione o Prometheus como uma nova fonte de dados. O URL da fonte de dados será `http://prometheus:9090` se você estiver usando os nomes de serviço do `docker-compose.yml`.

5.  Crie um Dashboard no Grafana:

    -   No Grafana, crie um novo dashboard.
    -   Adicione um painel e escolha as métricas que deseja visualizar, como as métricas de uso de disco que o Node Exporter coleta.
    -   Configure o painel para exibir as métricas de uso de disco de maneira que faça sentido para você, como gráficos de tempo, barras, etc.

6.  Configure Alertas no Grafana (opcional):

    -   Você pode configurar alertas no Grafana para notificá-lo quando o uso do disco atingir um limiar crítico. Isso pode ser feito na configuração do painel, na seção de alertas.

7.  Monitore e Analise:

    -   Use o Grafana regularmente para monitorar o uso de disco. Os dashboards irão fornecer uma visão clara e atualizada do estado do disco.

8.  Ajuste conforme Necessário:

    -   Com base nas métricas e alertas que você recebe, você pode precisar ajustar sua infraestrutura, como limpar arquivos desnecessários, aumentar a capacidade de armazenamento, etc.
    
9.  Manutenção e Atualizações:

    -   Mantenha o seu sistema de monitoramento atualizado e revise regularmente para garantir que ele continua atendendo às suas necessidades.

Com essa configuração, você terá um sistema robusto para monitorar o uso de disco do seu servidor, permitindo que você tome ações proativas para gerenciar o armazenamento e evitar problemas relacionados a espaço em disco insuficiente.