<img width="1338" height="338" alt="Captura de tela 2026-06-22 111430" src="https://github.com/user-attachments/assets/d7b2d011-3cf0-4310-acc3-c294157c3284" />


### Descrição do projeto

Este trabalho foi desenvolvido para o projeto final da disciplina de Prática em Ciência de Dados. Ele aplica regressão linear a dados de biomarcadores (CA-125, HE4, CEA, CA 19-9 e AFP) para modelar a relação entre seus níveis e o risco de câncer de ovário. Para cada biomarcador, ajusta-se uma função do tipo risco = a·x + b e os resultados são combinados, com pesos proporcionais à relevância clínica de cada marcador, em um modelo de classificação automática nas categorias normal, baixo, moderado e alto risco. O trabalho inclui ainda visualizações gráficas dos modelos ajustados e tem caráter didático, utilizando dados simplificados para ilustrar a aplicação prática da regressão linear em contextos biomédicos.


### Instalação e instruções

Para executar o projeto, é necessário ter o Python 3.3.7 instalado, bem como as bibliotecas numpy, matplotlib, scikit-learn e jupyter, que podem ser instaladas com o comando pip install numpy matplotlib scikit-learn jupyter. Em seguida, basta abrir o arquivo Projeto_Final.ipynb pelo Jupyter Notebook, executar todas as células em ordem. Para avaliar um novo paciente, basta inserir seus valores laboratoriais de cada biomarcador na função avaliar_paciente, localizada no bloco final do notebook, e o sistema classificará automaticamente o nível de risco e exibirá os gráficos correspondentes.


### Tecnologias utilizadas

- Python: Linguagem de programação utilizada como base de todo o projeto.
- Jupyter Notebook: Ambiente de desenvolvimento interativo no qual o projeto foi desenvolvido e documentado.
- Math: Módulo nativo do jupyter lab utilizado especificamente pela função ceil, que calcula o número de linhas necessárias no grid de subgráficos com base na quantidade de biomarcadores.
- Numpy: Biblioteca responsável pela manipulação de arrays numéricos e operações vetorizadas. Utilizada para estruturar os dados de treinamento de cada biomarcador, realizar cálculos de risco e aplicar a função np.clip, que limita os valores previstos ao intervalo [0, 1].
- Matplotlib: Biblioteca de visualização gráfica usada para gerar todos os gráficos do projeto — dispersão, regressão linear, barras e pizza. Também foi utilizada para configurar a espessura das hachuras nos gráficos de pizza e para personalizar elementos visuais como zonas de fundo coloridas, legendas compartilhadas e formatação dos eixos.
- sklearn.linear_model: Biblioteca da qual foi utilizado o módulo LinearRegression, responsável pelo ajuste dos modelos de regressão linear. A partir dele, são extraídos os coeficientes a e b de cada biomarcador, bem como o coeficiente de determinação R² para avaliação da qualidade do ajuste.


### Funcionalidade

- Recebe o dicionário de biomarcadores e ajusta um modelo de regressão linear simples para cada um deles. Para cada biomarcador, extrai a função do tipo risco = a·x + b, onde a é o coeficiente angular (sensibilidade ao aumento do marcador) e b é o intercepto. Também calcula o R² de cada ajuste, indicando a qualidade do modelo. Retorna um dicionário com o modelo treinado e seus parâmetros.
- Recebe os valores medidos de um paciente e utiliza os modelos treinados para prever o risco individual de cada biomarcador. O risco previsto é limitado ao intervalo [0, 1] e comparado ao limiar (padrão 0,5): se igual ou superior, o marcador é considerado em risco. Cada previsão é multiplicada pelo peso clínico normalizado do marcador, e a soma dessas contribuições forma o risco ponderado total, que determina a classificação final em uma de quatro categorias: Normal (< 25%), Baixo risco (25–50%), Risco moderado (50–75%) ou Alto risco (≥ 75%).
- Gera automaticamente um painel de gráficos com um subgráfico para cada biomarcador. Em cada subgráfico são exibidos: os pontos de treinamento, a reta de regressão ajustada, zonas de fundo coloridas que delimitam as regiões de normalidade (verde, abaixo dos 50%) e risco (vermelho, acima do 50%), e uma estrela indicando a posição do paciente. A equação extraída e o R² aparecem em uma caixa com borda na cor do biomarcador.
- Gera dois gráficos complementares de resumo do paciente: um gráfico de barras mostrando o risco previsto por biomarcador (ordenado por peso clínico) e um gráfico de pizza mostrando a contribuição percentual de cada biomarcador para o risco ponderado total. Inclui hachuras diferenciadas para acessibilidade visual.
- Função auxiliar que centraliza o fluxo completo de avaliação de um paciente: chama classificar_paciente, imprime no console o risco previsto e o status de cada biomarcador, e em seguida gera os dois conjuntos de gráficos para avaliar perfis distintos (plotar_graficos e plotar_resumo_paciente).


### Professores

##### Daniel Roberto Cassar
Doutorado: Ciência e Engenharia de Materiais (UFSCar) - Pós-doutorado: UFSCar. Área de atuação: Informática dos materiais

##### James Moraes de almeida
Doutorado: Nanociências de Materiais Avançados (UFABC). Pós-Doutorado: UFABC, Ecole Polytechnique Fédérale de Lausanne, USP. Área de atuação: Computação de alto desempenho

##### Leandro Nascimento Lemos
Doutorado: Bioinformática e Ecologia de Microorganismos (USP). Pós-Doutorado: Laboratório Nacional de Computação Científica (LNCC), Unicamp e Universidade de Viena. Área de atuação: Bioinformática e Ecologia Numérica

### Autoria

Beatriz Pessoa de Souza discente do curso de bacharelado em ciência e tecnologia na Ilum Escola de Ciência.

### Referência

VILLELA-CASTREJON, Javier; LEVINE, Herbert; KAIPPARETTU, Benny A.; ONUCHIC, José N.; GEORGE, Jason T.; JIA, Dongya. "Computational modeling of cancer cell metabolism along the catabolic-anabolic axes", npj Systems Biology and Applications. Pubicado 10 maio 2025. Disponível em: https://www.nature.com/articles/s41540-025-00525-x. Acesso em: 13 maio 2026

CBIOPORTAL FOR CANCER GENOMICS. Atualizado em: 10 de abril 2026. Disponível em: https://www.cbioportal.org/ . Acesso em: 20 maio 2026.

GTEX PORTAL. Disponível em: https://www.gtexportal.org/home/. Acesso em: 20 maio 2026.

MATPLOTLIB. Pyplot tutorial. Disponível em: https://br.matplotlib.net/stable/tutorials/introductory/pyplot.html. Acesso em: 4 jun. 2026.

NUMPY. Disponível em: https://numpy.org/. Acesso em: 4 jun. 2026.

AZIZI, Tahmineh. Mathematical modeling of cancer progression. Públicado 2 setembro 2024. Disponível em: https://doi.org/10.3390/appliedmath4030057. Acesso em: 4 jun. 2026.

NATIONAL COMPREHENSIVE CANCER NETWORK (NCCN). Disponível em: https://www.nccn.org/. Acesso em: 17 jun. 2026

MICROSOFT. Copilot (modelo GPT-5). Orientações sobre uso de cores (HEX, RGB, nomes) e propriedades de fonte (fontweight) em gráficos no Python (matplotlib). Acesso em: 6 jun. 2026.
