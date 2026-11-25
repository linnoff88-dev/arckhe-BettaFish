>  **Atençêo**: Se você precisa utilizar a funcionalidade de exportaçêo PDF, siga os passos abaixo para instalar as dependências do sistema. Se nêo precisar da funcionalidade de exportaçêo PDF, pode pular esta etapa; as demais funcionalidades do sistema nêo serêo afetadas.

<details>
<summary><b> Passos de instalaçêo para Windows</b></summary>

```powershell
# 1. Baixe e instale o GTK3 Runtime (execute na máquina host)
# Acesse: https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer/releases
# Baixe o arquivo .exe da versêo mais recente e instale
# É fortemente recomendado instalar no caminho padrêo, pois isso pode ajudar a evitar diversos erros desconhecidos

# 2. Adicione o diretório bin da instalaçêo GTK ao PATH (reabra o terminal após a instalaçêo)
# Exemplo de caminho padrêo (se instalado em outro diretório, substitua pelo seu caminho real)
set PATH=C:\Program Files\GTK3-Runtime Win64\bin;%PATH%

# Opcional: adicionar permanentemente ao PATH
setx PATH "C:\Program Files\GTK3-Runtime Win64\bin;%PATH%"

# Se instalado em um diretório personalizado, substitua pelo caminho real, ou defina a variável de ambiente GTK_BIN_PATH=seu_caminho_bin e reabra o terminal

# 3. Verificaçêo (execute em um novo terminal)
python -m ReportEngine.utils.dependency_check
# A saída contendo "✓ Pango 依赖检测通过" indica que a configuraçêo está correta
```

</details>

<details>
<summary><b> Passos de instalaçêo para macOS</b></summary>

```bash
# Passo 1: Instalar dependências do sistema
brew install pango gdk-pixbuf libffi

# Passo 2: Configurar variáveis de ambiente (⚠️ obrigatório!)
# Método um: Configuraçêo temporária (válida apenas para a sessêo atual do terminal)
# Apple Silicon
export DYLD_LIBRARY_PATH=/opt/homebrew/lib:$DYLD_LIBRARY_PATH
# Intel Mac
export DYLD_LIBRARY_PATH=/usr/local/lib:$DYLD_LIBRARY_PATH

# Método dois: Configuraçêo permanente (recomendado)
echo 'export DYLD_LIBRARY_PATH=/opt/homebrew/lib:$DYLD_LIBRARY_PATH' >> ~/.zshrc
# Usuários Intel devem alterar para:
# echo 'export DYLD_LIBRARY_PATH=/usr/local/lib:$DYLD_LIBRARY_PATH' >> ~/.zshrc
source ~/.zshrc

# Passo 3: Verificaçêo (execute em um novo terminal)
python -m ReportEngine.utils.dependency_check
# A saída contendo "✓ Pango 依赖检测通过" indica que a configuraçêo está correta
```

**Problemas comuns**:

- Se ainda aparecer erro de biblioteca nêo encontrada, verifique se:
  1. Executou `source ~/.zshrc` para recarregar a configuraçêo
  2. Está executando a aplicaçêo em um novo terminal (para garantir que as variáveis de ambiente estejam em vigor)
  3. Use `echo $DYLD_LIBRARY_PATH` para verificar se a variável de ambiente foi definida

</details>

<details>
<summary><b> Passos de instalaçêo para Ubuntu/Debian</b></summary>

```bash
# 1. Instalar dependências do sistema (execute na máquina host)
sudo apt-get update
sudo apt-get install -y \
  libpango-1.0-0 \
  libpangoft2-1.0-0 \
  libffi-dev \
  libcairo2

# Priorizar o nome de pacote mais recente; fazer fallback se o repositório nêo o fornecer
if sudo apt-cache show libgdk-pixbuf-2.0-0 >/dev/null 2>&1; then
  sudo apt-get install -y libgdk-pixbuf-2.0-0
else
  sudo apt-get install -y libgdk-pixbuf2.0-0
fi
```

</details>

<details>
<summary><b> Passos de instalaçêo para CentOS/RHEL</b></summary>

```bash
# 1. Instalar dependências do sistema (execute na máquina host)
sudo yum install -y pango gdk-pixbuf2 libffi-devel cairo
```

</details>

>  **Dica**: Se estiver utilizando deploy com Docker, nêo é necessário instalar essas dependências manualmente; a imagem Docker já contém todas as dependências de sistema necessárias.
