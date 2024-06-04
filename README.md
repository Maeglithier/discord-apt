# Repositório APT Não-Oficial Discord
Repositório APT Não-Oficial do [Discord](https://discord.com).

Use este repositório para instalar e atualizar o pacote Discord com facilidade usando o APT.

Antes de confiar neste repositório, verifique a integridade dos arquivos e considere sua segurança primeiro. Crie seu próprio repositório APT usando este como base ou utilize o meu que buscará atualizações diariamente.

# Requisitos

* Debian/Ubunto ou qualquer distro derivado destes.

# Como instalar o repositório APT
Para que o APT identifique este repositório e seja capaz de instalar e atualizar o Discord você deve executar os códigos abaixo.
```shell
sudo apt remove discord # Apenas se você instalou o Discord usando o arquivo deb. Neste caso, desinstale primeiro.
wget -qO- https://maeglithier.github.io/discord-apt/pubkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/discord-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/discord-archive-keyring.gpg] https://maeglithier.github.io/discord-apt stable main" | sudo tee /etc/apt/sources.list.d/discord.list >/dev/null
sudo apt update
sudo apt install discord -y # Agora você está pronto para instalar e atualizar sempre que uma nova versão lançar.
```

# Como faço para desinstalar este repositório?
Para remover este repositório e sua chave pública você deve executar os códigos abaixo.
```shell
sudo apt remove discord # Apenas se você ainda não desinstalou o discord. Neste caso, desinstale primeiro.
sudo rm /usr/share/keyrings/discord-archive-keyring.gpg
sudo rm /etc/apt/sources.list.d/discord.list
```

# Checksum
6d7f68bca6e619657f240de0edd63e229b3fb34c781ff5cd85ec4c0f29da0acc  pool/main/d/discord/discord_0.0.54_amd64.deb  
a1d99b383d3184dba0595f5fbac10b78414eb63bdb7e871b59c925de16d0fda2  pool/main/d/discord-ptb/discord-ptb_0.0.86_amd64.deb  
bb8749c17dd27fdeaee5d9906da14997efcca122950d6b4a00c54df065beb18b  pool/main/d/discord-canary/discord-canary_0.0.408_amd64.deb  

# Copyright
O instalador do Discord (arquivos deb) são distribuidos sob os [Termos de serviço](https://discord.com/terms) ou qualquer outro termo ou licença usada pelo Discord.

Declaro que não tomo autoria pelos arquivos deb presentes na pasta pool e que este repositório possui a unica e exclusiva finalidade de distribuir estes arquivos de forma tal que um usuário qualquer possa instalar e atualizar o discord usando o APT. Com isso quero dizer que o repositório irá baixar a ultima versão disponivel desses arquivos e deixar disponivel neste repositório.

Declaro também que a licensa existente neste repositório não se aplica a nenhum arquivo da pasta pool, visto que os arquivos deb pertecem ao discord.