# Resíduos Chapecó ML

Projeto de estudo e prototipagem para análise de resíduos sólidos em Chapecó — geração de dados simulados, análise exploratória e clusterização de perfis.

---

## Objetivo

Construir uma base inicial para:

- simular respostas de um formulário sobre geração e destinação de resíduos;
- analisar distribuição e comportamento das variáveis;
- identificar perfis semelhantes por técnicas de agrupamento.

---

## Estrutura do projeto

```text
residuos-chapeco-ml/
├─ dados/
│  ├─ publicos/
│  └─ simulados/
│     └─ respostas_simuladas.csv
├─ notebooks/
│  ├─ 00_geracao_dados_simulados.ipynb
│  ├─ 01_analise_exploratoria.ipynb
│  └─ 02_clusterizacao.ipynb
├─ scripts/
│  └─ preprocessamento.py
├─ requirements.txt
└─ README.md
```

## Requisitos

- Python 3.10+

Dependências listadas em `requirements.txt`:

| Pacote | Uso |
|---|---|
| pandas | manipulação de dados |
| numpy | operações numéricas |
| matplotlib + seaborn | visualizações |
| scikit-learn | clusterização e pré-processamento |
| jupyter | execução dos notebooks |

## Instalação

No diretório do projeto, crie e ative um ambiente virtual:

```bash
# criar
python -m venv .venv

# ativar (Linux/macOS)
source .venv/bin/activate

# ativar (PowerShell)
.\.venv\Scripts\Activate.ps1
```

Instale as dependências:

```bash
pip install -r requirements.txt
```

> Atenção: ao abrir os notebooks, selecione o kernel correspondente ao `.venv` criado acima para evitar erros de módulo não encontrado.

## Como executar

Execute os notebooks em ordem:

1. **00_geracao_dados_simulados.ipynb**
   - gera os dados simulados com semente fixa para reprodutibilidade;
   - salva em `dados/simulados/respostas_simuladas.csv`.

2. **01_analise_exploratoria.ipynb**
   - carrega o CSV gerado;
   - calcula proporções por variável;
   - gera gráficos de distribuição.

3. **02_clusterizacao.ipynb**
   - aplica técnicas de clusterização para segmentar perfis de geradores.

## Sobre os dados simulados

O arquivo `dados/simulados/respostas_simuladas.csv` contém variáveis relacionadas a:

- perfil e tipo do gerador;
- tipo e origem do resíduo;
- quantidade gerada;
- destino atual do resíduo;
- percepção e comportamento sobre reaproveitamento.

## Próximos passos

- preencher `scripts/preprocessamento.py` com tratamento e validação de dados;
- incluir métricas de qualidade dos clusters no notebook 02;
- adicionar testes automatizados para etapas de transformação.