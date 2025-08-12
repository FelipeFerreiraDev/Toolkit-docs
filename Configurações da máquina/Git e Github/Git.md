Guia de instalação:

``` Bash
sudo apt update
sudo apt install git
```

Vincule com o Github
```Bash
git config --global user.name "Seu Nome no GitHub"
git config --global user.email "seu-email@example.com"
```

**Criar chave SSH**
`ssh-keygen -t ed25519 -C "seu-email@example.com"`

Se aparecer `Enter a file in which to save the key` aperte **Enter** para usar o caminho padrão. Se pedir senha, você pode criar uma (opcional, mas mais seguro).

**Iniciar o agente SSH e adicionar a chave**
```Bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

**Copie a chave pública**
`cat ~/.ssh/id_ed25519.pub`

## **Adicionar a chave ao GitHub**

1. Vá em [https://github.com/settings/keys](https://github.com/settings/keys)

2. Clique **New SSH key**.

3. Dê um título (ex: "Ubuntu Laptop") e cole a chave copiada.

4. Salve.

Para testar a conexão você pode usar no terminal:
`ssh -T git@github.com`

Se a mensagem `Are you sure you want to continue connecting (yes/no/[fingerprint])?` aparecer, você pode escrever **yes** e pressionar enter para aceitar a conexão

Se funcionou corretamente deve aparecer a mensagem:
`Hi SEU_USUARIO! You've successfully authenticated...`

## Atenção
É mais recomendado utilizar agora ssh para acessar o GitHub ao clonar repositórios.

Caso você clone repositórios via `https`, sugiro rodar o comando a seguir para evitar ter que inserir a senha todas as vezes que realizar um commit
```Bash
git config --global credential.helper store
```

**Observação:** Use o comando a seguir para salvar temporariamente
```Bash
# Por padrão 15 min
git config --global credential.helper cache

# Ou para setar um valor específico, exemplo 6 horas

git config --global credential.helper 'cache --timeout=21600'
```