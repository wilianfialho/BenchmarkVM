![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge) ![GitHub Org's stars](https://img.shields.io/github/stars/wilianfialho?style=social)
![BenchmarkVM](https://user-images.githubusercontent.com/4766326/219923377-574378a5-6a3d-4064-9616-1fbdf0c3ce4d.png)

<h1 align="center"> BenchmarkVM </h1>
> :construction: Projeto em Desenvolvimento :construction:

BenchmarkVM é uma ferramenta para medir o desempenho de máquinas virtuais (VMs) utilizando a biblioteca `libvirt`. O projeto coleta estatísticas detalhadas sobre o uso de CPU, memória e disco das VMs especificadas e oferece uma interface gráfica para monitoramento em tempo real.

## :hammer: Funcionalidades

- **Medição de Estatísticas**: Coleta dados de desempenho das VMs, incluindo:
  - Nome da VM
  - Horário da medição
  - Tempo de CPU, sistema e usuário
  - Memória alocada, não utilizada, disponível, usável e caches de disco
  - Espaço em disco alocado e livre, além de leituras e escritas de disco

- **Escrita em CSV**: Salva os resultados em um arquivo CSV chamado "benchmark.csv".

- **Monitoramento em Tempo Real**: Permite iniciar e parar o monitoramento em tempo real através de uma interface gráfica com o Tkinter, mostrando o progresso em uma barra de progresso.

- **Alertas de Recursos**: Verifica se o uso de CPU ou memória ultrapassa os limites especificados e envia alertas.

## 🖥️ Tecnologias Utilizadas

- **LibVirt**: Biblioteca para interagir com o hipervisor.
- **CSV**: Para armazenamento dos dados coletados.
- **Python**: Linguagem de programação usada para o script.
- **Tkinter**: Biblioteca para a interface gráfica.
- **DateTime**: Para manipulação e formatação de datas e horas.
- **Time**: Para controle de intervalos e temporização.

## 🛠️ Como Rodar o Projeto

1. **Instalar Python**: Certifique-se de que o Python está instalado na sua máquina. É recomendado usar Python 3.7 ou superior.

2. **Instalar Dependências**:
   - Instale a biblioteca `libvirt` usando o comando:
     ```bash
     pip install libvirt-python
     ```

3. **Clonar o Repositório**:
   - Clone o repositório do projeto do GitHub:
     ```bash
     git clone https://github.com/seu-usuario/benchmarkvm.git
     ```
   - Navegue para o diretório do projeto:
     ```bash
     cd benchmarkvm
     ```

4. **Executar o Script**:
   - Execute o script Python para iniciar o monitoramento:
     ```bash
     python nome_do_arquivo.py
     ```
   - Substitua `nome_do_arquivo.py` pelo nome real do arquivo Python.

5. **Verificar Resultados**:
   - Após a execução, verifique o arquivo "benchmark.csv" na pasta do projeto para visualizar as informações coletadas.

## 📷 Exemplo de Uso

1. **Configuração**: Edite a lista `vm_names` com os nomes das VMs que deseja monitorar, e ajuste `measurement_time` e `measurement_interval` conforme necessário.

2. **Interface Gráfica**: Use a interface gráfica fornecida para iniciar e parar o monitoramento em tempo real. A barra de progresso exibirá o andamento do monitoramento.

## :warning: Avisos

- Certifique-se de que as VMs estão configuradas corretamente e que a conexão com o hipervisor está funcionando.
- Os limites de uso de CPU e memória são exemplos e podem ser ajustados conforme a necessidade.
