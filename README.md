# python_btc_06
## Iniciar
`pip install pipx`
`pipx install poetry`
`pyenv install 3.12.4`
`pyenv local 3.12.4`  
`poetry init`  
`poetry env use 3.12.4`  
`poetry shell`

## Utilizando bibliotecas para padronização do código
### Flake8
`poetry add flake8`  
Para utilizá-lo basta rodar o código: `poetry run flake8 main.py` - {nome do arquivo}. Dessa forma ele listará dicas de boas práticas para o código.  
A quantidade padrão de caracteres por linha, para esse biblioteca, são 79 caracteres.

---

### Black
`poetry add black`  
Para utilizá-lo basta rodar o código: `poetry run black main.py` - {nome do arquivo}. Dessa forma ele já irá corrigir todo o código.  
A quantidade padrão de caracteres por linha, para esse biblioteca, são 89 caracteres. Por isso é necessário adicionar o arquivo '.flake8' no projeto e nele definir a quantidade máxima de caracteres dentro de um projeto para não haver discordância entre as bibliotecas utilizadas.

---

### Blue
`poetry add blue`
Para utilizá-lo basta rodar o código: `poetry run blue main.py` - {nome do arquivo}. Nesta biblioteca são instaladas as bibliotecas 'black' e 'flake8' como dependência.

---
### Isort
`poetry add isort`  
Serve para ordernar os *import* das bibliotecas.  
É necessário adicionar ao arquivo 'pyproject.toml' o seguinte comando:  
```
[tool.isort]
profile = 'black'
```
Dessa forma está mostrando a biblioteca Isort para utilizar como padrão a biblioteca Black.

---
## Bandit
`poetry add bandit`  
Biblioteca de cibersegurança.

---

### Pre-commit
`poetry add pre-commit`
Para garantir que todo o código seja revisado antes de ser *commitado*, é possível configurar o pre-commit que ele irá rodar um conjunto de condições e garantir o padrão.  
Para isso é preciso ciar o arquivo '.pre-commit-config.yaml' com as condições necessárias a serem seguidas. Para saber mais acesse: [pre-commit hooks](https://pre-commit.com/hooks.html).
```python
poetry add pre-commit
poetry run pre-commit install
git add .pre-commit-config.yaml
git commit -m 'commit inicial'
```
No primeiro *commit* irá demorar um pouco, pois está instalando arquivos dentro da pasta '.git', após isso todos os *commit's* passarão por essa 'varredura'!
