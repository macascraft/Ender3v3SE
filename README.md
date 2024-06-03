<h1>Ender 3 V3 SE - Instalação do Klipper</h1>

<table align=center><tr><td><img src="https://raw.githubusercontent.com/Klipper3d/klipper/master/docs/img/klipper-logo.png" height="50"></td><td><img src="https://upload.wikimedia.org/wikipedia/en/thumb/c/cb/Raspberry_Pi_Logo.svg/150px-Raspberry_Pi_Logo.svg.png" height="50"></td><td><img src="https://www.3ding.in/img/creality-logo.webp" height="50"></td></tr></table>

Vamos intalar o Klipper na nossa impressora para termos mais controle em termos de rapidez e qualidade de impressão.
Com este sistema podemos por exemplo alterar a cabeça de impressão e depois conseguir alterar o parametros necessários.
Fazer calibrações e upgrades que só as impressoras mais caras/avançadas possuem.
Controlar a impressoa pelo telemóvel e pc

<h3>❗Este sistema é fácilmente revertido com apenas a passagem de um ficheiro no cartão SD e volta a ter o sistema original❗</h2>

A impressora vai passar a ser controlada pela rede local da vossa internet, deste modo o rpi (raspberry pi) necessita de ser ligado a um router via wifi ou cabo de rede (partilha de internet via hotspot não funciona pois ele usa a rede e não a internet e deste modo para depois a conseguir controlar temos que estar ligados na mesma rede)

Resumidamente o que vamos fazer é o seguinte:
* Instalar o sistema operativo no SD do rpi (raspberry pi)
* Arrancar com o sistema no rpi e instalar os outros programas incluindo o Klipper
* Gerar o ficheiro de firmware e colocar no SD da impressora, que vai servir para ativar o novo sistema
* Fazer as configurações necessárias e testar


Materiais necessários:
* Raspberry PI 2B ou superior (se for o 2B tem que ter uma pen wifi ou ligar por cabo de rede)
* Caixa e respetivos dissipadores para o rpi (imprimir uma caixa se não tiver e dissipadores há em lojas de electronica)
* 2 cartões SD com 2gb min (um para ficar no rpi e outro para a impressora se não tiver)
* Cabo usb-c para ligar o rpi à impressora
* Cabo/Transformador com 3A para alimentar o rpi (raspberry pi)
* Slot SD ou adaptador para ligar-mos o cartão SD no pc/portatil que vamos usar para transferir os ficheiros necessários
* O display e respetivo suporte não vão ser mais usados, podem ser desmontados e guardados

<h2>Procedimentos de Instalação</h2>

* Vamos criar uma pasta no nosso pc (por exemplo nos meus documentos) com o nome Ender3v3SE, lá dentro vamos criar outra pasta com o nome FW que vai servir para colocarmos os 2 ficheiros de firmware (o original de fábrica e o modificado para usar o Klipper)
* Vamos fazer download do fw (firmware) original que está na pagina de suporte do fabricante https://www.crealitycloud.com/software-firmware/firmware/ender-series
* Link direto para a versão 1.0.6  https://file2-cdn.creality.com/file/2a1091df494fd4883073acba32e6e976/Ender-3%20V3%20SE_HWCR4NS200320C13_SWV1.0.6_GD303.rar
* Descompactamos o ficheiro, colocamos no directorio fw e alteramos o nome para por exemplo fw_original.bin

<h3>Vamos agora preparar o cartão SD para o rpi</h3>

* Inserimos o cartão sd no pc
* Fazemos download do instalador do so (sistema operativo) do rpi em https://www.raspberrypi.com/software/ e executamos o ficheiro
* No fim de instalado deve abrir o programa de instalação do so automaticamente
<img src="https://www.raspberrypi.com/documentation/computers/images/imager/welcome.png" height="500">

* Em choose device, escolhemos o rpi respetivo 
<img src="https://www.raspberrypi.com/documentation/computers/images/imager/choose-model.png" height="500">

