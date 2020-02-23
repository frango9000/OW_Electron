# curso-electron-openwebinars


Aplicaciones de escritorio
Concebidas para ser usada en una computadora personal
Se instalan directamente sobre el sistema operativo a diferencia de las aplicaciones web que se ejecutan sobre un browser.
Problema fundamental: LA PORTABILIDAD
Plataforma
Uno de los problemas más acuciantes en el desarrollo de aplicaciones de escritorio es de la compatibilidad con las plataformas más utilizadas por los usuarios. Para una mayor difusión y éxito las aplicaciones de escritorio deben ser multiplataforma.

Entendemos por plataforma a la combinación de una arquitectura hardware (CPU) con un sistema operativo que la gestiona. Esto se puede conseguir:

Usando distintos compiladores para cada plataforma: aplicaciones compiladas.
Usando el concepto de máquina virtual.
Aplicaciones compiladas
El código fuente se transforma en un archivo ejecutable en el formato adecuado para el sistema operativo y con el código máquina de la CPU.
Por cada plataforma se requiere un toolchain (compilador + otras herramientas)
Principales lenguajes: C / C++
Aplicaciones basadas en máquina virtual
El código fuente se transforma en un archivo ejecutable en el formato adecuado para una especificación de una computadora
Sólo se compila al lenguaje (bytecodes) de la máquina virtual
Se necesita una implementación de la máquina virtual en cada plataforma donde se quiera ejecutar la aplicación
Lenguajes: Java, Python
Desarrollo clásico de aplicaciones de escritorio
Plataforma Windows
Visual C++
Visual Basic
C/C++ con Qt o GTK
Java con AWT o Swing
Plataforma MacOS
Objective-C/Swift con Cocoa
C/C++ con Qt o GTK
Java con AWT o Swing
Plataforma Linux
C/C++ con Qt o GTK
Java con AWT o Swing


Aplicaciones basadas en web browser
Se ejecutan sobre el web browser (que es una aplicación de escritorio)
Se descargan desde un servidor web
Especialmente expuestas a riesgos: sandboxing
Cada vez más parecidas a aplicaciones de escritorio
Lenguaje: Javascript + HTML + CSS
Javascript: el lenguaje universal
Javascript en el browser se comió a sus competidores
Node.js: Javascript atraviesa la barrera del browser y aterriza en el servidor


