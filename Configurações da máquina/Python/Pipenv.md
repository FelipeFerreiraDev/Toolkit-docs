O **pipenv** é uma ferramenta para **gerenciar dependências e ambientes virtuais** em projetos Python, meio que juntando o que o `pip` e o `virtualenv` fazem.

A lógica é semelhante ao `package-lock.json` do Node.Js

**Comando para instalação:**

``` python
# https://pipenv.pypa.io/en/latest/
pip install --user pipenv
```

- O `--user` evita que mexa no Python do sistema e instala só para o seu usuário.

Será necessário adicionar a linha a seguir no arquivo `~/.bashrc`

```Bash
export PATH="$HOME/.local/bin:$PATH"
```

## Atenção
Isso não ajusta só o **pipenv** — essa linha coloca **todo e qualquer programa** instalado pelo `pip --user` (ou outros programas que coloquem binários em `~/.local/bin`) no seu `PATH`.

Ou seja:

- O **pipenv** vai passar a funcionar, porque o executável dele está em `~/.local/bin`.

- Outros pacotes Python que você instalar com `pip install --user` também vão funcionar direto, sem precisar chamar o caminho completo.

- Isso também vale para alguns programas instalados por gerenciadores como `cargo` (Rust), `go install` (Go), etc., caso configurem essa pasta.


### Para validar a instalação:

Crie uma pasta qualquer e dentro dela execute o comando para instalar uma biblioteca qualquer

```Bash
pipenv install pandas
```

Após isso na pasta deve existir dois arquivos:
- Pipfile
- Pipfile.lock

Agora basta ativar o ambiente virtual
```Bash
pipenv shell
```

Assim que você executar o comando shell, o caminho do terminal ficará algo como:
```python
(python-example) user@user:~/dev/python-example$
```

Você também pode instalar versões específicas do pacote e do python
```Bash
pipenv install pandas==1.5.2 --python 3.8.7
```

Para desativar a seção do ambiente virtual:
```bash
exit
```

