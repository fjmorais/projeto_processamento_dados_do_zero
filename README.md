# Projeto e processamento de dados do Zero

Passo a passo de como estruturar um projeto de dados do zero, organizando o processo de ETL, Git, Testes unitários, CI/CD, etc.

### Como criar um repositório no Git HUB:

```bash
gh repo create
```
Veja a figura abaixo com o passo a passo para criação do repositório usando linha de comando.

Figura 01 - Criar repositório por linha de comando.

Como adicionar um arquivo no repositório e fazer o commit no repositório.

```bash
git add README.md
```

```bash
git commit -m "docs: Adicionar o arquivo README.md"
```

Para subir o arquivo para o repositório

```bash
git push
```

Sempre a primeira vez que estamos fazendo o git commit e o push, devemos informar qual a camada do repositório queremos enviar. Por exemmplo, camada "main", que é a principal.


```bash
git push --set-upstream origin main
```

Como fazer para recuperar um arquivo que foi excluído de um repositório do git hub ?

Executar o git log para verificar o histório de commit e escolher o apropriado para recuperar o arquivo que foi excluído.

```bash
git log
```

Após verificar o HASH devido do commit, executar o comando abaixo informando o arquivo que deseja recuperar.


```bash
git checkout <informar no HASH> -- <informar o nome do arquivo>
```

Figura 02 - Recuperando um arquivo que foi excluído.


### Escolhendo a versão python a qual será usada no projeto.

Depois da criação do repositório do Git Hub, é chegada o momento de definir a versão do python a ser utilizado.

Verificar versão do python:

```bash
python --version
```

Como vamos trabalhar com o Streamlit, devemos usar a versão 3.11.

Para fazer a gestão de qual versão vamos usar do Python no projeto, usaremos o pyenv.


```bash
pyenv versions
```

Vamos informar qual a versão do python que será utilizada no projeto, basta executar o comando abaixo na pasta do projeto que é a mesma que será atualizada no git hub.


```bash
pyenv local 3.11.5
```

Figura 03 - Definindo versão python para o projeto.


### Criação do ambiente virtual

Com a definição de qual versão python a ser criada no projeto, devemos fazer a criação do ambiente virtual.

Criar o arquivo para ambiente virtual, que nesse caso por questão de nomenclatura, usaremos o nome de ".venv". Importante entender que o nome do comando é "venv" e o nome do arquivo é ".venv", para não fazer confusão.

```bash
python -m venv .venv
```

Figura 04 - criação do ambiente virtual.


Importante ressaltar a necessidade de criação de um arquivo na pasta de projeto chamado gitgnore. Esse arquivo contém as informações do que não deve ser enviado para o repositório do github, quando é feito o commit. De forma simplista seria, git, para de verificar tais arquivos.


Figura 05 - Exemplo dos arquivo que serão ignorados no processo de commit.


Figura 06 - Arquivo de configuração do VSCODE.


Depois do ambiente virtual criado, é necessário "ligar", ou sejam deixar o ambiente virtual habilitado para a execução do projeto.

Comando para ser executado no windows:

```bash
source .venv/bin/activate
```

Comando para ser executado no Linux:

```bash
pyenv activate .venv
```

Depois do ambiente virtual ativado, vamos fazer a instalação dos pacotes que serão necessário para o projeto e que apenas existirá para essa pasta\projeto.


```bash
pip install streamlit
```

Importante compreender que tudo que for instalado nesse ambiente virtual, ficará no arquivo .venv e assim será possível validar e verificar o arquivo requirements.txt.


Executar o comando para criar o arquivo requirements.txt:

```bash
pip freeze > requirements.txt
```

Figura 07 - criação do arquivo requirements.txt


Validando o arquivo requirements txt:

Figura 08 - Validando o arquivo requirements.txt


Quando vocẽ for passar o seu projeto para alguma pessoa, o arquivo requirements.txt é uma ótima informação do que realmente é necessário para fazer a instalação do projeto.

```bash
pip install requirements.txt
```

# Informação básicas no README.md 

Em um projeto no github, o arquivo README, como boa prática, deve conter algumas informações básicas de como fazer o download do projeto.

Vejamos um exemplo:


Figura 09 - Exemplo do README parte 01.

Figura 10 - Exemplo do README parte 02.

Figura 11 - Exemplo do README parte 03.


# Preparando o projeto fazendo a organização das pastas


Criar a pasta tests, src e docs:

Figura 12 - Pastas criadas no projeto.


# Fazendo o contrato de dados

Nessa etapa, vamos utilizar o pydantic para realizar o nosso contrato de dados.

Instalação do pydantic:

```bash
pip install pydantic
```

Figura 13 - Instalação do pydantic no ambiente virtual .venv














