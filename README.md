# Especialização "AI for Good"

Este repositório contém materiais e exercícios desenvolvidos durante a especialização "[AI for Good](https://www.deeplearning.ai/courses/ai-for-good/)", oferecida pelo **DeepLearning.AI** em parceria com o **Coursera**. A especialização demonstra o papel da inteligência artificial na criação de soluções para desafios globais críticos, como saúde pública, mudanças climáticas e gestão de desastres naturais.

## Índice

- [Sobre a Especialização](#sobre-a-especialização)
- [Configuração do Ambiente](#configuração-do-ambiente)
  - [Requisitos](#requisitos)
  - [Criando o Ambiente Conda](#criando-o-ambiente-conda)
  - [Instalando as Dependências](#instalando-as-dependências)
  - [Configurando o Kernel no Jupyter Notebook](#configurando-o-kernel-no-jupyter-notebook)
- [Projeto de Aprendizagem Aplicada](#projeto-de-aprendizagem-aplicada)
- [Cursos Incluídos](#cursos-incluídos)
  - [Curso 1: IA e Saúde Pública](#curso-1-ia-e-saúde-pública)
  - [Curso 2: IA e Mudanças Climáticas](#curso-2-ia-e-mudanças-climáticas)
  - [Curso 3: IA e Gestão de Desastres](#curso-3-ia-e-gestão-de-desastres)
- [Resultados Esperados e Impacto](#resultados-esperados-e-impacto)
- [Tecnologias e Ferramentas Utilizadas](#tecnologias-e-ferramentas-utilizadas)
- [Possíveis Extensões](#possíveis-extensões)
- [Demonstração e Visualização](#demonstração-e-visualização)
- [Contribuição para a Comunidade](#contribuição-para-a-comunidade)
- [Agradecimentos](#agradecimentos)
- [Contato](#contato)

## Sobre a Especialização

A especialização "AI for Good" destaca como a IA pode ser utilizada para enfrentar desafios significativos em áreas como saúde pública, mudanças climáticas e gestão de desastres. Ao longo dos cursos, você aprenderá com o instrutor [Robert Monarch](https://www.linkedin.com/in/robertjmunro/), que possui mais de 20 anos de experiência na construção de produtos de IA na indústria e no trabalho na interseção de IA, saúde pública e gestão de desastres. Robert também é autor do livro "Human-in-the-Loop Machine Learning", focado em aplicações de IA centradas no ser humano.

Durante os cursos, você ouvirá especialistas envolvidos em iniciativas de "AI for Good" que visam abordar questões sociais e ambientais. Ao combinar inteligência humana e de máquina, conjuntos de dados do mundo real, melhores práticas em privacidade de dados e considerações éticas, você desenvolverá o conhecimento e as habilidades fundamentais para enfrentar seus próprios projetos de "AI for Good".

## Configuração do Ambiente

Para garantir que outros usuários não enfrentem os mesmos problemas que eu encontrei ao configurar o ambiente, siga as instruções abaixo para configurar corretamente seu ambiente de desenvolvimento.

### Requisitos

- **Anaconda ou Miniconda**: Para gerenciamento de ambientes e pacotes.
- **Python 3.11**: Versão utilizada nos projetos.
- **Visual Studio Code (VS Code)**: Recomendado para edição e execução dos notebooks Jupyter.
- **Extensão Jupyter para VS Code**: Para suporte a notebooks dentro do VS Code.

### Criando o Ambiente Conda

1. **Abra o terminal** e certifique-se de que o Conda está instalado executando `conda --version`.

2. **Crie um novo ambiente** chamado `ai_env` com Python 3.11:

   ```bash
   conda create -n ai_env python=3.11
   ```

3. **Ative o ambiente**:

   ```bash
   conda activate ai_env
   ```

### Instalando as Dependências

Com o ambiente `ai_env` ativo, instale as bibliotecas necessárias:

1. **Atualize o Conda**:

   ```bash
   conda update conda
   ```

2. **Instale os pacotes principais** usando Conda:

   ```bash
   conda install numpy pandas scikit-learn matplotlib
   ```

3. **Instale pacotes adicionais do canal `conda-forge`**:

   ```bash
   conda install -c conda-forge folium shapely
   ```

4. **Instale pacotes que não estão disponíveis via Conda usando `pip`**:

   ```bash
   pip install colour
   ```

5. **Instale o kernel do IPython para Jupyter**:

   ```bash
   conda install ipykernel
   ```

6. **Registre o ambiente `ai_env` como um kernel Jupyter**:

   ```bash
   python -m ipykernel install --user --name ai_env --display-name "Python (ai_env)"
   ```

### Configurando o Kernel no Jupyter Notebook

Para garantir que os notebooks usem o ambiente correto:

1. **Abra o VS Code** e instale a extensão Jupyter, se ainda não o fez.

2. **Abra o notebook desejado**.

3. **Selecione o kernel**:

   - Clique no nome do kernel no canto superior direito.
   - Selecione **"Python (ai_env)"** na lista de kernels disponíveis.

4. **Verifique o ambiente** executando no notebook:

   ```python
   import sys
   print(sys.executable)
   ```

   Deve retornar o caminho para o Python dentro de `ai_env`.

### Resolvendo Problemas Comuns

- **Erro `ModuleNotFoundError: No module named 'colour'`**: Certifique-se de que o pacote `colour` está instalado no ambiente `ai_env` e que o kernel do Jupyter está usando este ambiente.

- **Mistura de Ambientes (`conda` e `venv`)**: Evite ativar múltiplos ambientes simultaneamente. Desative quaisquer ambientes virtuais (`venv`) antes de ativar o `ai_env`.

- **Importação de `utils.py`**: Verifique se o diretório atual no notebook é o mesmo onde `utils.py` está localizado ou adicione o caminho ao `sys.path`:

  ```python
  import sys
  sys.path.append('/caminho/para/o/diretório')
  ```

### Exportando o Ambiente

Para facilitar a reprodução do ambiente:

```bash
conda env export --no-builds > ai_env.yml
```

Outros usuários podem recriar o ambiente com:

```bash
conda env create -f ai_env.yml
```

## Projeto de Aprendizagem Aplicada

- **Monitoramento da Qualidade do Ar**: Crie uma aplicação para monitorar a qualidade do ar na cidade de Bogotá, Colômbia.
- **Previsão de Energia Eólica**: Desenvolva um modelo de IA para prever a geração de energia eólica, tornando-a mais previsível ao fornecer previsões com 24 horas de antecedência.
- **Monitoramento da Biodiversidade**: Aplique técnicas de visão computacional para detectar e classificar animais com o objetivo de monitorar a biodiversidade.
- **Avaliação de Danos por Desastres**: Construa uma pipeline de classificação de imagens para realizar avaliações de danos usando imagens de satélite capturadas após o furacão Harvey nos EUA em 2017.
- **Análise de Solicitações de Ajuda**: Utilize técnicas de processamento de linguagem natural para analisar tendências em mensagens de texto enviadas após o terremoto de 2010 no Haiti.

## Cursos Incluídos

### Curso 1: IA e Saúde Pública

#### Semana 1: Introdução ao AI for Good

**Objetivos de Aprendizagem**

- Resumir a importância dos dados para um projeto de IA.
- Listar vários exemplos de algoritmos de aprendizado de máquina.
- Definir "AI for Good" e identificar exemplos nessa área.
- Explicar em alto nível o que são inteligência artificial, aprendizado de máquina e aprendizado profundo, e suas relações entre si.
- Descrever algumas limitações da IA, preocupações e questões éticas relacionadas.
- Identificar os componentes-chave do aprendizado supervisionado.

[Quiz: O que é IA?](Course-1/Week-1/C1_W1_Quiz.md)

#### Semana 2: Framework de Projeto AI for Good

**Objetivos de Aprendizagem**

- Descrever o framework de desenvolvimento de projetos "AI for Good".
- Listar os resultados esperados de cada fase do framework.
- Reconhecer como o framework é aplicado em projetos do mundo real.
- Explorar um problema real (qualidade do ar em Bogotá) usando o framework "AI for Good".
- Interpretar gráficos comuns de análise exploratória de dados (EDA).
- Usar um Jupyter Notebook para executar código Python e explorar dados de qualidade do ar.

[Quiz 1: Framework AI for Good](Course-1/Week-2/C1_W2_Quiz-1.md)

[Laboratório: Fase de Exploração - Explorando Dados de Qualidade do Ar](Course-1/Week-2/C1_W2_Lab/C1_W2_L1_Air_Quality_Explore_Phase.ipynb)

[Quiz 2: Explorando a Qualidade do Ar](Course-1/Week-2/C1_W2_Quiz-2.md)

#### Semana 3: Qualidade do Ar em Bogotá, Colômbia

**Objetivos de Aprendizagem**

- Esclarecer como abordar um problema de IA e por quê.
- Listar vários desafios que você pode encontrar em projetos relacionados à IA.
- Resumir as tarefas realizadas nas fases de design e implementação.
- Descrever algumas abordagens para imputação de dados faltantes.
- Determinar o desempenho dos modelos usando MAE.
- Diferenciar entre modelos com base em seu desempenho usando MAE.
- Interpretar gráficos comuns de EDA e heatmaps.
- Projetar e implementar o projeto AI4G, incluindo a estratégia do modelo e a experiência do usuário.
- Determinar como garantir a proteção e privacidade dos dados.

[Laboratório 1: Fase de Design - Estimando Valores Faltantes de PM2.5](Course-1/Week-3/C1_W3_Lab-1/C1_W3_L1_Air_Quality_Design_Phase.ipynb)

[Laboratório 2: Fase de Design e Implementação - Estimando Entre Sensores e Construindo um Mapa](Course-1/Week-3/C1_W3_Lab-2/C1_W3_L2_Design_and_Implement_Phase.ipynb)

[Quiz: Design e Implementação da Qualidade do Ar](Course-1/Week-3/C1_W3_Quiz.md)

### Curso 2: IA e Mudanças Climáticas

#### Semana 1: Introdução à IA e Mudanças Climáticas

**Objetivos de Aprendizagem**

- Explicar o efeito estufa e como emissões de gases de efeito estufa aumentam a temperatura global.
- Descrever como as mudanças climáticas causam crises sociais e ambientais.
- Avaliar a aplicação de técnicas de IA para previsão de energia eólica.
- Identificar contextos onde a IA é utilizada para enfrentar mudanças climáticas.

[Laboratório: Explorando Mudanças de Temperatura Globais](Course-2/Week-1/C2_W1_Lab/C2_W1_Lab_1_Temperature.ipynb)

[Quiz: Mudanças Climáticas e Aquecimento Global](Course-2/Week-1/C2_W1_Quiz.md)

#### Semana 2: Previsão de Energia Eólica

**Objetivos de Aprendizagem**

- Avaliar a aplicabilidade de tecnologias de IA na previsão de geração de energia eólica.
- Determinar como técnicas de aprendizado de máquina (ex.: LSTMs) podem ser usadas para prever geração de energia eólica.
- Identificar métricas úteis para avaliar o desempenho de um modelo de regressão.

[Laboratório 1: Fase de Exploração - Distribuição dos Dados de Energia Eólica](Course-2/Week-2/C2_W2_Lab-1/C2_W2_Lab_1_Wind_Energy_Explore.ipynb)

#### Semana 3: Monitoramento da Biodiversidade

**Objetivos de Aprendizagem**

- Descrever o impacto das mudanças climáticas na perda de habitat e diversidade.
- Explicar como a análise de dados de imagem pode ajudar na preservação da biodiversidade.
- Determinar como dados de armadilhas fotográficas são analisados atualmente e como a IA pode contribuir.

[Laboratório: Fase de Exploração - Explorando Dados de Imagem do Karoo](Course-2/Week-3/C2_W3_Lab/C2_W3_Lab_1_Karoo_Image_data_exploration.ipynb)

### Curso 3: IA e Gestão de Desastres

#### Semana 1: Introdução à IA e Gestão de Desastres

**Objetivos de Aprendizagem**

- Examinar os impactos imediatos e de longo prazo dos desastres nas comunidades.
- Definir as quatro fases do ciclo de gestão de desastres.
- Descrever considerações éticas ao trabalhar com comunidades afetadas.

#### Semana 2: Detecção de Locais de Desastre com Imagens de Satélite

**Objetivos de Aprendizagem**

- Analisar imagens de satélite para definir o problema e identificar stakeholders.
- Implementar uma rede neural convolucional para classificar imagens de satélite.
- Avaliar o desempenho do modelo com matrizes de confusão.

[Laboratório 1: Fase de Exploração - Dados do Furacão Harvey](Course-3/Week-2/C3_W2_Lab-1/C3_W2_L1_Hurricane_Harvey_Explore.ipynb)

[Quiz: Avaliação de Danos para Resposta e Recuperação de Desastres](Course-3/Week-2/C3_W2_Quiz.md)

#### Semana 3: Análise de Dados Textuais para Obtenção de Insights

**Objetivos de Aprendizagem**

- Explorar o desastre do terremoto no Haiti em 2010 para definir o problema, identificar stakeholders, determinar onde a IA pode ser aplicada e se é realmente necessária.
- Descrever como processar dados textuais para aplicações de linguagem natural.
- Implementar a técnica LDA (Latent Dirichlet Allocation) para modelagem de tópicos e avaliar o desempenho utilizando a métrica de coerência.

[Laboratório 1: Fase de Exploração - Explorando Dados de Mensagens de Texto do Terremoto no Haiti](Course-3/Week-3/C3_W3_Lab-1/C3_W3_Lab_1_Haiti_Earthquake_Explore.ipynb)

[Laboratório 2: Fase de Design - Limpeza e Processamento de Dados Textuais](Course-3/Week-3/C3_W3_Lab-2/C3_W3_Lab_2_Haiti_Earthquake_Design_1.ipynb)

[Laboratório 3: Fase de Design - Modelagem de Tópicos em Mensagens de Texto com LDA](Course-3/Week-3/C3_W3_Lab-3/C3_W3_Lab_3_Haiti_Earthquake_Design_2.ipynb)

[Quiz: Análise de Texto para Mitigação e Preparação para Desastres](Course-3/Week-3/C3_W3_Quiz.md)

## Resultados Esperados e Impacto

Este projeto não apenas destaca o uso da inteligência artificial para abordar problemas reais, mas também demonstra a aplicação prática de IA para fins sociais e ambientais. Ele ilustra a viabilidade de soluções tecnológicas em cenários críticos e a capacidade de análise e desenvolvimento de IA para apoiar o bem-estar público. Esses exemplos servem como referência para projetos que busquem impacto social positivo com IA.

## Tecnologias e Ferramentas Utilizadas

- **Python**: Programação e desenvolvimento de modelos de IA.
- **Jupyter Notebooks**: Ambiente para desenvolvimento e visualização de análises.
- **Pandas, NumPy**: Manipulação e análise de dados.
- **Scikit-Learn**: Implementação de algoritmos de aprendizado de máquina.
- **TensorFlow/PyTorch**: Modelagem de redes neurais para tarefas de visão computacional e processamento de linguagem natural.
- **Matplotlib, Seaborn**: Visualização de dados.
- **NLTK, spaCy**: Processamento de linguagem natural para análise textual.
- **Conda**: Gerenciamento de ambientes e pacotes.
- **VS Code**: Ambiente de desenvolvimento integrado para código e notebooks.

## Possíveis Extensões

- **Monitoramento em Tempo Real**: Implementar um sistema de monitoramento contínuo para qualidade do ar ou previsão de energia eólica.
- **Integração com APIs Externas**: Conectar com APIs de monitoramento de clima, qualidade do ar ou sistemas de alerta de desastres para obter dados em tempo real.
- **Aplicação de Modelos mais Complexos**: Experimentar arquiteturas de redes neurais profundas, como LSTM para previsão sequencial de energia eólica ou modelos transformers para análise textual em desastres.

## Demonstração e Visualização

- **Notebooks Interativos no Google Colab**: [Link para os Notebooks](https://colab.research.google.com/)
- **Imagens de Resultados**: Gráficos, heatmaps e diagramas estão incluídos nos notebooks para facilitar a compreensão dos resultados.
- **Vídeo ou Apresentação**: Em breve, adicionarei um vídeo explicando o projeto e seu impacto.

## Agradecimentos

Gostaria de expressar meus sinceros agradecimentos ao professor [Robert Monarch](https://www.linkedin.com/in/robertjmunro/) por compartilhar sua experiência e pela clareza de suas explicações ao longo desta especialização. Agradeço também ao **DeepLearning.AI** e ao **Coursera** pela criação de uma plataforma tão abrangente e bem estruturada, que permite aos alunos explorarem como a IA pode gerar impacto positivo no mundo.

## Contato

Para discutir mais sobre este projeto ou outras iniciativas de IA para o bem, você pode me encontrar no [LinkedIn](https://www.linkedin.com/in/daniel-fugisawa/).