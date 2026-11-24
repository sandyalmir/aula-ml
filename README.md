# Versionamento de Dados e Modelos

Este projeto apresenta uma prática de versionamento de dados e modelos de Machine Learning utilizando Git e DVC.

## Objetivo

Demonstrar como versionar conjuntos de dados, modelos treinados e resultados de experimentos, permitindo reproduzir versões anteriores e acompanhar alterações nos dados.

## Tecnologias utilizadas

- Python
- Git
- DVC
- Pandas
- Scikit-learn

## Estrutura do projeto

- `data/`: conjunto de dados e divisão entre treino e teste.
- `src/`: código utilizado para treinamento do modelo.
- `models/`: modelos treinados.
- `metrics/`: métricas dos experimentos.
- `reports/`: relatório de comparação dos modelos.

## Pré-requisitos

É necessário ter instalado:

- Git
- Python
- DVC

## Configuração do armazenamento DVC

O armazenamento local utilizado neste projeto está localizado na pasta `dvc-storage`, separada do repositório Git.

Para configurar o armazenamento local, execute:

```powershell
dvc remote add -d storage ../dvc-storage