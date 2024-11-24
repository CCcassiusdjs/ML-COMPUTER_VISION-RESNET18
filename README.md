# README

## Classificação de Imagens Astronômicas usando CNNs e Otimização com Optuna

### **Autores**
- **Arthur Gil dos Santos** - **a.gil@edu.pucrs.br** - 20101221  
- **Cássio Jones Dhein da Silva** - **c.jones@edu.pucrs.br** - 22180214  
- **Eduardo Cardoso** - **eduardo.spode01@edu.pucrs.br** - 20102745  
- **Lucas Bromberg Antunes** - **lucas.antunes@edu.pucrs.br** - 20103332  
- **Nicolle Canceri Lumertz** - **nicolle.lumertz@edu.pucrs.br** - 20103640  
- **Rafael Schaker Kopczynski da Rosa** - **rafael.schaker01@edu.pucrs.br** - 20107315  

---

## **Descrição do Projeto**
Este projeto tem como objetivo criar, treinar e avaliar um modelo baseado em **Redes Neurais Convolucionais (CNNs)** para classificar imagens astronômicas, utilizando a arquitetura **ResNet18** pré-treinada como base. O projeto também inclui a otimização de hiperparâmetros usando a biblioteca **Optuna** para maximizar o desempenho do modelo.

O fluxo completo abrange:
1. Pré-processamento e validação dos dados.
2. Configuração e treinamento do modelo CNN.
3. Avaliação do modelo em métricas como **acurácia**, **F1-score**, **precisão** e **recall**.
4. Otimização de hiperparâmetros utilizando **Optuna**.

---

## **Estrutura do Projeto**
- **`AOI.ipynb`**: Notebook principal contendo todas as etapas de desenvolvimento do modelo, treinamento, avaliação e otimização.
- **`README.md`**: Este arquivo, que fornece uma visão geral do projeto.
- **`data/`**: Diretório contendo o dataset utilizado para treinar e avaliar o modelo.
- **`requirements.txt`**: Arquivo de texto contendo lista de pacotes necessários...

---

## **Datasets Utilizados**
O dataset utilizado neste projeto é o **SpaceNet FLARE**, um conjunto de imagens astronômicas organizadas em classes. O dataset foi obtido via **Kaggle**.

**Características principais do dataset:**
- Classes: 8 classes de imagens astronômicas.
- Estrutura: As imagens estão organizadas em subpastas nomeadas com o rótulo correspondente.
- Formato: `.jpg` ou `.png`.

**Download e Preparo do Dataset:**
- O dataset pode ser obtido automaticamente pelo script, desde que o **Kaggle API** esteja configurado.

---

## **Pré-requisitos**
### **Versão do Python**: 3.8 ou superior

### **Bibliotecas Necessárias**
As bibliotecas utilizadas no projeto são:

```bash
pip install -r requirements.txt
```

---

## **Instruções para Execução**
1. **Clonar ou baixar o repositório**:
   ```bash
   git clone https://github.com/CCcassiusdjs/ML-COMPUTER_VISION-RESNET18.git
   cd ML-COMPUTER_VISION-RESNET18
   ```

2. **Configurar o dataset**:
   Certifique-se de que o dataset está na pasta `data/`. O script automaticamente verifica e baixa o dataset caso necessário.

3. **Executar o notebook**:
   Abra e execute sequencialmente o notebook `AOI.ipynb`.

---

## **Etapas do Projeto**

### **1. Pré-processamento de Dados**
- Validação e remoção de imagens corrompidas.
- Redimensionamento das imagens para 150x150 pixels.
- Normalização baseada em estatísticas do **ImageNet**.

### **2. Criação do Modelo**
- Utilizamos a **ResNet18** pré-treinada.
- Personalizamos a camada fully connected:
  - Adicionamos camadas ocultas com função de ativação ReLU e Dropout.
  - Ajustamos a saída para 8 classes.

### **3. Treinamento**
- Configuramos a função de perda (**CrossEntropyLoss**) e o otimizador (**Adam**).
- Implementamos **early stopping** para evitar overfitting.

### **4. Avaliação**
- Métricas calculadas:
  - **Acurácia**
  - **F1-Score**
  - **Precisão**
  - **Recall**
- Visualizações geradas:
  - **Matriz de Confusão**
  - **Curva ROC**
  - **Curva de Precisão-Recall**

### **5. Otimização de Hiperparâmetros**
- Hiperparâmetros otimizados com **Optuna**:
  - Número de unidades ocultas.
  - Taxa de dropout.
  - Taxa de aprendizado.
- Configurações que minimizam a perda de validação são salvas.

---

## **Resultados Esperados**
Após a execução, espera-se um modelo capaz de:
- Classificar imagens astronômicas com alta acurácia.
- Demonstrar equilíbrio entre precisão e recall.
- Utilizar hiperparâmetros otimizados para maximizar o desempenho.