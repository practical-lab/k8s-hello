# Helm

## Installation

```powershell
scoop install helm
```

## Basic commands

### Help

```bash
helm -h
```

## Wordpress

This example is based on [事実上の標準ツールとなっているKubernetes向けデプロイツール「Helm」入門](https://knowledge.sakura.ad.jp/23603/).

### Add a repo

```bash
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
```

### Install wordpress via helm

```bash
helm install wordpress stable/wordpress
```

### Uninstall wordpress

```bash
helm uninstall wordpress
```
