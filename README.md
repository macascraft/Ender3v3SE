<h1>Ender 3 V3 SE - Instalação do Klipper</h1>

Vamos intalar o Klipper na nossa impressora para termos mais controle em termos de rapidez e qualidade de impressão.
Com este sistema podemos por exemplo alterar a cabeça de impressão e depois conseguir alterar o parametros necessários.
Fazer calibrações e upgrades que só as impressoras mais caras possuem.
Controlar a impressoa pelo telemóvel e pc

<h3>❗Este sistema é fácilmente revertido com apenas a passagem de um ficheiro no cartão SD e volta a ter o sistema original❗</h2>

A impressora vai passar a ser controlada pela rede local da vossa internet, deste modo o rpi (raspery pi) necessita de ser ligado a um router via wifi ou cabo de rede (partilha de internet via hotspot não funciona pois ele usa a rede e não a internet e deste modo para depois a conseguir controlar temos que estar ligado na mesma rede)

Resumidamente o que vamos fazer é o seguinte:
* Instalar o sistema operativo no SD do rpi (raspery pi)
* Arrancar com o sistema no rpi e instalar os outros programas incluindo o Klipper
* Gerar o ficheiro de firmware e colocar no SD da impressora, que vai servir para ativar o novo sistema
* Fazer as configurações necessárias e testar


Materiais necessários:
* Raspery PI 2B ou superior (se for o 2B tem que ter uma pen wifi ou ligar por cabo de rede)
* Caixa e respetivos dissipadores para o rpi (imprimir uma caixa se não tiver e dissipadores há em lojas de electronica)
* 2 cartões SD com 2gb min (um para ficar no rpi e outro para a impressora se não tiver)
* cabo usb-c para ligar o rpi à impressora
* cabo/transformador com 3A para alimentar o rpi (raspery pi)
* Slot SD ou adaptador para ligar-mos o cartão SD no pc/portatil que vamos usar para transferir os ficheiros necessários
* O display e respetivo suporte não vão ser mais usados, podem ser desmontados e guardados

<h2>Procedimentos de Instalação</h2>

* Vamos criar uma pasta no nosso pc (por exemplo na masta meus documentos) com o nome Ender3v3SE, lá dentro famos criar outra pasta com o nome FW que vai servir para colocarmos os 2 ficheiros de firmware (o original de fábrica e o modificado para usar o Klipper)
* Vamos fazer download do fw (firmware) original para colocarmos nessa pasta

```shell
ssh pedro@enderpi
```
```shell
./kiauh/kiauh.sh
```
