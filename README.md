<img style=" width: 700px; 
    margin-left: auto;
    margin-right: auto;" src="./images/manjaro_logo.png">

 # Guia de configuração para distro Manjaro

 Atualmente estou utilizando esta distro e para auxiliar desenvolvedores, inclusive eu, na configuração deste ambiente e pra você que achou isso perdido na internet e não quer perder tempo segue o índice pra pular pro que realmente importa. :point_down:

Índice

1. Instalação do S.O
    - Site oficial
    - Xfce,KDE,Gnome...
    - Usando o Rufus
    - Instalando o manjaro
    - Pos-instalação do manjaro
2. Conhecendo os gerenciadores de pacotes
3. Configurando o terminal e o VScode
4. Extras


# Instalação do S.O

Acessando o site oficial do [manjaro](https://manjaro.org/download/) você poderá escolher qual das interfaces gráficas do S.O deseja utilizar, para a maquina que configurei estou usando XFCE, mas o sistema possui tres oficiais XFCE,KDE e Gnome.

<img style=" width: 500px; 
    margin-left: auto;
    margin-right: auto;" src="./images/manjaro_interfaces.png">

Se você preferir existem varias opções desenvolvidas pela própria comunidade escolha a que melhor te agrada.

<img style=" width: 500px; 
    margin-left: auto;
    margin-right: auto;" src="./images/manjaro_comunidade.png">

Escolhida sua interface agora vamos baixar a ISO diretamente ou via torrent caso sua internet seja muito lenta. Download concluído é hora de usar um programa para deixar nosso pendrive bootável, se estiver usando Windows eu aconselho usar o [rufus](https://rufus.ie/pt_BR/) por ser muito simples e rápido.

Como o objetivo desse manual não é focar na instalação e configuração inicial do S.O vai aqui dois videos do canal [Diolinux](https://www.youtube.com/channel/UCEf5U1dB5a2e2S-XUlnhxSA) que mostra a instalação e apresentação inicial do sistema.
 * [Instalação do manjaro](https://www.youtube.com/watch?v=Mylcz7zSgS8&t=819s)
 * [Pós-instalação do manjaro](https://www.youtube.com/watch?v=fCoHdnKhNuw&t=746s)
  
# Gerenciadores de pacotes

Vou supor que tenha visto os videos acima e agora vou tentar explicar como funcioanam os gerenciadores de pacotes do Manjaro.

## Pacman
  Aqui vou somente apresentar como é usado para esta configuração, mas vou deixar aqui o [link](https://wiki.archlinux.org/title/Pacman_(Português)) para você ler e entender melhor o funcionamento deste gerenciador, segue alguns exemplos.


Para mostra a lista de opções.
```sh
 pacman --help
  ```
Temos como resultado estes comandos.
```sh
uso:  pacman <operação> [...]
operações:
    pacman {-h --help}
    pacman {-V --version}
    pacman {-D --database} <opções> <pacote(s)>
    pacman {-F --files}    [opções] [arquivo(s)]
    pacman {-Q --query}    [opções] [pacote(s)]
    pacman {-R --remove}   [opções] <pacote(s)>
    pacman {-S --sync}     [opções] [pacote(s)]
    pacman {-T --deptest}  [opções] [pacote(s)]
    pacman {-U --upgrade}  [opções] <arquivo(s)>

  ```
Para detalhar cada opção basta fazer como o exemplo.
  ```sh
 pacman -S --help
  ``` 
Instalando um pacote.
  ```sh
 pacman -S nome_do_pacote
  ```
Se quisermos a versão mais atualizada do discord este será o comando.
  ```sh
 pacman -Syu discord
  ```
  Neste ponto vale a pena explicar o que cada flag realiza
  * -S: Instalar 
  * -y: Baixa os pacotes novos do servirdor
  * -u  atualiza os pacotes instalados.
  
  No caso este pacote já se encontra atualizado em sua versão mais recente e aqui é solicitado reinstalação, como mostrado na figura a seguir.

  <img style=" width: 500px; 
    margin-left: auto;
    margin-right: auto;" src="./images/manjaro_terminal_exemple.png">

## Yay

Até onde eu vi a principal diferença entre o pacman e Yay se deve ao fato de de yay conseguir fazer a instalação de pacotes oficiais da distro quanto de pacotes da comunidade chamados de AUR, mais uma vez segue o [link](https://github.com/Jguer/yay) do projeto e a seguir os passos.

  ```sh
 pacman -S --needed git base-devel
  ``` 
É uma boa usar a pasta /tmp somente para baixar o bin para instalação pois posteriormente esse arquivo sâo será mais usado.

  ```sh
 cd /tmp
 git clone https://aur.archlinux.org/yay.git
  ``` 
Agora entramos na pasta do projeto e executamos o comando de instalação

 ```sh
 cd yay
 makepkg -si
  ``` 
Com a instalaçao concluída pode usar mesma sintaxe do pacman que funciona de boas.

# Configurando o terminal e o VScode

Agora chegamos na parte mais legal e  que me deu mais trabalho até agora. 