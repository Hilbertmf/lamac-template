# Passo a Passo: Configuração do LaTeX Local (Windows e Linux)

Este guia prático ensina a instalar o **TeX Live**, configurar o **VS Code** com a extensão **LaTeX Workshop** e gerar o preview do PDF localmente.

---

## 1. Instalação do TeX Live

O TeX Live é o conjunto de ferramentas e pacotes necessários para compilar o seu código LaTeX em PDF.

### No Windows
1. Acesse o site oficial do [TeX Live](https://tug.org).
2. Baixe o instalador web clicando em **install-tl-windows.exe**.
3. Execute o arquivo baixado.
4. Na tela inicial, selecione **"Install"** e clique em **Next**.
5. Clique em **Advanced** se desejar alterar o diretório de instalação ou escolher pacotes específicos (recomenda-se a instalação padrão se tiver espaço em disco — aproximadamente 9 GB).
6. Clique em **Install** e aguarde a conclusão (o processo pode demorar algumas horas dependendo da velocidade da sua internet).

### No Linux (Ubuntu / Debian / Mint)
1. Abra o seu terminal (`Ctrl + Alt + T`).
2. Atualize a lista de pacotes do sistema:
   ```bash
   sudo apt update
   ```
3. Instale a versão completa do TeX Live para garantir que nenhum pacote fique ausente:
   ```bash
   sudo apt install texlive-full
   ```

> 📌 **Verificação:** Após instalar (e reiniciar o computador no Windows), abra o terminal ou prompt de comando e digite `pdflatex --version`. Se o comando for reconhecido, a instalação foi bem-sucedida.

---

## 2. Configuração do VS Code e LaTeX Workshop

1. Abra o **Visual Studio Code**.
2. Acesse a aba de Extensões clicando no ícone de quadrados na barra lateral esquerda ou usando o atalho:
   * **Windows/Linux:** `Ctrl + Shift + X`
3. Na barra de pesquisa, digite `LaTeX Workshop`.
4. Encontre a extensão desenvolvida por **James Yu** e clique em **Install**.

---

## 3. Configurando o Projeto e Visualizando o Preview

1. Abra a pasta do projeto no VS Code indo em `File > Open Folder...`.
2. A estrutura do seu projeto está organizada da seguinte forma:
   * `main.tex`: O arquivo principal do projeto. É ele quem gerencia os pacotes, o título e junta todas as partes do texto.
   * `bibliografia.bib`: Arquivo onde ficam armazenadas as suas referências bibliográficas.
   * `sections/`: Pasta que contém o conteúdo real do seu trabalho dividido por seções (`section00.tex`, `section01.tex`, `section02.tex`, `section03.tex`).
   * `img/` e `config/`: Pastas para armazenar suas imagens e configurações adicionais do documento.
   * *(Nota: Arquivos como `.aux`, `.log`, `.toc`, `.pdf` são gerados automaticamente pelo compilador e você não precisa mexer neles).*
3. **Como editar:** 
   * **Informações gerais:** Abra o arquivo `main.tex` se precisar alterar o título, autores, data ou configurações estruturais.
   * **Conteúdo do texto:** Escreva o seu texto abrindo diretamente os arquivos dentro da pasta `sections/` (ex: abra `sections/section00.tex` para editar a introdução ou capítulo inicial).
4. **Garantindo a compilação correta (Dica Essencial):** Para que o VS Code saiba que o `main.tex` é o arquivo principal mesmo quando você estiver editando uma seção secundária, adicione esta linha exatamente no **topo (primeira linha)** de cada arquivo `.tex` dentro da pasta `sections/`:
   ```latex
   %!TEX root = ../main.tex
   ```
5. **Compilar o PDF:** Salve qualquer arquivo que esteja editando pressionando `Ctrl + S`. A extensão identificará o arquivo principal e compilará o código automaticamente. (Caso prefira compilar manualmente, use o atalho `Ctrl + Alt + B` ou clique no triângulo verde).
6. **Abrir o Preview:** No canto superior direito da tela do editor, clique no ícone de **PDF com uma lupa** (*View LaTeX PDF*) (Ctrl+Alt+V por padrão).

---

## 💡 Dica de Produtividade
Com o preview aberto lado a lado, você pode usar o **SyncTeX**:
* Segure `Ctrl` e clique em qualquer frase no PDF para o cursor do VS Code pular direto para a linha equivalente no código fonte.
