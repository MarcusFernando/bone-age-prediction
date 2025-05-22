# bone-age-prediction
Projeto de Deep Learning para estimativa da idade óssea a partir de imagens de raio-X
# Objetivo e Resumo do Projeto
Este projeto tem como objetivo desenvolver um modelo de Deep Learning (Rede Neural Convolucional - CNN) capaz de estimar a idade óssea de indivíduos a partir de imagens de raio-X da mão. O modelo foi treinado em um dataset de imagens de raio-X e busca fornecer uma estimativa precisa em meses.
# Requisitos e Configuração
Python 3.x
TensorFlow / Keras: Framework principal para o modelo de Deep Learning.
pandas: Manipulação e análise de dados.
numpy: Operações numéricas.
scikit-learn: Ferramentas para pré-processamento e métricas.
Pillow (PIL): Processamento de imagens.
matplotlib e seaborn: Visualização de dados (opcional, para análise).
instalação: pip install tensorflow pandas numpy scikit-learn pillow matplotlib seaborn
# Estrutura da Base de Dados
/content/
├── boneage-training-dataset/
│   ├── boneage-training-dataset/
│   │   ├── [IMAGENS_DE_TREINO].png
│   │   └── ...
│   └── boneage-training-dataset.csv
└── boneage-validation-dataset/
    ├── boneage-validation-dataset/
    │   ├── [IMAGENS_DE_VALIDACAO].png
    │   └── ...
    └── boneage-validation-dataset.csv
  Obs: para uso em produção, o conjunto de validação separado é crucial
 # Pré-processamento dos Dados
 As imagens e os dados foram pré-processados da seguinte forma:

Redimensionamento de Imagens: Todas as imagens foram redimensionadas para 224x224 pixels.
Normalização de Pixels: Os valores dos pixels das imagens foram normalizados para o intervalo [0, 1] (dividindo por 255.0).
Normalização da Idade Óssea: A idade óssea (em meses) foi normalizada usando MinMaxScaler para o intervalo [0, 1]. Os parâmetros (mínimo e máximo) do MinMaxScaler são essenciais para a desnormalização das previsões.
# Arquitetura do Modelo
Camadas convolucionais (Conv2D) para extração de características.
Camadas de MaxPooling2D para redução dimensional.
Camadas BatchNormalization para estabilização do treinamento.
Camadas Dropout para regularização e prevenção de overfitting.
Camada Flatten para transformar a saída convolucional em um vetor.
Camadas Dense (totalmente conectadas) para a predição final.
A saída do modelo é uma única camada densa com ativação linear, que prediz a idade óssea normalizada.


