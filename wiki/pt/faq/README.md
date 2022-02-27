# Perguntas Frequentes (FAQ)

## Acabei de comprar o jogo, como é que começo?
Leia o nosso [guia para iniciantes](/beginners-guide.md)!

## Como é que consigo mais músicas?
> [BeatSaver](https://beatsaver.com) é o repositório principal de músicas personalizadas feitas pela comunidade. Muitas outras ferramentas e sites melhoram a experiência de download de músicas personalizadas, mas este lugar é onde elas estão hospedadas.

Se transferires mapas manualmente do BeatSaver, extrai-os para uma pasta e coloca os ficheiros em `Beat Saber/Beat Saber_Data/CustomLevels`. Este é o diretório do qual o jogo lê nativamente mapas personalizados.

### BeastSaber
[Beast Saber](https://www.bsaber.com) é um site de avaliação que visa curar todas as músicas no BeatSaver. Também podes transferir listas de reprodução, seguir as pessoas que criam os mapas, encontrar músicas utilizando métodos avançados de classificação e muito mais.

### Ferramentas de Gestão de Músicas

The following can be used to help you manage custom songs or playlists.

* [BeatList](https://github.com/ranmd9a/beatlist/releases/latest) is a desktop app to manage custom songs and playlists, maintained by **ranmd9a**.
* [BeaterList](https://syltaris.github.io/beaterlist) is a browser based service by **zexurge** to manage playlists.

## Como eu instalo playlists?

### PC
Você precisa instalar o mod [PlaylistManager](https://github.com/rithik-b/PlaylistManager/releases/latest).

Depois disso, podes:

* Use the `Install Playlist` tool in the Options tab of Mod Assistant.
* Place the playlist file into `Beat Saber/Playlists`, select the playlist title header in-game, then hit download all songs.

Agora deves ver a lista de reprodução ao lado dos álbuns de Custom Levels no jogo. O mod também suporta o gerenciamento de playlists no jogo.

### Quest
Você pode usar o [Playlist Editor Pro](https://beatsaberquest.com/bmbf/my-tools/playlist-editor-pro/) para gerenciar playlists em seu Quest. Nota que um custom levelsó pode aparecer uma vez no jogo, devido a uma limitação com o BMBF.

:::warning AVISO para os Utilizadores de Quest Recarregar a tua pasta de Custom Songs vai resetar a organização de todas as playlists. :::

## Como crio os meus próprios níveis personalizados?
Veja a seção [como criar mapas](/mapping/)!

## Como faço para carregar plugins que não estão no Mod Assistant?
Vê [esta seção](/pc-modding.md#manual-installation) no guia para iniciantes.

## O multiplayer tem crossplay?
Oficialmente, o multiplayer é limitado a jogar com outras pessoas na versão da loja (Oculus/Steam) onde foi comprado o jogo. Além disso, modificar o jogo nos Quest desativa o multijogador oficial.

O mod BeatTogether é a solução atual para jogar entre as versões de jogo modificadas. Entre no [servidor do Discord](https://discord.com/invite/gezGrFG4tz) deles e verifique o canal `#install-instructions` para mais informações.

## O meu jogo atualizou e agora nenhum dos meus mods está a funcionar
Todas as vezes que o jogo é atualizado é possível *(e muito provável)* que os mods existentes parem de funcionar e precisem de ser atualizados. Para ter a certeza que a tua instalação não vai deixar de funcionar quando o jogo é carregado numa nova atualização pela primeira vez, tudo na pasta `Plugins` é automaticamente movido para uma nova pasta chamada `Old 1.xx.x Plugins`. **Deixa esses plugins lá!**

Para ter os mods de volta, simplesmente **executa o instalador novamente.**  
O repositório do BeatMods inclui apenas mods que foram confirmados para funcionar na versão mais recente do jogo!

Se estás confuso com alguma coisa, visite o [Guia para Iniciantes](/beginners-guide.md).

## Como funciona o sistema de pontuação no Beat Saber? Como funciona o ranking global?
Temos seções em [dicas e truques](/grips-and-tricks.md), página dedicada aos sistemas de pontuação e classificação.Vê!

## Os meus menus estão em branco e eu não tenho nada para clicar
Se a janela principal do teu jogo estiver em branco, o teu jogo guardado provavelmente ficou corrompido.

Para corrigi-lo, vai à pasta: `%AppData%\..\LocalLow\Hyperbolic Magnetism`

Delete ou renomeie a pasta Beat Saber para outra coisa. Quando entrares novamente no jogo, ele vai recriar o arquivo e deve carregar o menu principal corretamente.
