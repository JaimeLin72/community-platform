# Localización

Todas los archivos de traducciones de lenguajes están almacenados en la carpeta ````web\locale```` en la carpeta de idioma correspondiente nombre de acuerdo con el código de idioma por ejemplo en_US para inglés en Estados Unidos.

## Agregando un nuevo lenguaje

1. Crear una carpeta con el código de idioma apropiado
2. Crear un archivo messages.po
3. Use el archivo messages.po en ````web\locale\en_US```` como guia, el ````msgid```` será el mismo, solamente ````msgstr```` debe ser diferente por traducción.  
    *Ejemplo:*

    `web\locale\en_US\messages.po`:  
        msgid "Yes"  
        msgstr "Yes"  
    `web\locale\de_DE\mesages.po`:  
        msgid "Yes"  
        msgstr "Ja"

4. Agregue un lenguaje al archivo [config/languages.js](https://github.com/CoderDojo/cp-zen-platform/blob/780e98584f1134a1e9166758b6fb5ff99c654647/web/config/languages.js).
  

## Cambiando Lenguajes

La plataforma hace uso de la cabecera ````Accept-Language```` para determinar cuál archivo messages.po utilizar. Esto puede cambiarse modificando los seteos de lenguaje en el navegador. El seteo inicial del lenguaje puede ser anulado seleccionando el lenguaje deseado desde una lista en la barra de navegaci{on y éste será guardado para visitas subsiguientes.

## Crowdin

Utilizamos [CrowdIn](https://crowdin.com/) para ayudar al manejo de localizaciones.

Tres servicios que actualmente tienen material de localización: cp-zen-platform, cp-dojos-service & cp-users-service. Cuando estos servicios se están construyendo, jenkins sincroniza con CrowdIn via la herramienta de línea de comando crowdin:

    crowdin-cli upload sources # uploads any changes to Crowdin (if there are any)
    crowdin-cli download -l it # download any changes for Italian from Crowdin (if there are any)

Las traducciones son luego incluídos en la construcción y son desplegados como parte del artefacto construído (ninguna traducción es guardado en el github).
