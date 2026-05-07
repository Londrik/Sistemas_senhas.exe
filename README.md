📑 Documentação: Sistema de Painel de Senhas

Esta documentação descreve o processo técnico para baixar o código fonte e transformá-lo em um aplicativo executável (.exe) para Windows.
1. 📥 Obtendo o Arquivo do GitHub

Para baixar apenas o arquivo de código específico (Sistemas_senhas.py) sem baixar o repositório inteiro, utilizamos o comando de requisição web do PowerShell:

Comando utilizado:
PowerShell

Invoke-WebRequest -Uri "https://raw.githubusercontent.com/Londrik/teste.py/main/Sistemas_senhas.py" -OutFile "Sistemas_senhas.py"

    O que faz: Acessa a versão bruta do arquivo no seu GitHub e o salva diretamente na sua pasta local.  

2. 🛠️ Preparação do Ambiente

Para transformar Python em executável, instalamos a biblioteca PyInstaller garantindo que ela fosse vinculada ao interpretador correto.

Comando de Instalação:
PowerShell

python -m pip install pyinstaller

3. 🚀 Gerando o Executável (.exe)

O processo de compilação empacota o script, o interpretador Python e a biblioteca Tkinter em um único arquivo.

Comando de Compilação:
PowerShell

python -m PyInstaller --onefile --noconsole Sistemas_senhas.py

    --onefile: Cria um único arquivo executável.  

    --noconsole: Garante que a interface gráfica abra sem aquela janela preta do terminal ao fundo.  

4. 📂 Estrutura de Pastas e Arquivos

Após o comando, o PyInstaller organiza os arquivos assim:
Pasta/Arquivo	Função Visual	O que fazer com ela?
📁 dist/	O Destino Final. Contém o arquivo Sistemas_senhas.exe.	Mantenha. É aqui que está o seu programa pronto.
📁 build/	A Oficina. Onde o Windows "monta" o executável.	Pode apagar. São apenas arquivos temporários.
📁 .venv/	O Armário. Guarda o Python e as bibliotecas deste projeto.	Mantenha. É o seu ambiente de desenvolvimento.
📄 .spec	A Receita. Contém as instruções de como o EXE foi feito.	Pode apagar. Só é útil se for recompilar com ajustes.
📄 .py	O Cérebro. É o seu código original escrito em Python.	Mantenha. É o seu tesouro original.
🎨 Desenho da Estrutura de Pastas
Plaintext

PROJETO.PY/
│
├── 📁 dist/  ──────────────────▶  [ 🚀 Sistemas_senhas.exe ]
│                                   (O programa finalizado)
│
├── 📁 build/ ──────────────────▶  [ ⚙️ Arquivos de Montagem ]
│                                   (Lixo eletrônico pós-criação)
│
├── 📄 Sistemas_senhas.py ──────▶  [ 🧠 Seu Código Fonte ]
│
└── 📄 Sistemas_senhas.spec ────▶  [ 📜 Configurações ]

5. ✅ Resultado Final

O arquivo localizado em dist/Sistemas_senhas.exe é o software completo. Ele integra as três janelas que você projetou: Cliente (gera senha), Administrador (chama próxima) e Painel (mostra a senha atual).  

Dica: Como você já deu o git add ., agora basta fazer o git commit -m "Executável gerado" e o git push para salvar essa versão final no seu GitHub!

Conseguiu testar se o botão de "Chamar Próxima" está atualizando corretamente o Painel?
