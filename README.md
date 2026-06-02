🌱 AgroScan AI – Diagnóstico Automatizado de Fitopatologias
📌 Descrição do Projeto

O AgroScan AI é um sistema inteligente de apoio à decisão agrícola desenvolvido com técnicas de Inteligência Artificial, Redes Neurais Artificiais e Visão Computacional para identificação automática de doenças em folhas de plantas.

O sistema permite que o usuário envie uma imagem de uma folha e receba uma análise automática contendo:

Diagnóstico detectado;
Explicação da decisão da IA;
Recomendação de manejo;
Grau de confiança da predição.

O objetivo do projeto é auxiliar no reconhecimento inicial de fitopatologias, oferecendo suporte para tomada de decisão no ambiente agrícola.

📂 Dataset Utilizado

Dataset utilizado no treinamento:
PlantVillage Dataset

https://www.kaggle.com/datasets/emmarex/plantdisease

O conjunto contém imagens de folhas saudáveis e infectadas por diferentes doenças agrícolas.

Classes utilizadas incluem:
Pimentão
Batata
Tomate

▶️ Como executar o projeto

Instalar dependências

Execute:

```bash
pip install streamlit ultralytics pillow kagglehub pyngrok
```

Gerar acesso público

Configure o Ngrok:

```python
from pyngrok import ngrok

ngrok.set_auth_token("SEU_TOKEN")
```


Acessar o sistema

Abra a URL gerada no navegador.
