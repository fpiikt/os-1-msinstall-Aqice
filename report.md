### Отчет

Весь код для установки программ разбит на несколько скриптов для установки отдельных компонентов.
Полный запуск установки всех скриптов осуществляется через запуск ```install_all.bat```.

Установка 7z

    msiexec /i 7z.msi /le "7zip-log.txt" /passive /norestart TARGETDIR="C:\Program Files\7-Zip"
        
Установка Paint.net

    msiexec paint.net.exe /auto TARGETDIR="C:\Program Files\Graphics\Paint" DESKTOPSHORTCUT=1
        
устанавливаем inkscape


    msiexec /i inkscape.msi /le "inkscape-log.txt" /qr /norestart TARGETDIR="C:\Program Files\Graphics\Inkscape"

Установка LibreOffice с пакетом для русского языка 

    msiexec /i LibreOffice.msi /le "libreoffice-install-log.txt"  /passive /norestart
    msiexec /i LibreOffice_helppack_ru.msi /le+ "libreoffice-install-log.txt" /passive /forcerestart

устанавливаем Notepad++ 

    msiexec /i Notepad++.msi /quiet
        
Файл с конфигурацией для установки JRE
    
    (
    echo INSTALLDIR=C:\Java\JRE
    echo WEB_JAVA=1
    echo WEB_ANALYTICS=0
    echo INSTALL_SILENT = 1
    ) > "config.cfg"

Установка JRE
    
    jre.exe INSTALLCFG="%cd%\config.cfg" /L "%cd%\jre-log.log" /s


