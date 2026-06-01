# PGENE556 - Aprendizado de Máquina

Repositório central para os trabalhos, implementações e projetos desenvolvidos na disciplina **PGENE556 - Aprendizado de Máquina** do Programa de Pós-Graduação em Engenharia Elétrica (PPGEE) da Universidade Federal do Amazonas (UFAM).

**Autor:** Davi Israel Abtibol Carvalho  
**Semestre:** 2026/1

---

## Estrutura do Repositório

O repositório está organizado por trabalhos. Cada pasta contém o seu próprio conjunto de dados (`dataset`), o código-fonte desenvolvido (geralmente em `.ipynb`) e a documentação respectiva.

```text
 aprendizado-maquina-2026
 ┣  trabalho_1_naive_bayes/
 ┃ ┣  dataset/                                      # Base de dados (Iris)
 ┃ ┣  Trabalho1_NaiveBayes.ipynb                    # Código-fonte e experimentos
 ┃ ┗  Trabalho_1_Naive_Bayes___Davi_Carvalho.pdf    # Relatório final formato IEEE
 ┣  trabalho_2/
 ┃ ┣  dataset/                                      # Base de dados (Câncer de Ovário)
 ┃ ┣  trabalho_2.ipynb                              # Código-fonte e experimentos
 ┃ ┗  Trabalho_2_Regressao_Logistica___Davi_Carvalho.pdf # Relatório final formato IEEE
 ┣  .gitignore
 ┣  README.md
 ┣  pyproject.toml                                  # Arquivos de formatação do Ruff
 ┗  requirements.txt                                # Lista de dependências do ambiente
```

_(Obs: Novos trabalhos serão adicionados como novas pastas ao longo do semestre)._

---

## Trabalhos Desenvolvidos

### Trabalho 1: Classificador Naive Bayes Gaussiano "From Scratch"

**Objetivo:** Implementar do zero (sem uso de frameworks de alto nível como `scikit-learn`) um classificador Naive Bayes para o clássico _Iris Dataset_, utilizando apenas matemática vetorial e álgebra linear.

- **Modelo:** Gaussian Naive Bayes (lidando com probabilidade contínua via Função de Densidade de Probabilidade).
- **Validação:** Implementação manual de um _Stratified 5-Fold Cross-Validation_ para garantir balanceamento perfeito (33,33% por classe) em todas as pastas de teste.
- **Resultados:** Acurácia média de 96.00% ($\pm$ 1.33%).
- **Bibliotecas:** `numpy`, `pandas`, `matplotlib`, `seaborn`.

### Trabalho 2: Classificação de Câncer de Ovário utilizando Regressão Logística e Redução de Dimensionalidade (PCA)

**Objetivo:** Projetar um regressor logístico de uma camada para identificar pacientes com câncer de ovário através de assinaturas proteômicas originadas de exames de espectrometria de massa.

- **Pré-processamento:** Padronização estatística (`StandardScaler`) e Análise de Componentes Principais (`PCA`) para redução de dimensionalidade (de 100 características originais para 50 componentes principais). Conservação de 99,88% da variância.
- **Modelo:** Regressão Logística (classificação linear binária).
- **Validação:** Particionamento estratificado 80/20 (Treino/Teste).
- **Resultados:** Capacidade analítica perfeita perante os dados de teste, atingindo 100,00% de Acurácia, 100,00% de Sensibilidade e 100,00% de Especificidade (dados linearmente separáveis).
- **Bibliotecas:** `scikit-learn`, `numpy`, `pandas`, `matplotlib`, `seaborn`, `xlrd`.

### Trabalho 3: Predição de Temperaturas usando Random Forest Regressor

**Objetivo:** Projetar e otimizar modelos baseados no algoritmo _Random Forest_ (Floresta Aleatória) para predizer a temperatura máxima contínua (Regressão) da cidade de Seattle baseando-se em eventos climáticos de dias anteriores.

- **Modelo:** Random Forest Regressor. Estudo aprofundado dos hiperparâmetros `max_depth`, `min_samples_split` e uso de amostragens `bootstrap`.
- **Pré-processamento:** Separação 75/25 sem padronização de escalonamento (vetores baseados em nós de decisão não-lineares).
- **Validação e Otimização:** Otimização exaustiva de hiperparâmetros utilizando `RandomizedSearchCV` e extração da métrica de Feature Importances.
- **Resultados:** Erro Absoluto Médio (MAE) de apenas 3.67 graus atingido por um modelo conservador e resistente ao overfitting, equiparando-se ao modelo otimizado e superando consideravelmente redes superprofundas.
- **Bibliotecas:** `scikit-learn`, `numpy`, `pandas`, `matplotlib`, `seaborn`.

---

## Como reproduzir o ambiente localmente

Este repositório utiliza as melhores práticas de Engenharia de Software voltadas para Dados. Para garantir extrema velocidade e reprodutibilidade, o gerenciamento de dependências e ambientes virtuais é feito utilizando o [uv](https://github.com/astral-sh/uv) (um instalador Python extremamente rápido escrito em Rust).

**Pré-requisitos:** Python 3.10+ e `uv` instalados. Recomendado o uso de WSL2 (Ubuntu) no Windows ou ambientes Linux/macOS.

**1. Clone o repositório:**

```bash
git clone https://github.com/AbtibolDavi/aprendizado-maquina-2026.git
cd aprendizado-maquina-2026
```

**2. Crie e ative o ambiente virtual com `uv`:**

```bash
uv venv
source .venv/bin/activate
```

**3. Instale as dependências automaticamente:**

```bash
uv pip install -r requirements.txt
```

**4. Execute os Notebooks:**
Abra o repositório no seu editor de preferência (ex: VS Code) ou inicie o servidor do Jupyter:

```bash
jupyter notebook
```
