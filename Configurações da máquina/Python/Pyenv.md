Responsável por gerenciar as versões do python, semelhante ao nvm

```Bash
# https://github.com/pyenv/pyenv?tab=readme-ov-file#installation
curl -fsSL https://pyenv.run | bash
```

Reinicie o terminal e execute o comando para validar a instalação
```Bash
pyenv --version
```

Caso retorne um erro ou uma linha vazia, será necessário adicionar adicionar ao ***~/.bashrc*** o texto a seguir. É só colar no final do arquivo
```bash
# Pyenv
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"
```

Agora só reiniciar o terminal e ser feliz
```Bash
source ~/.bashrc
```


### Uso prático

Para instalar uma nova versão do python execute o comando
```bash
pyenv install -v 3.9.15
```

### Atenção

Pode ser necessário instalar outras dependências caso o comando anterior falhar. Execute o comando a seguir e depois retorne ao comando anterior
```bash
sudo apt update
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev \
libffi-dev liblzma-dev
```

Para validar a instalação da versão python execute:
```Bash
pyenv versions
```

### Setar a versão global

``` Bash
pyenv global 3.9.15
```

Aqui instalei como global a versão 3.10.4 presente na documentação do próprio Pyenv, mas isso não é um problema já que posso substituir depois facilmente.

### Setar versão local

Depois de instalar uma nova versão, posso deixar ela fixa para uma pasta específica, dentro da pasta é só executar o comando:
``` Bash
pyenv local 3.9.15
```
