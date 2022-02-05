---
jupyter:
  jupytext:
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.13.6
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

O NameNode, armazena os metadados dos arquivos (componente central do HDFS)

```python

```

# Apache Hadoop


"O projeto Apache™ Hadoop® desenvolve software de código aberto para computação distribuída confiável, escalável.
A biblioteca de software Apache Hadoop é uma estrutura que permite o processamento distribuído de grandes conjuntos de dados em clusters de computadores usando modelos de programação simples. Ele foi projetado para escalar de servidores únicos para milhares de máquinas, cada uma oferecendo computação e armazenamento locais. Em vez de depender de hardware para fornecer alta disponibilidade, a própria biblioteca foi projetada para detectar e lidar com falhas na camada de aplicação, fornecendo um serviço altamente disponível em um cluster de computadores, cada um dos quais pode estar propenso a falhas."

https://hadoop.apache.org/


```python

```

# Dados


Pensando na taxa de crescimento dos dados, como os dados foram armazenados, processados, consultados e analisados?
Arquitetura montada é escalável?


# Categorias


Pensando em Big Data, precisamos considerar: Volume, Velocidade, Variedade, Veracidade, Valor, Variabilidade, 
Validade, Vulnerabilidade, Volatilidade e Visualização...


# Arquitetura


Crescimento Vertical (tecnologia) ou Horizontal (equipamentos)? em Big Data usamos arquitetura Horizontal 
* Armazenar, processar e analizar os dados.


### HDFS

O Hadoop armazena os dados no HDFS, dividindo os dados em blocos de 128MB. (Ex. um aquivo de 500 MB seria dividido em 3 partes de 128Mb e um bloco teria 116MB) e cada bloco será armazenado em 3 cópias.

### Arquitetura Mestre (NameNode) / Escravo (DataNode)

* O NameNode, armazena os metadados dos arquivos (componente central do HDFS)
* O DataNode, armazena os dados


### Map Reduce


MapReduce é o responsável pelo processamento. Recebe uma tarefa, divide em blocos, que são um conjunto de tarefas independentes,que vão realizar vários processos. (Split, Map, Shuffle e Reduce)

Quando um job é executado, o Jobtracker agenda, monitora e coordena todas as tarefas executadas no sistema e os vários Tasktracker, executam as tarefas e enviam relatórios de progresso para o Jobtracker. 

Quando um Job é executado  em um cluster HDFS o Namenode, armazena os metadados e os Datanodes armazenam os dados que serão copiados em 3 nós de forma distribuída. Os Jobs de Map Reduce são executados, no processamento o Jobtracker agenda, monitora e coordena todas as tarefas executadas e os Tasktracker, executam as tarefas e enviam relatórios de progresso ao Jobtracker.

O HDFS é o responsável pelo armazenamento e o Map Reduce pelo processamento dos dados.




# Yarn

É um gerenciador de recursos que oferece paralelismo de tarefas, divide as funcionalidades de gerenciamento de recursos e agendamento/ monitoramento de tarefas em daemons separados.

É uma evolução implementada no Hadoop 2 

```python

```