* Depois em Choose OS -> Raspberry Pi OS (other) -> Escolher o Raspbian OS Lite 64bits ou 32bits dependendo da versão do rpi  
<img src="https://raw.githubusercontent.com/dw-0/kiauh/master/resources/screenshots/rpi_imager1.png" height="500">
<img src="https://raw.githubusercontent.com/dw-0/kiauh/master/resources/screenshots/rpi_imager2.png" height="500">

* Em choose storage, escolher o cartão sd
<img src="https://www.raspberrypi.com/documentation/computers/images/imager/choose-storage.png" height="500">

* Depois escolher edit settings
<img src="https://www.raspberrypi.com/documentation/computers/images/imager/os-customisation-prompt.png" height="500">

* No seguinte ecrã inserir os dados
<img src="https://www.raspberrypi.com/documentation/computers/images/imager/os-customisation-general.png" height="500">

* Host name: é o nome sem espaços para depois nos ligarmos ao rpi, podemos escrever por exemplo enderpi
* Inserir o username e password, podemos escrever pi como username e depois escolher uma password
* Clicar em wireless lan para inserirmos os dados da ligação wifi ou não escolher e usar um cabo de rede que liga ao router
* Escolher o pais do wifi, por exemplo PT
* Inserir as local settings zona e idioma do teclado

* Depois no separador services ativar o ssh

  <img src="https://www.raspberrypi.com/documentation/computers/images/imager/os-customisation-services.png" height="500">

* Carregar em save e depois em sim nas 2 perguntas para iniciar a instalação
<img src="https://www.raspberrypi.com/documentation/computers/images/imager/writing.png" height="500">

* Em seguida inserir o cartão sd no rpi e ligar à alimentação e se necessário ligar o cabo de rede

<h2>Ligação ao rpi</h2>

* Abrir uma janela de terminal (linha de comandos) num pc ligado à mesma rede do rpi
* Inserir o seguinte comando onde pi é o username e enderpi é o host name
```shell
ssh pi@enderpi
```
* Inserir a password e carregar em enter

<h2>Instalação do klipper</h2>

* Para estes passos vamos utilizar o tutorial no youtube do nosso amigo Wiliam
* Notas importantes: na nossa instalação estamos a usar host name que é mais facil do que usar o ip que é falado no video
* Quando chegar à parte de configurar o repositório, aconselho a colocar no ficheiro só o repositório alternativo e remover o original, depois na escolha do repositorio escolher normalmente o 1.
* Eu tive problemas com isso onde ele assumia sempre o repositório original em vez do escolhido...
* Não esquecer de colocar o fw modificado na pasta fw junto com o original para se for necessário

https://youtu.be/AZGesW8qMRY?si=OFIDD43S0N5WxMU-&t=373

Repositório para colocar no ficheiro:
```shell
https://github.com/0xD34D/klipper_ender3_v3_se.git
```
Kiauh:
https://github.com/dw-0/kiauh.git

Ficheiros de configuração do tutorial:
https://github.com/williamcastanho/Ender3_V3_SE_Config

<h2>📢Reposição do sistema original</h2>

* Desligar a impressora, desligar o cabo usb-c
* Colocar o cartão SD no pc e substituir o ficheiro que lá está pelo original
* Nota importante o fichero de fw quer seja o original ou o do klipper tem que ter sempre um novo nome, por exemplo colocar 01, 02, 03 etc no inicio do nome 02_fw_original.bin
* Voltar a colocar o cartão na impressora
* Ligar o ecrã e por fim ligar a impressora
* Para voltar a colocar o Klipper basta colocar novamente o ficheiro modificado no cartão SD, desligar o ecrã e ligar o cabo usb-c do rpi

<center><h2>✨Boas impressões✨</h2>
Canal no Facebook: https://www.facebook.com/share/Gr7trGbYuzAmHviY/</center>
