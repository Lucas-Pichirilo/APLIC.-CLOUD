
### **Sistema de Monitoramento IoT para Estacionamento com Identificação de Veículos**

#### **Objetivo do Projeto**
O objetivo deste projeto é criar um sistema inteligente de monitoramento para estacionamentos utilizando IoT (Internet das Coisas). O sistema visa automatizar a identificação de veículos, classificando-os em carros ou motos, e fornecendo informações em tempo real sobre o status de ocupação das vagas.

#### **Como o Sistema Funciona**
O sistema funciona com base em uma câmera instalada na entrada do estacionamento. Ao captar a imagem de um veículo que está entrando, o software processa a imagem e utiliza um modelo de aprendizado profundo para identificar se o veículo é um **carro** ou uma **moto**.

- **Câmera**: A câmera captura as imagens dos veículos à medida que entram no estacionamento.
- **Processamento de Imagem**: As imagens são enviadas para um modelo pré-treinado que faz a classificação.
- **Classificação**: O modelo identifica se o veículo é um carro ou uma moto com base em características visuais.
- **Atualização em Tempo Real**: O sistema atualiza as informações de ocupação, exibindo o número de vagas disponíveis para cada tipo de veículo.

#### **Tecnologia Utilizada**
- **Keras e TensorFlow**: As bibliotecas de aprendizado de máquina Keras e TensorFlow são utilizadas para carregar e executar o modelo de classificação de imagens.
- **Python**: Linguagem principal do sistema, responsável pelo processamento de dados e integração com a câmera e o modelo de IA.
- **IoT**: Conectividade em tempo real entre os sensores da câmera e o sistema central de monitoramento, possibilitando o acompanhamento do fluxo de veículos.
- **Hardware**: Câmeras de vigilância conectadas ao sistema, além de servidores para processamento dos dados.

#### **Benefícios do Sistema**
- **Automação e Precisão**: O uso de câmeras com reconhecimento de imagem elimina a necessidade de monitoramento manual, aumentando a precisão.
- **Gestão Eficiente do Estacionamento**: O sistema permite a distribuição de vagas de maneira mais eficaz, reservando áreas específicas para carros ou motos.
- **Relatórios em Tempo Real**: Informações instantâneas sobre a ocupação do estacionamento permitem ajustes rápidos na operação e ajudam os gestores a prever a demanda.
  
#### **Aplicações Finais**
O projeto pode ser implementado em diferentes tipos de estacionamentos, como:
- **Shoppings e centros comerciais**: Facilita o direcionamento de veículos para áreas com vagas disponíveis.
- **Estacionamentos de grandes empresas**: Auxilia no controle interno do fluxo de veículos de funcionários.
- **Aeroportos e rodoviárias**: Torna a entrada e saída de veículos mais eficiente, com menor congestão.

#### **Integrantes**
- Lucas Kaua Pichirilo Lima


