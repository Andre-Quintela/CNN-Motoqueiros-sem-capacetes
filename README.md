# Validação de Capacete (CNN)

Descrição
-	Projeto em notebook contendo uma Convolutional Neural Network (CNN) para validação de uso de capacete em imagens (detecção/classificação), acompanhado de um conjunto de dados local `HelmetViolationsV2`.

Conteúdo deste repositório
- `CNN_ValidacaoCapacete.ipynb` — Notebook principal com todo o fluxo: carregamento dos dados, pré-processamento, definição da CNN, treinamento, validação e inferência.

Objetivo
- Documentar como executar o notebook localmente, quais dependências instalar e onde ajustar caminhos de dados. O notebook realiza experimento de treino/validação de uma CNN para classificar/validar capacete em imagens.

Requisitos
- Python 3.8+
- CUDA (opcional) para acelerar treinamento com GPU

Dependências recomendadas
Instale as dependências listadas em `requirements.txt` (arquivo criado neste repositório). Recomenda-se usar um ambiente virtual.

Exemplo (Windows `cmd.exe`):
```
python -m venv .venv
.venv\Scripts\activate
pip install -r "e:\Ifood Projects\requirements.txt"
```

Como usar
1. Abra o notebook `CNN_ValidacaoCapacete.ipynb` em Jupyter Notebook ou JupyterLab:
```
jupyter notebook "e:\Ifood Projects\CNN_ValidacaoCapacete.ipynb"
```
2. Verifique/ajuste os caminhos de dataset no notebook. Por padrão o notebook assume que a pasta do dataset está em `HelmetViolationsV2/` na raiz do projeto. Pontos comuns a ajustar:
   - `DATA_DIR = "HelmetViolationsV2/"` ou `"e:\Ifood Projects\HelmetViolationsV2/"`
   - Caminhos de `train/images`, `valid/images`, `test/images` e os arquivos de label correspondentes.
3. Execute as células na ordem (ou use `Run All`).

Treinamento (alternativa via script)
Se você extraiu trechos do notebook para um script Python, rode-o com:
```
python train.py --data "HelmetViolationsV2/data.yaml" --epochs 50
```
(Ajuste flags conforme o seu script.)

Possíveis melhorias
- Separar código em scripts `train.py`, `eval.py`, `infer.py` para execução mais robusta.
- Implementar logging (TensorBoard ou Weights & Biases).
- Adicionar pipeline de augmentations (albumentations).
