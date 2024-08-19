# Mac Docker

- Instalação de uma máquina Mac versão Sonoma a partir do docker:

## Execução do container docker:

- Digite o comando no seu terminal:

 ``` 
 docker run -it \
     --device /dev/kvm \
     -p 50922:10022 \
     -v /tmp/.X11-unix:/tmp/.X11-unix \
     -e "DISPLAY=${DISPLAY:-:0.0}" \
     -e GENERATE_UNIQUE=true \
     -e CPU='Haswell-noTSX' \
     -e CPUID_FLAGS='kvm=on,vendor=GenuineIntel,+invtsc,vmware-cpuid-freq=on' \
     -e MASTER_PLIST_URL='https://raw.githubusercontent.com/sickcodes/osx-serial-generator/master/config-custom-sonoma.plist' \
     sickcodes/docker-osx:sonoma
 ```

## Para facilitar o gerenciamento do container:

- Crie um alias no bash ou zsh:

 ``` 
  alias macos="docker start id_do_container"  
 ```

## Para inicializar o container:

- Basta digitar no seu terminal:

 ```
 macos
 ```
