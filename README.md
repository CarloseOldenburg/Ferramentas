# VSD Launcher - Ferramenta

`vsd-launcher` é uma ferramenta de linha de comando desenvolvida para facilitar a configuração de ambientes de software da VideoSoft, permitindo alterar URLs de execução, limpar cache/token do navegador e configurar o sistema para ambientes de homologação ou produção.

---

## ⚙️ Funcionalidades

- ✅ Atualiza automaticamente a URL de ambiente (`VS_URL_APP`) de acordo com o serviço e versão desejada.
- 🧹 Limpa o cache do Google Chrome do sistema.
- 🔐 Remove arquivos de token e recuperação da interface.
- 📄 Fornece ajuda interativa com o parâmetro `--help`.

---

## 📥 Instalação

Execute o comando abaixo para baixar e instalar o script diretamente no terminal:

```bash
sudo wget https://raw.githubusercontent.com/CarloseOldenburg/Ferramentas/refs/heads/main/VSD-Launcher -O vsd-launcher && \
sudo chmod 755 vsd-launcher && \
sudo mv vsd-launcher /usr/bin/
````

---

## 🧪 Uso

### Comando principal:

```bash
vsd-launcher -s <serviço> [-v <versão>] [--homolog] [--clear-cache] [--clear-token]
```

### Parâmetros disponíveis:

| Parâmetro        | Descrição                                                              |
| ---------------- | ---------------------------------------------------------------------- |
| `-s <serviço>`   | Define o serviço a ser atualizado: `food` ou `self`                    |
| `-v <versão>`    | (Opcional) Define a versão do serviço: `2` ou `3` (apenas para `food`) |
| `--homolog`      | Altera para o ambiente de homologação                                  |
| `--clear-cache`  | Limpa o cache do Google Chrome                                         |
| `--clear-token`  | Limpa cache + tokens (`_database_token*` e `_database_recovery*`)      |
| `-h` ou `--help` | Exibe a ajuda                                                          |

---

## 🌐 Exemplos de uso

### ✅ Atualizar para ambiente de produção Food 3.0:

```bash
vsd-launcher -s food -v 3
```

### ✅ Atualizar para ambiente de homologação SelfCheckout:

```bash
vsd-launcher -s self --homolog
```

### ✅ Limpar apenas o cache do Chrome:

```bash
vsd-launcher --clear-cache
```

### ✅ Limpar tokens e cache:

```bash
vsd-launcher --clear-token
```

---

## 🛠 Caminhos utilizados

* O launcher edita o seguinte arquivo para atualização de URL:

  ```
  /opt/videosoft/vs-food-launcher/app/vs-food.sh
  ```

* Os tokens são apagados em:

  ```
  /opt/videosoft/vs-os-interface/log/
  ```

* O cache é limpo em:

  ```
  ~/.cache/google-chrome/
  ~/.config/google-chrome/
  ```

---

## 📚 Ajuda

Para exibir o menu de ajuda, use:

```bash
vsd-launcher --help
```

---

## 📌 Observações

* O script precisa ser executado com permissões administrativas para realizar alterações nos diretórios do sistema.
* Certifique-se de que o arquivo `vs-food.sh` contém a variável `VS_URL_APP="..."` para que a substituição funcione corretamente.

---

## 👤 Autor

Desenvolvido por [Carlos Eduardo Oldenburg](https://github.com/CarloseOldenburg)
Fonte do launcher [Wilker Santos](https://github.com/wilker-santos)

---

## 📜 Licença

Distribuído sob licença livre para uso interno corporativo e manutenção de terminais com sistemas VideoSoft.

