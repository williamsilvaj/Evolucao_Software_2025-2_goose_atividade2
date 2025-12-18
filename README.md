# Evolucao_Software_2025-2_goose_atividade2

## 📋 Descrição do Projeto
Este repositório contém o material técnico e os artefatos produzidos para a **Atividade 2** da disciplina de **Evolução de Software (2025.2)**. 

O objetivo principal é a detecção e análise de **Code Smells** no projeto open-source **Goose** (`block/goose`), utilizando uma abordagem híbrida que combina métricas tradicionais (AST) e Modelos de Linguagem de Grande Escala (LLMs) hospedados no **Hugging Face**.

---

## 👥 Equipe
* **Igor Nathan Monteiro Santos** 
* **João Vítor Santos** 
* **Manoel Victor Lima Monteiro**
* **Pedro Henrique Isidorio Soares** 
* **Unaldo Santos Vasconcelos Neto** 
* **Vitor De Lima Alves** 
* **William Santos Silva** 

---

## 🚀 Guia de Execução (Tutorial)

### 1. Pré-requisitos
O projeto foi desenvolvido em ambiente **Google Colab** para aproveitar recursos de GPU necessários para a execução dos modelos da Hugging Face.

* Conta no Google.
* Token de acesso pessoal do GitHub (Classic Token) para coleta de dados via API.
* Bibliotecas principais: `transformers`, `torch`, `pandas`, `radon`, `matplotlib`, `seaborn`.

### 2. Configuração do Ambiente
1.  Abra o arquivo `Atividade_2_Code_Smells_modificado.ipynb` no Google Colab.
2.  Insira seu **GitHub Token** na seção de "Secrets" (UserData) do Colab com a chave `GITHUB_ACCESS_TOKEN`.
3.  Execute a primeira célula para instalar todas as dependências automáticas.

### 3. Workflow de Análise
O notebook executa as seguintes etapas:
* **Extração:** Conecta à API do GitHub e extrai as 5 últimas releases do projeto `block/goose`.
* **Análise Heurística:** Utiliza a biblioteca `AST` e `Radon` para estabelecer um baseline (Long Method e Large Class).
* **Inferência por IA:** Utiliza os modelos:
    * `mrm8488/codebert-base-finetuned-detect-insecure-code` (Segurança).
    * `microsoft/codebert-base` (Estrutura).
    * `Salesforce/codet5-base` (Semântica).
* **Comparação:** Consolida os resultados em uma tabela comparativa.

---

## 📊 Resultados e Insights

### Tabela Comparativa (Resultados Consolidados)
| Code Smell | AST-Heuristics | CodeBERT-Insecure | CodeT5 |
| :--- | :---: | :---: | :---: |
| **Insecure Code** | 0 | 268 | 0 |
| **Feature Envy** | 123 | 0 | 58 |
| **Long Method** | 23 | 0 | 44 |

### Evolução da Dívida Técnica
A análise temporal mostrou um crescimento significativo na quantidade de *smells* detectados:
* **v1.13.2:** 56 instâncias.
* **v1.16.1:** 148 instâncias.

**Conclusão:** O aumento de ~164% sugere que a evolução do projeto está gerando uma complexidade que supera a taxa de refatoração, impactando a manutenibilidade futura.

---

## 🔗 Links e Documentos
* **Vídeo Tutorial (Apresentação):**
* **Relatório PDF:**
* **Projeto Original Analisado:** [block/goose](https://github.com/block/goose)

---

## 🛠️ Artefatos no Repositório
* `/scripts`: Contém o notebook `.ipynb` e scripts auxiliares.
* `/results`: Tabelas e gráficos gerados durante a análise.
* `Atividade_2_Relatorio.pdf`: Documento oficial com nomes e matrículas.

---
**Nota:** Este projeto foi realizado para fins acadêmicos na Universidade Federal de Sergipe (UFS).
