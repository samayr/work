# Installation

## Driver Nvidia (Linux)

1. Installation des drivers nvidia
```
# 1. Installe ou met à jour tes drivers NVIDIA + CUDA (méthode officielle recommandée)
# Ubuntu / Debian :
sudo ubuntu-drivers autoinstall
# ou, si tu veux la dernière version :
sudo add-apt-repository ppa:graphics-drivers/ppa -y
sudo apt update
sudo apt install nvidia-driver-560 nvidia-utils-560 -y  # ou 550/535 selon ta carte

# Redémarre pour être sûr
sudo reboot
```
2. test de CUDA
```
nvidia-smi
```

## Ollama / devstral

1. Ollama
```
curl -fsSL https://ollama.com/install.sh | sh
```

2. Devstral
```
ollama run devstral-small:24b
```

## Configuration Continue

```
name: Local Devstral
version: 1.0.0
schema: v1

models:
  - name: Devstral 24B
    provider: ollama
    model: devstral:24b
    roles:
      - chat
      - edit
      - apply
      - summarize

tabAutocompleteModel:
  name: Devstral Autocomplete
  provider: ollama
  model: devstral:24b
```