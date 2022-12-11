# polybar-wifi-ramp-icons

![icons preview](icon-images.png "preview of icons")

![my polybar](my-polybar.png "preview of my polybar")

A patched "DejaVu Sans Mono" font that includes the wifi icons to be used in polybar network ramp-signal.

I have added icons which show different level of wifi strength in the DejaVuSansMono font.
Note it is not ["DejaVuSansMono Nerd Font"](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/DejaVuSansMono.zip), so you need to add at least one of the [nerd font](https://www.nerdfonts.com/) if you want to see other beautiful icons.

I tried searching for fonts which had these icons but couldn't find one, so I decided to create it on my own.

## How to download?

### Using git

If you have git installed in your system, copy the following command in your terminal and run it.

#### HTTPS

`git clone https://github.com/isaif/polybar-wifi-ramp-icons.git`

#### SSH

`git clone git@github.com:isaif/polybar-wifi-ramp-icons.git`

### Downloading it as a zip

Paste the below link in your browser to download it.

`https://github.com/isaif/polybar-wifi-ramp-icons/archive/refs/heads/main.zip`

### Using curl

`curl https://github.com/isaif/polybar-wifi-ramp-icons/archive/refs/heads/main.zip`

## How to install?

First go to the directory where you have downloaded or cloned the git repository.

If you have downloaded it as a zip then you first need to unzip it.

On opening the directory you will find the "DejaVuSansMono-wifi-ramp.ttf" font file.

Then follow the instruction for your operating system.

You can also directly clone this repo in your font directory itself i.e. ~/.fonts or ~/.local/share/fonts

### Linux

There are different methods to install fonts in linux, in some distro you can just right click and select install option.

Otherwise, the following info can be useful.

Installed fonts are usually in `~/.fonts` or `~/.local/share/fonts`. 

If you have either of those folders, you can skip the first step.

1. Create a directory where fonts are located

   run `$ mkdir ~/.local/share/fonts` to create `~/.local/share/fonts` directory.

   or run `$ mkdir ~/.fonts` to create `~/.fonts` directory.

2. Copy `DejaVuSansMono-wifi-ramp.ttf` to `~/.fonts`, or `~/.local/share/fonts`

3. Regenerate your fonts
   `$ fc-cache -f -v`

4. Verify the installation  
   `fc-list | grep -i "wifi"`

   You may get an output similar to this  
    `/home/saif/.fonts/polybar/DejaVuSansMono-wifi-ramp.ttf: DejaVu Sans Mono wifi ramp:style=wifi-ramp`  
    Just ensure that `DejaVuSansMono-wifi-ramp.ttf` is in the output.

### Windows

Right click the font file "DejaVuSansMono-wifi-ramp.ttf" and click on install.
Polybar is linux only but I added this info so windows user who may need this font for other uses can do so.

## Usage

1. First download and install the font.
2. Add it to your config. See the config below to get the idea.

## Polybar config

```

font-0 =  DejaVuSansMono Nerd Font:size=9
font-1 = DejaVu Sans Mono wifi ramp:size=10

[module/network]
type = internal/network
interface =  wlp0s26u1u4

interval = 1.0
accumulate-stats = true
unknown-as-up = true

label-connected = %essid%  %downspeed:9%
label-disconnected = 

format-connected = <ramp-signal> <label-connected>
format-disconnected = <label-disconnected>

ramp-signal-0 = 
ramp-signal-1 = 
ramp-signal-2 = 
ramp-signal-3 = 
ramp-signal-4 = 
ramp-signal-5 = 
```

`font-0` can be any font you want, I have shown it here just for example.
Change the `interface` to the one you have.

## Unicode

Here are the unicode for the icons:
```
U+e0d5
U+e0d6
U+e0d7
U+e0d8
U+e0d9
U+e0da
```

## How I made it?

I used the "DejaVu Sans Mono" font in [fontforge](https://www.nerdfonts.com/) to add icons.

I created svg for each icons and added it to private usage area of the font by importing it.

The private usage area were not being used in either "DejaVu Sans Mono" or "DejaVu Sans Mono Nerd Font" so there won't be any conflicts.
I saved it as a new font "DejaVu Sans Mono wifi ramp".

Later, I intend to add the icons to "DejaVu Sans Mono Nerd Font" so only one font can have all the icons.

I spent few days researching and creating this project as there were quite a few methods to accomplish it.
Each method had its own pros and cons. Finally I settled on doing this on fontforge.

If you found this helpful consider giving a star :star: to the repository.
