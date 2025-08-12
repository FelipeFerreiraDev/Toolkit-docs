Será necessário instalar o GPG, realize os procedimentos a seguir

**Assinar commits com GPG**

**1. Instalar o GPG**
```Bash
sudo apt update sudo apt install gnupg
```

**2. Criar uma chave**
```Bash
gpg --full-generate-key
```

- Escolha: `1` (RSA and RSA)
- Tamanho: `4096` (recomendado)
- Validade: pode ser infinita (`0`) ou definir um prazo
- Nome e e-mail: use o mesmo e-mail do GitHub
- Senha: opcional, mas recomendada

**3. Listar suas chaves**
```Bash
gpg --list-secret-keys --keyid-format=long
```

O Retorno será algo como `sec   rsa4096/ABCDEF1234567890 2025-08-11 [SC]`. O ID da chave é o que vem depois de **rsa4096**


**4. Exportar a chave pública**
```Bash
gpg --armor --export ABCDEF1234567890
```

Copie todo o texto que aparecer (`-----BEGIN PGP PUBLIC KEY BLOCK-----` até `-----END PGP PUBLIC KEY BLOCK-----`).


**5. Adicionar ao GitHub**
1. Vá em: [https://github.com/settings/keys](https://github.com/settings/keys)

2. Clique **New GPG Key**

3. Cole a chave pública e salve.


**6. Configurar o Git para usar a chave**
```Bash
git config --global user.signingkey ABCDEF1234567890 git config --global commit.gpgsign true
```

Se tudo ocorreu como planejado, basta realizar um commit e olhar no GitHub para validação, deve aparecer o selo ao lado do commit.