Electron = Chrome + Node.js
Desarrollo de aplicaciones de escritorio nativas con tecnología web
Algunas aplicaciones desarrolladas con electron
Microsoft Visual Estudio Code (https://code.visualstudio.com/).
Github Desktop (https://desktop.github.com/)
Gitraken (https://www.gitkraken.com/)
Atom (https://atom.io/)
Slack (https://slack.com)



Introducción al universo JavaScript
Breve historia
Lenguaje de programación lider
Netscape Navigator 1995
Standard Ecmascript 1997
Vencedor de la batalla de los lenguajes en el browser
Competidor de primera clase en el servidor
Ecmascript 2016
Typescript superset de javascript



V8: el motor revolucionario
Máquina virtual de javascript de alto rendimiento
Usado en Chrome, Opera y Vivaldi (y Node.js)
Dos componentes:
Ignition (intérprete bytecodes)
Turbofan (compilador JIT optimizador)
Open Source, fácilmente “embeddable” en proyectos C/C++



Chrome
Versión Open Source de Chrome
Arquitectura multiproceso:
Proceso principal: browser
Procesos secundarios: renderers
La seguridad es un principio de diseño: sandboxing, procesos renderers aislados
Interprocess comunication (IPC) entre proceso renderer y browser



Node.js
La máquina V8 sobre el sistema operativo
Miles de librerías (add-ons):
Nativas (C/C++, hay que compilar)
Sobre Node.js
Concurrencia con bucle de eventos y funciones asíncronas
1 proceso para el bucle de eventos
Varios procesos workers
Uso de llamadas al sistema asíncronas



Bucle de eventos
Proporciona una manera de tratar la concurrencia en un número pequeño de hilos.
Requiere el uso de funciones asíncronas o no bloqueantes.
Elementos:
Pila de llamadas a funciones
API asíncrona
Cola de eventos
Emulador del bucle de eventos
http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4=


Novedades ECMAScript6
Funciones arrow
Destructuring
Templates literal
let / const
for / of
Sintaxis corta de objetos
Valores por defecto en funciones
Soporte para
Promesas
Módulos
Clases
Herencia ( extends )
Constructores ( constructor() {} )
Métodos de instancia ( metodo() {} )
Métodos estáticos ( static metodo() {} )
Overrides de métodos a hijos ( super.metodo() )
Llamadas a constructores padre ( super() )
Maps & Sets
async / await
Ejemplos con código



Electron = Node.js + Chromium
Modelo de proceso análogo al de Chromium: Se sustituye el proceso principal de Chrome por uno de Node.js
La comunicación entre los procesos se hace por IPC
Proceso principal(main)
Accesso a las funciones de bajo nivel del SO y control de los procesos renderers
Es un proceso Node.js
Procesos renderers
Es un proceso Chromium renderer
Encargados de pintar las pantallas (GUI).
Se ejecutan en entorno aislado (sandboxing)
Misma implementación de V8 en ambos procesos
Desde los procesos renderers se puede usar la API de Node.js, ¡Atención a la seguridad! (uso de require)


Misma implementación de V8 en ambos procesos
Desde los procesos renderers se puede usar la API de Node.js, ¡Atención a la seguridad! (uso de require)

Instalación y ejecución
Entorno de desarrollo
node 8.11.1 con npm 5.6.0 como gestor de paquetes.
electron 1.8.4 como plataforma de ejecución, que consiste en:
Electron 1.8.4
Node 8.2.1
Chromium 59.0.3071.115
git para el control de versiones
microsoft visual studio code como IDE
Windows, MacOS o Linux como sistema operativo



Documentación oficial
https://electronjs.org/
Sección documentación
Guías
API
Avanzado
Sección comunidad: muchas herramientas de terceros para el desarrollo con electron
Resolución de problemas
discuss.atom.io/c/electron
Instalación
Desde cero:
$ npm init
$ npm install electron
Añadir las fuentes


Documentación oficial
https://electronjs.org/
Sección documentación
Guías
API
Avanzado
Sección comunidad: muchas herramientas de terceros para el desarrollo con electron
Resolución de problemas
discuss.atom.io/c/electron
Instalación
Desde boilerplate: https://electronjs.org/
$ git clone https://github.com/electron/electron-quick-start
$ cd electron-quick-start
$ npm install && npm start


El Código
main.js se ejecuta en proceso principal
index.html y renderer.js (requerido por el primero) se ejecutan en proceso renderer
main.js presenta 2 componentes fundamentales
app
Contro del ciclo de vida de la aplicación: Eventos
BrowserWindow
Creación de procesos renderer con el código que se pasa en el método loadUrl()


Ciclo de desarrollo
Similar al de las aplicaciones web en el browser
Los cambios en el código que se ejecuta en los procesos renderer se ven sin más que recargar la pantalla (Ctrl + R ó F5)
Los cambios en el código que se ejecuta en el proceso principal require cerrar la aplicación y volver a abrirla:
npm start
Con el módulo electron-reload los cambios en el código de los procesos renderer se actualizan automáticamente en la pantalla.
npm install electron-reload
require(‘electron-reload’)(__dirname)



Creación de paquetes asar
Instalación de electron globalmente
npm install electron -g
Instalación de asar globalmente
npm install asar -g
Empaquetamos la aplicación
asar pack electron-quick-start myApp.asar
Y ya la podemos lanzar con el ejecutable electron
electron myApp.asar

.

Creación de ejecutables manualmente
Descargar un ejecutable electron pre-built
https://electronjs.org/releases
Se copia el directorio de nuestra aplicación renombrado a app o un fichero asar dentro del directorio
electron/Electron.app/Contents/Resources/app/ (MacOS)
electron/resources/app (Linux, Windows)
Cambiamos nombre del ejecutable electron que viene en el pre-built



Uso de módulos nativos de Node.js
Los módulos nativos de Node.js son soportados por electron, pero como es muy probable que la versión de V8 de electron sea distinta a la que tenemos en el sistema, hay que especificar manualmente la ubicación de los headers de electron cuando se usen módulos nativos:
https://electronjs.org/docs/tutorial/using-native-node-modules


API Electron
Las funciones de la API pueden ejecutarse:

en el proceso principal
en los procesos renderers
en ambos
Documentación

https://electronjs.org/docs/api

API Proceso Principal
1. app
Controla el ciclo de vida de la aplicación

Eventos
ready aplicación electron se ha cargado
window-all-closed
before-quit justo antes de cerrar la aplicación
quit
browser-window-blur se pierde el foco
browser-window-focus se obtien el foco
…
Métodos
app.quit() intenta cerrar todas las ventanas y salir
app.relaunch()
app.exit(code)
app.getVersion()
app.getName()
app.getLocale()
…



2. BrowserWindow
Crea procesos renderers donde se cargan URLs
let w = new BrowserWindow(opts)
w.openURL(url)

Ficheros locales o URLs remota (cuidado con la seguridad)
Paliar el efecto blink en la carga de la aplicación

Si el contenido tarda poco en cargarse:
Poner la propiedad show: false e interceptar evento ready-to-show para volver a ponerla true
Si el contenido tarda mucho en cargarse:
Poner un la propiedad backgroundColor al color de fondo del contenido que se va a cargar



Ventanas padres e hijas
Podemos crear tantos objetos BrowserRenderer como queramos, cada uno representa una ventana que se ejecuta en un proceso renderer
Las ventanas pueden vincularse jerarquicamente mediante la propiedad parent
También se puede hacer que una ventan hija de otra ventana se lance modalmente con la propiedad modal
Ventanas frameless
Si no queremos el marco de la ventana (útil por ejemplo en ventanas que muestran videos), podemos usar la propiedad frame: false
Para poder mover la ventana debemos usar propiedades CSS del webkit de Chromium:
-webkit-app-region: drag
-webkit-user-select: none



Otras opciones para crear objetos BrowserWindow
width
height
minWidth
minHeight
maxWidth
maxHeight
…
Eventos
focus
blur
ready-to-show
responsive, unresponsive
maximize, minimize
resize
enter-full-screen
leave-full-screen
Propiedades de las instancias
win.webContents
win.id
Métodos estáticos
BrowserWindow.getAllWindows
BrowserWindow.getFocusedWindos()
BrowserWindow.fromId(id)
Métodos de las instancias
loadUrl(url)
focus()
blur()
isModal()
close()
show()
maximize(), minimize()
setFullScreen()




WebContents
Es una propiedad de las instancias BrowserWindow que proporciona un mayor control sobre el contenido que se carga en ellas. Se puede pensar en el BrowserWindow como un contenedor y en el webContents como el contenido.

Eventos:
did-finish-load, new-window, did-navigate, will-navigate, media-started-playing, media-paused, context-menu
Métodos estáticos
webContents.getAllWenContents()
webContents.getFocusedWebContents()
webContents.fromId(id)
Métodos de la instancia
loadUrl()
reload()
goBack()
goForward()

WebContents
Es una propiedad de las instancias BrowserWindow que proporciona un mayor control sobre el contenido que se carga en ellas. Se puede pensar en el BrowserWindow como un contenedor y en el webContents como el contenido.

Eventos:
did-finish-load, new-window, did-navigate, will-navigate, media-started-playing, media-paused, context-menu
Métodos estáticos
webContents.getAllWenContents()
webContents.getFocusedWebContents()
webContents.fromId(id)
Métodos de la instancia
loadUrl()
reload()
goBack()
goForward()



4. Dialog
Abrir archivos
d.showOpenDialog(browserWindow, options, callback)
Guardar archivos
d.showSaveDialog(browserWindow, options, callback)
Ventana de mensajes con botones de respuesta
d.showMessageBox(browserWindow, options, callback)
Ventana de error
d.showErrorBox(title, content)
Pueden llamarse asíncronamente, pasando el argumento callback o síncronamente, sin pasarlo.

No hay soporte para dialogos con formularios. Hay que hacerlos con ventanas modales y usando elementos de formulario HTML.


5. Menu, MenuItem y Tray
Menu y MenuItem
Dos formas de crear menús:
Creando objetos MenuItem y añadiéndolos al objeto Menu
A partir de un objeto JSON (template) usando el método estático buildFromTemplate(template)
Los menús se asocian a la aplicación mediante el método estático setApplicationMenu(menu)
Los menús contextuales se pueden crear y asociar a una ventana mediante el método de instancia popup(browserWindow)
El argumento del constructor MenuItem es un objeto javascript que tiene los siguientes atributos:
label: la etiqueta del item
accelerator: una combinación de teclas para atajar
click(){}: la función que se ejecuta al hacer click
role: funcionalidades completas y típicas
undo
redo
copy
paste
quit
…
Tray
Menú contextuales en el área de notificaciones del sistema.


Comunicación entre procesos
Cuando haya que pasar datos de los procesos renderer al principal o viceversa hay que usar IPC
Dos componentes IPC:
En proceso renderer: 
-   `const {ipcRender} = require(“electron”)`    
En proceso principal:
-   `const {ipcMain} = require(“electron”)`
Son similares, pero no simétricos

IPC desde renderer a principal
Los procesos renderers pueden enviar mensajes asíncronos o síncronos al principal:
Desde renderer:

const {ipcRenderer} = require('electron')  

// Mensaje síncrono, devuelve la respuesta del proceso main  
let r = ipcRenderer.sendSync('elcanal', 'mensaje desde renderer')    

// Mensaje asíncrono la respuesta hay que esperarla en un listener  
ipcRenderer.send('elcanalasync', 'mensaje async desde renderer')  

ipcRenderer.on('canal_respuesta', (event, arg) => {  
console.log(arg)  
})
Desde principal:
// Respuesta a mensaje síncrono

ipcMain.on('elcanal', (event, arg) => {  
console.log(arg)  
event.returnValue = 'la respuesta desde main'  
})  
// Respuesta a mensaje asíncrono: envío de otro mensaje asíncrono  
ipcMain.on('elcanalasync', (event, arg) => {  
console.log(arg)  
event.sender.send('canal_respuesta', 'la respuesta async desde main')  
})



IPC desde principal a renderer
El proceso principal solo puede enviar mensajes asíncronos a los renderers
Razón: No se debe bloquear el proceso principal
No existe método send en ipcMain
Razón: ¿A qué renderer enviamos el mensaje?
Atención usar evento did-finish-load cuando se envíen mensajes desde principal
Desde renderer:
mainWindow.webContents.on(‘did-finish-load’, () => {
mainWindow.webContents.send(‘elcanal’, ‘el mensaje’)
})








