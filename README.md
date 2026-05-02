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
 ┃ ┣  dataset/                      # Arquivos base (ex: iris_dataset.xlsx)
 ┃ ┣  Trabalho1_NaiveBayes.ipynb    # Código-fonte e experimentos
 ┃ ┗  Artigo_IEEE_NaiveBayes.pdf    # Relatório final formato IEEE
 ┣  .gitignore
 ┣  README.md
 ┗  pyproject.toml                  # Arquivos de formatação do Ruff
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

---

## Como reproduzir o ambiente localmente

Este repositório utiliza as melhores práticas de Engenharia de Software voltadas para Dados. Para garantir extrema velocidade e reprodutibilidade, o gerenciamento de dependências e ambientes virtuais é feito utilizando o [uv](https://github.com/astral-sh/uv) (um instalador Python escrito em Rust).

**Pré-requisitos:** Python 3.10+ e `uv` instalados. Recomendado o uso de WSL2 (Ubuntu) no Windows ou Linux.

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

**3. Instale as dependências:**

```bash
uv pip install jupyter pandas openpyxl numpy matplotlib seaborn
```

**4. Execute os Notebooks:**
Abra o repositório no seu editor de preferência (ex: VS Code) ou inicie o servidor do Jupyter:

```bash
jupyter notebook
```
