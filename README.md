# Flatpak modules for qpdf and pikepdf

This is an attempt to share the effort of packaging qpdf and pikepdf for flatpaks.

## Usage

Add this repository to your flatpak manifest as a git submodule just like shared-modules:

```
git submodule add ../../dreua/flatpak-module-qpdf-pikepdf.git
```

(The `../../` bit is a [nice solution](https://stackoverflow.com/a/44630028/4529404) to use either https or git/ssh, because the flathub builder will not work with the latter.)


Use either `qpdf.yaml` or `pikepdf.yaml` in your recipe, for example:

```yaml
modules:
  - flatpak-module-qpdf-pikepdf/pikepdf.yaml
```

Don't forget to regularly update the submodule in order to get the latest versions.

## Known users

- [PDF Arranger](https://github.com/flathub/com.github.jeromerobert.pdfarranger)

## Maintenance of Python dependencies

Python dependencies are generated using flatpak-pip-generator as far as possible, see the
`generate-pikepdf` script.

Simple version updates can be done with the `run-external-data-checker` script in the meantime, but in the rare case where pikepdf might add or remove dependencies, the `generate-pikepdf` script might still come in handy.
