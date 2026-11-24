# Comparação entre os Modelos

## 1. Correção dos dados

Durante a atividade, foi identificada uma inconsistência no rótulo do chamado de ID 006, que estava classificado como `comum`, mas deveria ser classificado como `urgente`.

A correção foi realizada na branch `correcao-rotulo`, gerando a segunda versão dos dados (`dados-v2`). A primeira versão dos dados foi preservada, permitindo comparar os modelos treinados antes e depois da correção.

## 2. Comparação dos modelos

Foram treinados dois modelos utilizando o mesmo conjunto de divisão entre treino e teste.

| Métrica | Modelo r1 | Modelo r2 |
|---|---:|---:|
| Versão dos dados | dados-v1 | dados-v2 |
| Acurácia | 0.75 | 1.00 |
| Recall - comum | 1.00 | 1.00 |
| Recall - urgente | 0.50 | 1.00 |

O modelo r1 apresentou acurácia de 75%, enquanto o modelo r2 alcançou 100%. Além disso, o recall da classe urgente aumentou de 50% para 100%, indicando uma melhora na identificação dos chamados urgentes após a correção do rótulo.

O recall da classe comum permaneceu em 100% nos dois modelos.

## 3. Verificação da restauração

Foi realizada a clonagem do repositório em um diretório separado, denominado `aula-ml-restauracao`, para verificar se era possível restaurar uma versão anterior dos dados e do modelo.

A tag `modelo-r1` foi selecionada e os arquivos versionados pelo DVC foram restaurados utilizando o comando `dvc pull`.

O commit restaurado foi:

`7fd13777e533eee620fc7c69a50acd1d711cb18b`

Os hashes SHA-256 dos arquivos restaurados foram:

| Arquivo | SHA-256 |
|---|---|
| `data/chamados.csv` | `abbead0c669e9ebb58d5453321061c21eda5db454a60f504e32c2effb10cd52f` |
| `data/split.csv` | `a543f066e63278bf40d73dcb0cf6b523f949fdeeb2469155c008a9416d0c10f2` |
| `models/model.json` | `72a3a67936139a3473838a6dcfa7aae1acb4c23467be1ef1056d51d485b94840` |

A verificação dos hashes confirmou que os arquivos restaurados correspondem exatamente aos arquivos da versão selecionada.

## 4. Decisão sobre o modelo

O modelo r2 foi escolhido como a versão mais adequada, pois apresentou melhores resultados nas métricas avaliadas, principalmente no recall da classe urgente, que passou de 0.50 para 1.00.

Essa melhoria é importante porque a identificação incorreta de chamados urgentes pode comprometer a prioridade de atendimento. Portanto, a correção do rótulo contribuiu para melhorar o desempenho do modelo nos dados avaliados.

## 5. Conclusão

A atividade demonstrou a importância do versionamento de dados e modelos utilizando Git e DVC. Foi possível preservar versões anteriores, registrar alterações nos dados, treinar novos modelos, comparar resultados e restaurar uma versão específica em um ambiente separado.

O processo também permitiu verificar a integridade dos arquivos restaurados por meio dos hashes SHA-256, garantindo a reprodutibilidade dos experimentos.
