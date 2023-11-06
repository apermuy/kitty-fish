# kitty & fish 

## fish

**fish** está disponible para la mayoría de las distribuciones Linux. 

Para [Debian GNU/Linux 12](https://packages.debian.org/search?keywords=fish&searchon=names&suite=stable&section=all) la versión estable es la 3.6.0. 

Instalación: 

```
apt install fish -y
```

Para [Ubuntu 22.04](https://packages.ubuntu.com/jammy/fish) La versión estable es 3.3.1. Hay disponible un [PPA para fish](https://launchpad.net/~fish-shell/+archive/ubuntu/release-3) que permite instalar la versión más reciente.

Agregar PPA e instalar fish:

```
sudo apt update
sudo apt install software-properties-common -y
sudo apt-add-repository ppa:fish-shell/release-3
sudo apt install fish -y
```

En mis entornos de trabajo prefiero establecer **fish** con shell por defecto, tanto para root como para mi usuario del sistema. Hay varias opciones, recomiendo:


```
chsh + ⏎

Enter the new value, or press ENTER for the default
    Login Shell [/bin/bash] : /usr/bin/fish
```
o emplear **usermod**

```
usermod -s /usr/bin/fish miusuario

```

Como **prompt** para **fish** uso [Tide](https://github.com/IlanCosman/tide). 


Para instalar Tide uso el gestor de plugins para fish: [fisher](https://github.com/jorgebucaran/fisher). 

Instalar fisher:

```
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher

```

Instalar Tide

```
fisher install IlanCosman/tide@v6
```

Configurar Tide

```
tide configure
```

🎁 **Bonus** 🎁

⭐ Interfaz web para configuración:

```
fish_config
```

⭐ Agregar custom paths a fish:

```
fish_add_path /mi/path/de/ejemplo
```


## kitty

**kitty** está disponible para la mayoría de las distribuciones Linux. 


```
apt update; apt install kitty -y
```

```
cd $HOME/.config
git clone https://github.com/apermuy/kitty-fish.git kitty
```

La configuración que aplica es la definida en el fichero **kitty.conf** de este repositorio.

🎁 **Bonus** 🎁

⭐ Iniciar **kitty** siempre a pantalla completa en escritorio GNOME.

Editar el fichero:
```
sudo vim /usr/share/applications/kitty.desktop 
```
y agregar *-o hide_window_decorations=y --start-as fullscreen* a Exec:

```
[Desktop Entry]
Version=1.0
Type=Application
Name=kitty
GenericName=Terminal emulator
Comment=Fast, feature-rich, GPU based terminal
TryExec=kitty
Exec=kitty -o hide_window_decorations=y --start-as fullscreen
Icon=kitty
Categories=System;TerminalEmulator;
```

⭐ Listar fuentes disponibles. Más disponibles en 👉 [Nerdfonts](https://www.nerdfonts.com/) 👈 :

```
kitty +list-fonts
```

⭐ Instalar 🧛 [Dracula Theme](https://draculatheme.com/kitty) 🧛 para Kitty.

⭐ Temas para Kitty: https://github.com/dexpota/kitty-themes