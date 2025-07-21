# Detecção de Sinais de Trânsito Alemães com HOG e SVM

Este projeto implementa um pipeline clássico de visão computacional para **detecção de sinais de trânsito** utilizando o dataset [German Traffic Sign Detection Benchmark (GTSDB)](https://www.kaggle.com/datasets/safabouguezzi/german-traffic-sign-detection-benchmark-gtsdb?resource=download-directory). O objetivo é localizar sinais de trânsito em imagens reais de estradas, simulando um cenário de carro autônomo.

## Objetivo

Desenvolver e aprimorar um sistema capaz de identificar e localizar sinais de trânsito em ambientes rodoviários complexos, utilizando técnicas tradicionais de processamento de imagem e aprendizado de máquina.

## Etapas do Projeto

1. **Download do Dataset**
   - Utiliza o [KaggleHub](https://github.com/kagglehub/kagglehub) para baixar o dataset: `safabouguezzi/german-traffic-sign-detection-benchmark-gtsdb`.
   - Estrutura esperada: imagens e anotações (bounding boxes) para treino e teste.

2. **Extração de Características**
   - Utiliza o descritor **HOG (Histogram of Oriented Gradients)** para transformar regiões das imagens em vetores de características.

3. **Treinamento do Classificador**
   - Treina um classificador **SVM (Support Vector Machine)** para distinguir entre "sinal de trânsito" e "fundo".

4. **Detecção de Objetos**
   - Implementa **Janela Deslizante (Sliding Window)** e **Pirâmide de Imagens (Image Pyramid)** para localizar sinais em múltiplas escalas.
   - Aplica **Non-Maximum Suppression (NMS)** para eliminar detecções redundantes.

5. **Hard Negative Mining**
   - Minera amostras negativas difíceis (falsos positivos) e re-treina o modelo para aumentar a precisão.

6. **Ajuste Fino**
   - Refina hiperparâmetros como limiar de confiança e sobreposição para otimizar o equilíbrio entre precisão e revocação.

## Principais Resultados

- **Modelo Base (V1):** Alta revocação, mas muitos falsos positivos.
- **Modelos V2/V3 (Hard Negative Mining):** Redução drástica de falsos positivos e aumento da robustez.
- **Modelo V4 (Refinado):** Ajuste fino dos parâmetros, eliminando falsos positivos residuais.

## Como Executar

1. Instale as dependências:
   ```
   pip install kagglehub scikit-image scikit-learn opencv-python matplotlib numpy imutils pandas
   ```
2. Baixe o dataset do Kaggle conforme instruções do notebook.
3. Execute o notebook [projeto_German_Traffic_Sign_Detection_Benchmark.ipynb](Projeto_VCAP_GTSDB/projeto_German_Traffic_Sign_Detection_Benchmark.ipynb) em ambiente Jupyter.

## Requisitos

- Python 3.7+
- kagglehub
- scikit-image
- scikit-learn
- opencv-python
- matplotlib
- numpy
- imutils
- pandas

## Autor

Projeto desenvolvido por Marcos Vinicius da Silva para estudo de detecção de padrões visuais em sinais de trânsito.