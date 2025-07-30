# Desafio Técnico – Processo Seletivo para Analista de Inteligência Artificial

Este projeto demonstra um pipeline de processamento de vídeo e áudio para análise de cena e classificação de objetos, utilizando técnicas de visão computacional e machine learning.

## Descrição do Projeto

O objetivo deste projeto é extrair frames de um vídeo, processá-los para análise visual, extrair o áudio para transcrição e, finalmente, classificar objetos presentes nas cenas utilizando um modelo de aprendizado de máquina. O pipeline inclui as seguintes etapas:

1.  **Separação de Vídeo e Áudio:** Utiliza FFmpeg para separar a trilha de vídeo e a trilha de áudio de um arquivo de vídeo de entrada.
2.  **Extração e Armazenamento de Frames:** Extrai frames do vídeo (sem áudio) em intervalos regulares, salva cada frame no formato FITS com metadados e armazena os metadados em um banco de dados SQLite local.
3.  **Análise e Processamento de Imagens:** Lê as imagens FITS do armazenamento, calcula e plota seus histogramas, aplica equalização de histograma para melhorar o contraste e salva as imagens equalizadas.
4.  **Classificação com Machine Learning:** Utiliza um classificador SVM (Support Vector Machine), uma técnica de **aprendizado supervisionado**, para classificar os objetos. As **features visuais** para o treinamento são extraídas com uma rede neural **ResNet pré-treinada**, e os **rótulos (labels) dos frames foram definidos manualmente** com base em faixas de tempo onde cada objeto aparece predominantemente.
5.  **Análise de Áudio:** Transcreve o áudio extraído utilizando um modelo de Automatic Speech Recognition (ASR).
6.  **Detecção de Objetos (Opcional/Alternativa):** Demonstra a detecção de objetos utilizando um modelo pré-treinado (Faster R-CNN) em frames do vídeo.

## Tecnologias Utilizadas

*   **FFmpeg:** Processamento de vídeo e áudio (separação).
*   **OpenCV (`cv2`):** Extração e processamento de frames, desenho em imagens.
*   **Astropy (`astropy.io.fits`):** Manipulação de arquivos FITS.
*   **SQLite (`sqlite3`):** Banco de dados local para metadados.
*   **NumPy:** Manipulação de arrays numéricos.
*   **Matplotlib:** Visualização (histogramas, plots).
*   **PyTorch:** Carregamento e utilização de modelos de Deep Learning pré-treinados (ResNet18, Faster R-CNN).
*   **Scikit-learn (`sklearn`):** Treinamento e avaliação do modelo de classificação (SVM).
*   **Transformers (Hugging Face):** Transcrição de áudio (ASR).

## Como Configurar e Executar o Projeto

Para configurar e executar este projeto, siga os passos abaixo:

1.  **Clone o Repositório:**
```bash
git clone https://github.com/thiagoribeiro00/artificial_intelligence_analyst-_challenge.git
cd artificial_intelligence_analyst-_challenge
```

2.  **Crie e Ative um Ambiente Virtual:**
```bash
        python -m venv .venv
        source .venv/bin/activate  # No Windows use `.venv\Scripts\activate`
```
2. **Instalar as Dependencias:**
```
    pip install -r requirements.txt
```
