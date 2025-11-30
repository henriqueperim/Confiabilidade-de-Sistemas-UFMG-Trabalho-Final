# Análise de Confiabilidade Aplicada a Dados de Manutenção de Caminhões Scania

## Projeto: Análise de Confiabilidade de Sistemas  
Disciplina: EEE017 – Confiabilidade de Sistemas  
Universidade: UFMG – Engenharia de Sistemas  
Grupo: 3  

---

## Descrição do Projeto

Este repositório contém o código utilizado no Trabalho Prático final da disciplina de Confiabilidade de Sistemas.  
O objetivo é analisar dados reais disponibilizados pela Scania (Nature – 2025), contendo informações de tempo até falha (TTF) e leituras operacionais de caminhões pesados.  

Com base nesses dados, exploramos técnicas clássicas e modernas de análise de confiabilidade para estimar taxas de falha, gerar curvas de sobrevivência e investigar sinais de desgaste nos veículos.

---

## Estrutura do Repositório
```
.
├── dados/ # Pasta vazia (dados originais são muito grandes)
├── notebooks/ # Notebooks com toda a análise e gráficos
├── scripts/ # Funções auxiliares e rotinas de plot e modelos
├── requirements.txt # Dependências do projeto
└── README.md # Este arquivo
```


A pasta `dados/` foi propositalmente deixada vazia, pois os CSVs originais são grandes e excedem o tamanho permitido pelo GitHub.


## Principais Técnicas Aplicadas

### Pré-processamento
- Seleção de variáveis relevantes  
- Agregação por veículo  
- Tratamento básico de outliers e valores ausentes

### Análise de Confiabilidade
- Estimativa de sobrevivência empírica (falhas observadas)
- Modelagem da sobrevivência com distribuição **GEV** (Generalized Extreme Value)
- Comparação empírica vs. ajustada

### Bootstrap
- Estimação não-paramétrica do MTTF condicional
- Intervalos de confiança por reamostragem
- Análise da variabilidade da estimativa

### Visualização
- Histogramas dos tempos até falha
- Boxplots comparando falha x censura
- Evolução temporal de contadores operacionais
- Curvas ajustadas da GEV vs. sobrevivência empírica

---

## Como obter os dados

Os dados utilizados podem ser baixados diretamente no artigo da Nature:

https://www.nature.com/articles/s41597-025-04802-6

Após baixar e extrair, coloque os arquivos CSV na pasta:
```
dados/
```

Arquivos principais:
- `train_tte.csv`
- `train_operational_readouts.csv`
- (opcional) arquivos de validação/teste

---

## Como executar o projeto

### Criar ambiente e instalar dependências
```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

