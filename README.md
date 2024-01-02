# **Guia de Instalação da Stack Prometheus e Grafana**

Este guia detalha como configurar uma stack de observabilidade robusta usando Prometheus e Grafana, incluindo configurações para PVC (Persistent Volume Claim) para o Grafana e additional scrape para o Prometheus.

## **Pré-requisitos**

- Ter o Helm instalado.
- Configuração de kubeconfig adequada.

## **🚀 Configuração**

### **1. Adicionando o Repositório do Prometheus Community ao Helm**

Primeiro, adicione o repositório Prometheus Community ao Helm:

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

### **2. Instalação do Prometheus e Grafana com PVC e AdditionalScrape**

A seguir, instale o Prometheus e Grafana. Neste exemplo, usamos um arquivo de configurações **`values.yaml`** que inclui as configurações do PVC para Grafana e additional scrape para Prometheus:

```bash
helm install prometheus prometheus-community/kube-prometheus-stack -f values.yaml
```

### **3. Atualização do Prometheus e Grafana**

Para atualizar a stack do Prometheus e Grafana, use o seguinte comando:

```bash
helm upgrade prometheus prometheus-community/kube-prometheus-stack -f values.yaml
```

### **4. Desinstalação**

Caso seja necessário remover a stack, utilize:

```bash
helm uninstall prometheus
```

## **🎉 Conclusão**

Após seguir os passos acima, você terá configurado com sucesso uma stack de observability com Prometheus e Grafana, otimizada com PVC para o Grafana e additional scrape para o Prometheus. É recomendável verificar periodicamente por atualizações para manter sua stack atualizada e segura.

---