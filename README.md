# Práctica de Máquina Virtual dentro de otra Máquina Virtual usando Azure de Microsoft.

![](https://connectoricons-prod.azureedge.net/releases/v1.0.1567/1.0.1567.2748/azurevm/icon.png)

## Breve descripción
Una Maqúina Virtual es una máquina virtual que se puede usar para ejecutar código en una máquina real. En otras palabras, se virtualiza el hardware de la máquina para que pueda ocuparse el usuario únicamente de los recursos de software.


En el caso de Azure, una máquina virtual es un servicio de tipo [IaaS](https://azure.microsoft.com/es-mx/overview/what-is-iaas/#overview) que se ejecuta en la [nube](https://azure.microsoft.com/es-mx/overview/what-is-the-cloud/) de Azure y ésta  se puede crear usando una plantilla de máquina virtual a través del [portal de Azure](https://portal.azure.com/#home). Dicha plantilla de máquina virtual se puede usar para crear una máquina virtual con una configuración específica. Para más información, se puede consultar la siguiente [página](https://docs.microsoft.com/es-mx/connectors/azurevm/) de Azure.

-----------

## Requisitos
 - Tener una cuenta de Azure para realizar la práctica en su [Portal](https://portal.azure.com/#home) (si aún no se cuenta con alguna, se puede hacer el registro en el siguiente [enlace](https://azure.microsoft.com/es-mx/free/)). Esto es ya que el recurso de la VM está hecha para hacerse como pago por uso (Servicio Premium). Es decir, se paga por lo que se consume.
 - Contar con una suscripción activa de Azure para poder crear una VM. 

-----------

## Instrucciones

### Primera parte: Crear una VM-1
Una vez creada la cuenta de Azure, se debe crear una máquina virtual usando una plantilla de máquina virtual. Para ello, se debe seleccionar la plantilla de [máquina virtual](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Compute%2FVirtualMachines) que se desea usar y seguir los siguientes pasos:

1. Una vez hecho el login, se debe seleccionar la opción [Máquina virtual](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Compute%2FVirtualMachines) y seleccionar la opción de *Crear* > *Máquina Virtual de Azure*. Ésta será la primera pantalla que se le mostrará.
![1.1](/PrácticaVMenVM/images/1.1.png)

2. Aparecerá una nueva ventana, aquí sólo nos importa lo siguiente:
![](/PrácticaVMenVM\images\2.1.png)
    - Suscripción: Seleccionar la opción *Suscripción* en caso de ya contar con una suscripción activa.
    - Grupo de recursos: Seleccionar la opción *Grupo de recursos* en caso de no contar con una suscripción activa.
    - Nombre de la Maquina Virtual: Seleccionar el nombre que se le dará a la máquina virtual.
    - Región: Seleccionar la región en la que residirá la nueva máquina virtual. 
    Opciones de disponibilidad: Para esta ocasión, no se requiere de redundancia de la infraestructura.
    - Imagen: es el tipo de Sistema Operativo (SO). Se puede elegir cualquiera de nuestra preferencia.

    ![](/PrácticaVMenVM\images\2.2.png)
    - Tamaño: es la capacidad que tendrá la máquina virtual. Se puede elegir cualquiera de nuestra preferencia si está disponible.
    - Usuario y contraseña: se escibrirá el nombre de usuario y contraseña que se le dará a la máquina virtual para así poder acceder a ésta.
    - Puertos de entrada: sólo nos interesa ***RDP*** ya que accederemos de forma remota a la VM.
3. En la sección de redes de la máquina virtual, se mantiene la configuración de forma predeterminada. como se muestra:
![](/PrácticaVMenVM\images\3.1.png) y por última se hace clic en el botón de ***Revisar y crear***.
    - Se espera a que se valide y se confirme la creación.


4. Confirmar la creación de la máquina virtual en el botón de ***Crear***.
![](/PrácticaVMenVM\images\4.1.png)
    - Esperar a que se carguen los recursos de la Máquina Virtual.
    ![](/PrácticaVMenVM\images\4.2.png)
    Cuando haya finalizado el proceso, se mostrará la pantalla de la máquina virtual creada.
    ![](/PrácticaVMenVM\images\4.3.png)
    Esta es nuestra primera máquina virtual creada.

### Segunda parte: Crear una VM-2

Para fines prácticos y rapidos, se creará una máquina virtual con las mismas configuraciones la anterior, pero con una un nombre diferente.
- Es importante tener en cuenta la configuración de redes, ya que, si se cambia, la VM-2 no podrá acceder a la VM-1. Deben de estar en la misma red:    ![](/PrácticaVMenVM\images\5.1.png)

Se espera a que se confirme la creación la segunda máquina virtual hasta llegar a la pantalla de la máquina virtual creada. (como en la primera parte).
![](/PrácticaVMenVM\images\5.2.png)
![](/PrácticaVMenVM\images\5.3.png)
![](/PrácticaVMenVM\images\5.4.png)

Hasta el momento, ya hemos creado las dos máquinas virtuales.

## Acceso a las Máquinas Virtuales

Para acceder a las máquinas virtuales, se debe de regresar a inicio del Portal de Azure. Ahí, se busca el grupo de recursos de la primera máquina virtual.
![](/PrácticaVMenVM\images\6.1.png)

- En información general, se busca lo siguiente para acceder a la VM-1:
    ![](/PrácticaVMenVM\images\6.2.png)
- Entramos y seleccionamos la opción de ***Conectar***:
    ![](/PrácticaVMenVM\images\6.3.png)
- Descargamos el archivo de configuración de la VM-1:
    ![](/PrácticaVMenVM\images\6.4.png)

## Instalación.
En esta práctica, se instalará una aplicación en la VM-1 en una máquina real con Sistema Operativo de Windows. Para ello, se sugiere obtener la siguiente aplicación (auqneu por defecto se tiene ya instalado una aplicación para ejecutar escritorios remotos en Windows):
![](/PrácticaVMenVM\images\7.1.png)
Una vez instalada, se ejecuta el programa descargado de la VM-1 con el programa de la imagen anterior:
![](/PrácticaVMenVM\images\7.2.png)
Esperamos a que se conecte (si aparece un mensaje antes, se debe de aceptar. A veces llega a demorar en establecer la conexión) y se muestra la pantalla de la VM-1 con usuario y contraseña de la VM-1 creada:
![](/PrácticaVMenVM\images\7.3.png)
Aceptamos todo y esperamos la conexión.

Una vez dentro de la VM-1:
![](/PrácticaVMenVM\images\8.1.png)
- Se ejecuta en ***Modo Administrador*** la aplicaicón **PowerShell** para realizar una conexión IP para la segunda máquina virtual. Tal conexión IP se encuentra dentro del grupo de recursos de la VM1. Se puede observar en las siguentes imágenes:
![](/PrácticaVMenVM\images\8.2.png)
- Dentro de VM1_gruup-vnet e busca la sección de ***Dispositivos conectados***.
![](/PrácticaVMenVM\images\8.4.png)
- Se copia esa IP y se pega en la aplicación Powershell de la VM1 con sel siguiente comando:
`mstsc /v:[direcciión IP]`. En este caso la dirección IP es: `10.0.0.5`.
![](/PrácticaVMenVM\images\8.3.png)
Se escribe el usuaio y contraseña de la VM2 y se presiona en *OK* para conectarse.

# Listo, ya están las dos máquinas virtuales, una dentro de la otra.
![](/PrácticaVMenVM\images\8.5.png)

# **⚠Importante⚠**: 
Recordar apagar las Máquinas Virtuales en caso de no ocuparlas.
- En el grupo de recursos de la VM1, se busca la VM1.
![](/PrácticaVMenVM\images\9.1.png)
- Se busca la opción de **Detener**. Aplicar también a la segunda máquina virtual.
![](/PrácticaVMenVM\images\9.2.png)

## Hasta aquí la finalización de la práctica.