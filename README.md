<h1>🌱 AgroScan AI</h1>
<p>Diagnóstico Automatizado de Fitopatologias</p>

---

## 📌 Descrição do Projeto
O **AgroScan AI** é um sistema inteligente de apoio à decisão agrícola desenvolvido com técnicas de **Inteligência Artificial** (utilizando modelos YOLO da Ultralytics) para a identificação automática de doenças em folhas de plantas.

O sistema opera com uma arquitetura de **modelos em cascata**:
1. **Filtro de Rejeição (Validador):** Analisa a imagem para garantir que se trata de uma folha válida (`leaf` ou `non-leaf`). Se o objeto não for uma folha, a análise é interrompida imediatamente para evitar diagnósticos inconsistentes.
2. **Modelo de Diagnóstico:** Caso a imagem seja validada com sucesso, o segundo modelo entra em ação para identificar a fitopatologia específica e calcular o grau de certeza.

O usuário envia a foto e recebe instantaneamente:
* 📋 Status do diagnóstico detalhado.
* 🔍 Explicação visual baseada nos sintomas detectados.
* ⚠️ Plano de ação/recomendação de manejo específico.
* 📈 Grau de confiança da predição com barra de progresso.

---

## 📂 Datasets Utilizados

O desenvolvimento e o treinamento dos modelos foram realizados utilizando duas bases de dados públicas:

1. **Classificação de Imagem (Filtro de Rejeição):**
   * **Leaf vs Non-Leaf Images Dataset** — Utilizado para treinar o modelo validador a distinguir folhas de outros objetos cotidianos ou cenários de fundo. (Disponível no [Kaggle](https://www.kaggle.com/datasets/robiulhasanjisan/leaf-vs-non-leaf-images))

2. **Detecção e Diagnóstico de Doenças:**
   * **PlantVillage Dataset** — Utilizado para treinar o modelo principal na identificação de folhas saudáveis e infectadas por patógenos específicos. (Disponível no [Kaggle](https://www.kaggle.com/datasets/emmarex/plantdisease))

### Culturas Suportadas pelo Sistema:
* 🌶️ **Pimentão** 
* 🥔 **Batata** 
* 🍅 **Tomate** 

---

## 🛠️ Tecnologias e Dependências
O ecossistema do projeto foi construído utilizando:
* **Python** (Linguagem base)
* **Streamlit** (Interface Web interativa e responsiva)
* **Ultralytics (YOLO)** (Processamento das redes neurais de visão computacional)
* **Pillow (PIL)** (Manipulação e padronização de imagens)

---

## 🚀 Como Executar no Google Colab


Acesse:

https://colab.research.google.com

e faça upload do arquivo:

- `Diagnostico_de_Plantas.ipynb`

---

## 2. Ativar GPU (Opcional, mas recomendado)

No menu:

```text
Ambiente de execução → Alterar tipo de ambiente de execução → GPU
```

Clique em **Salvar**.

---

## 3. Fazer upload dos modelos

No painel lateral esquerdo do Colab:

1. Clique no ícone de pasta 📁
2. Clique em **Upload**
3. Envie os arquivos:

```text
best.pt
best_nao_folha.pt
```

Os arquivos devem aparecer na pasta principal do Colab.

---

## 4. Instalar as dependências

Execute uma célula com:

```python
!pip install ultralytics streamlit pillow
```

---

## 5. Executar o notebook

Clique em:

```text
Ambiente de execução → Executar tudo
```

ou execute as células uma a uma.

O notebook carregará os modelos:

```python
best.pt
best_nao_folha.pt
```

e criará o arquivo `app.py`.

---

## 6. Executar a aplicação Streamlit

Após a criação do arquivo `app.py`, execute:

```python
!streamlit run app.py &>/content/logs.txt &
```

---

## 7. Criar acesso externo

Execute:

```python
!npm install -g localtunnel
```

Depois:

```python
!lt --port 8501
```

Será exibido um link semelhante a:

```text
https://xxxx.loca.lt
```

Abra esse link no navegador para acessar o sistema.

---

## Estrutura Final dos Arquivos

```text
/
├── Diagnostico_de_Plantas.ipynb
├── best.pt
├── best_nao_folha.pt
├── app.py
```

## Funcionamento

1. O usuário envia uma imagem.
2. O modelo `best_nao_folha.pt` verifica se a imagem contém uma folha.
3. Se a imagem for válida, o modelo `best.pt` realiza o diagnóstico.
4. O resultado é exibido na interface Streamlit.
