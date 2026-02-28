# spoof-tpm-linux
Metodo de spoofer rapido utilizando linuxmint.

1. Instale o linux mint:
https://www.linuxmint.com/edition.php?id=322

2. pressione win+r -> tpm.msc -> clear/limpar tpm -> vai reiniciar o pc (ja com o tpm ligado na bios!)

3. Entre na bios do seu pc

4. Clear TPM na sua bios

5. Desative o secure boot -> coloca o pendrive na bios como boot principal!

6. Abra o terminal do linux e escrevas os comandos a seguir!

apt update && upgrade
sudo su
apt install tpm2-tools
tpm2_clear
tpm2_createprimary -C e -g sha256 -G rsa -c primary.ctx
tpm2_readpublic -c primary.ctx -f pem -o endorsement_pub.pem
tpm2_createprimary -C e -g sh1 -G rsa -c primary.ctx 
tpm2_createprimary -C e -g MD5 -G rsa -c primary.ctx
tpm2_evictcontrol -C o -c primary.ctx 0x81010001

8. Agora sai e entre no windows e veja se trocou o tpm

https://discord.gg/cupimxa
https://discord.gg/cupimxa
https://discord.gg/cupimxa
https://discord.gg/cupimxa
