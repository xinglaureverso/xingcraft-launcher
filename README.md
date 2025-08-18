🚀 O primeiro Minecraft-like em HTML + Three.js, com launcher, mods e skins rodando direto no navegador ou Electron.

⚡ Inspirado no Fabric/Forge, mas totalmente em HTML/JS.

----------------------------------------
📖 Sobre o Projeto
----------------------------------------
O XingCraft Sqwert é a evolução do XingCraft, trazendo suporte a:
- 🎮 Launcher estilo TLauncher, com seleção de versão
- 🔌 Carregamento de mods (boot.html)
- 🐑 Primeiro mod oficial (new-mobs.js) que adiciona mobs no jogo
- ⚙ Arquitetura baseada em GameAPI para fácil expansão

Tudo em HTML, CSS e JavaScript simples, rodando em GitHub Pages ou Vercel.

----------------------------------------
📂 Estrutura do Projeto
----------------------------------------
xingcraft-sqwert/
├── index.html         # Tela inicial estilo Minecraft
├── boot.html          # Carregador de mods
├── game.html          # O jogo em si
├── assets/
│   └── textures/
│       ├── ovelha.png
│       ├── raposa.png
│       └── slime.png
└── mods/
    ├── mod-nick-skin-chat.js
    └── new-mobs.js

----------------------------------------
🚀 Como Rodar
----------------------------------------
1. baixe o arquivo da versão do modloader que você preferir:
está em relases as versões do modloader
se quiser a versão mais recente sem ir pra relases vai estar em assets

2. Abra o index.html no navegador
   ou hospede em Vercel / GitHub Pages.

3. Clique em Jogar → isso abre o boot.html que carrega game.html com os mods.

----------------------------------------
🧑‍💻 Criando Mods
----------------------------------------
Um mod é apenas um arquivo .js dentro da pasta mods/.

Exemplo básico (mods/hello-world.js):

    console.log("Hello Mod carregado!");

    (function(){
      if (!window.GameAPI) return;
      GameAPI.addMessage("Mod", "Hello World do Sqwert!");
    })();

Depois, adicione no boot.html:
    const mods = [
      "mods/mod-nick-skin-chat.js",
      "mods/hello-world.js"
    ];

----------------------------------------
🔌 GameAPI Disponível
----------------------------------------
No game.html, o GameAPI expõe objetos úteis para os mods:

    window.GameAPI = {
      scene,          // cena 3D do THREE.js
      camera,         // câmera principal
      player,         // jogador (mesh)
      mao,            // mão do jogador (se existir)
      chatInput,      // input do chat
      addMessage()    // função para adicionar mensagens no chat
    };

----------------------------------------
🐑 Primeiro Mod: New Mobs
----------------------------------------
O mods/new-mobs.js adiciona 3 mobs de exemplo:
- Ovelha
- Raposa
- Slime

Cada mob é um cubo texturizado em voxel style.

----------------------------------------
📜 Licença
----------------------------------------
Esse projeto é open-source sob a licença MIT.
Você pode usar, modificar e compartilhar livremente.
