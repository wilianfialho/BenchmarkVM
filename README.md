![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge) ![GitHub Org's stars](https://img.shields.io/github/stars/wilianfialho?style=social)

<h1 align="center"> # BenchmarkVM </h1>
> :construction: Projeto em Desenvolvimento :construction:

Este código é utilizado para a medição de recursos de máquinas virtuais. Ele utiliza a biblioteca libvirt para conectar-se ao host e obter informações sobre as VMs especificadas.

As informações coletadas incluem o nome da VM, horário da medição, tempo de CPU, tempo de sistema, tempo de usuário, memória alocada, memória não utilizada, memória disponível, memória usável e caches de disco.

O código salva esses dados em um arquivo CSV, com o nome "benchmark.csv". A medição de recursos é realizada por um período de tempo especificado (em segundos) e o intervalo entre medições também pode ser especificado.

Para usar o código, basta especificar os nomes das VMs desejadas na lista vm_names e configurar o tempo de medição e o intervalo de medição. Depois, basta executar o código e verificar o arquivo "benchmark.csv" para os resultados.


# :hammer: Funcionalidades do BenchmarkVM

- `Funcionalidade 1`: Medição de estatísticas de desempenho de máquinas virtuais (VMs) com o nome listado em "vm_names".
- `Funcionalidade 2`: Escrita dos resultados em um arquivo CSV.
- `Funcionalidade 3`: Intervalo de tempo da medição é especificado em "measurement_time".
- `Funcionalidade 3a`: Intervalo entre medições é especificado em "measurement_interval".
- `Funcionalidade 4`: As estatísticas coletadas incluem: nome da VM, horário de medição, tempo de CPU, tempo de sistema, tempo de usuário, memória alocada, memória não utilizada, memória disponível, memória usável, e caches de disco.



# 🖥️ Tecnologias Utilizadas

- `LibVirt`
- `CSV`
- `Python`
- `DateTime`
- `Time`


# 🛠️ Abrir e rodar o projeto

- Instalar o Python na versão necessária para este projeto.

- Instalar a biblioteca libvirt, que é utilizada para se conectar ao hipervisor.

- Clonar o repositório do código do projeto do Github.

- Abrir o terminal na pasta do projeto.

- Executar o arquivo de script Python (nome do arquivo é o mesmo do código apresentado acima).

- Verificar o arquivo CSV gerado com o nome "benchmark.csv", que contém as informações coletadas das VMs.
