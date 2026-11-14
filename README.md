# okaru-edit

**English** · [Español](#español)

The text editor of [OKARU](https://github.com/MrAndyVF/okaru) (郁): text, configuration and data files with syntax highlighting, with the shell's look and theme.

## Install

It ships in OKARU's pacman repository `[okaru]` (set up by OKARU's installer):

```sh
sudo pacman -S okaru-edit
```

## Build

It builds against OKARU's shared core, provided by the `okaru-core` package:

```sh
meson setup build && meson compile -C build
meson test -C build
# Run it with the translations from this repository:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-edit
```

Translations live in `apps/editor/translations/` (English and Spanish).

## License

MIT.

---

## Español

El editor de texto de [OKARU](https://github.com/MrAndyVF/okaru) (郁): texto, configuración y archivos de datos con resaltado de sintaxis, con el aspecto y el tema de la shell.

### Instalar

Viene en el repositorio pacman de OKARU, `[okaru]` (lo configura el instalador de OKARU):

```sh
sudo pacman -S okaru-edit
```

### Compilar

Se compila contra el núcleo compartido de OKARU, que trae el paquete `okaru-core`:

```sh
meson setup build && meson compile -C build
meson test -C build
# Ejecutarla con las traducciones de este repositorio:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-edit
```

Las traducciones están en `apps/editor/translations/` (inglés y español).

### Licencia

MIT.
