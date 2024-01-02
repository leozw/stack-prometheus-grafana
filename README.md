# **Guia Completo de Instalação e Configuração do Prometheus e Grafana**

Este guia fornece instruções detalhadas para configurar uma stack de observabilidade usando Prometheus, Grafana com PVC (Persistent Volume Claim), e diversos exporters e serviços relacionados. Vamos abordar cada componente e sua função na stack.

## **Pré-requisitos**

- Kubernetes cluster operacional.
- Helm instalado e configurado.

## **Configuração da Stack**

### **1. Adicionando o Repositório do Prometheus Community ao Helm**

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

### **2. Instalação da Stack com Prometheus e Grafana**

```bash
helm install prometheus prometheus-community/kube-prometheus-stack -f values.yaml
```

## **Componentes da Stack**

### **Prometheus**

O Prometheus é o coração da stack de observabilidade, responsável pela coleta e armazenamento de métricas de tempo.

### **Grafana**

O Grafana é a interface de visualização para os dados coletados pelo Prometheus. Permite criar dashboards interativos e visualizar métricas.

## **Outros Exporters e Serviços**

### **Node Exporter**

O Node Exporter é um exporter que coleta métricas de hardware e SO de cada node do Kubernetes, como uso de CPU, memória, disco e rede.

### **Alert Manager**

O Alert Manager gerencia alertas do Prometheus. Ele processa alertas enviados pelo Prometheus e pode reencaminhá-los para diferentes destinos como e-mail, Slack, etc.

### kube-state-metrics

Coleta métricas sobre o estado de objetos do Kubernetes, como deployments, pods e nodes.

### Prometheus Operator

Simplifica a configuração e operação do Prometheus em ambientes Kubernetes.

### Additional Service Monitors

Service Monitors configuram como o Prometheus descobre e coleta métricas de diferentes serviços.

### PVC para Grafana

Configuração de Persistent Volume Claim para garantir que os dados e configurações do Grafana sejam mantidos entre reinicializações do pod.

### **3. Acesso e Verificação**

Instruções para acessar o Prometheus e o Grafana, e como verificar se todos os componentes estão funcionando corretamente.

### **4. Atualização e Manutenção**

```bash
helm upgrade prometheus prometheus-community/kube-prometheus-stack -f values.yam
```

### **5. Desinstalação**

```bash
helm uninstall prometheus
```

## **Conclusão**

Este guia oferece uma visão geral de como configurar uma stack robusta de observabilidade com Prometheus e Grafana. Periodicamente, verifique atualizações para manter a stack segura e eficiente.

Repo base: https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack
