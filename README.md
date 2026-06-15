<h1>🌱 AgroScan AI</h1>
<p>Diagnóstico Automatizado de Fitopatologias</p>

<div class="card">
    <h2>📌 Descrição do Projeto</h2>
    <p>
        O <b>AgroScan AI</b> é um sistema inteligente de apoio à decisão agrícola desenvolvido com técnicas de <b>Inteligência Artificial</b> para identificação automática de doenças em folhas de plantas.
    </p>
    <p>O sistema permite que o usuário envie uma imagem de uma folha e receba uma análise automática contendo:</p>
    <ul class="lista">
        <li>Diagnóstico detectado</li>
        <li>Explicação da decisão da IA</li>
        <li>Recomendação de manejo</li>
        <li>Grau de confiança da predição</li>
    </ul>
    <div class="objetivo">
        <b>Objetivo:</b> Auxiliar no reconhecimento inicial de fitopatologias, oferecendo suporte para tomada de decisão no ambiente agrícola.
    </div>
</div>

<div class="card">
    <h2>📂 Dataset Utilizado</h2>
    <p>
        <b>Dataset utilizado no treinamento:</b><br>
        PlantVillage Dataset
    </p>
    <div class="link">
        🔗 <a href="https://www.kaggle.com/datasets/emmarex/plantdisease" target="_blank">Acessar Dataset</a>
    </div>
    <br>
    <p>O conjunto contém imagens de folhas saudáveis e infectadas por diferentes doenças agrícolas.</p>
    <p><b>Classes utilizadas:</b></p>
    <ul class="lista">
        <li>🌶️ Pimentão (Pepper bell)</li>
        <li>🥔 Batata (Potato)</li>
        <li>🍅 Tomate (Tomato)</li>
    </ul>
</div>

<div class="card">
    <h2>🧠 Arquitetura de IA (Em Cascata)</h2>
    <p>Para garantir a confiabilidade dos diagnósticos, o sistema utiliza dois modelos <b>YOLO</b> trabalhando em conjunto:</p>
    <ol class="lista">
        <li><b>Filtro Validador (best_nao_folha.pt):</b> Analisa se a imagem enviada é realmente uma folha (classes: <code>leaf</code> e <code>non-leaf</code>). Se o objeto for inválido, a análise é interrompida.</li>
        <li><b>Modelo de Diagnóstico (best.pt):</b> Uma vez validada como folha, este modelo identifica a cultura e a presença de eventuais fitopatologias.</li>
    </ol>
</div>

<div class="card">
    <h2>🛠️ Pré-requisitos e Instalação</h2>
    <p>Certifique-se de ter o <b>Python 3.8+</b> instalado em sua máquina. Siga os passos abaixo para configurar o ambiente:</p>
    
    git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio</code></pre>

    pip install streamlit ultralytics pillow</code></pre>
</div>

<div class="card">
    <h2>🚀 Como Executar o Sistema</h2>
    <p>Com os arquivos dos modelos de pesos (<code>best.pt</code> e <code>best_nao_folha.pt</code>) na raiz do projeto, execute o comando:</p>
    <pre><code>streamlit run app.py</code></pre>
    <p>A aplicação será iniciada e abrirá automaticamente no seu navegador padrão (geralmente no endereço <code>http://localhost:8501</code>).</p>
</div>

<div class="card">
    <h2>💻 Tecnologias Utilizadas</h2>
    <ul class="lista">
        <li><b>Python</b> — Linguagem base do sistema.</li>
        <li><b>Streamlit</b> — Framework utilizado para a criação da interface web interativa.</li>
        <li><b>YOLO (Ultralytics)</b> — Modelo de Deep Learning para a classificação e validação das imagens.</li>
        <li><b>Pillow (PIL)</b> — Biblioteca para manipulação e padronização geométrica das imagens.</li>
    </ul>
</div>

<hr>
<p align="center"><small>AgroScan AI © 2026</small></p>
