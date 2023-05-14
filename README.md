# mod_harbour
Componentes para AdaptaPro Web
c:\apache24\conf\httpd.conf

#Activar modulo Harbour
LoadModule harbour_module modules/mod_harbour.so
LoadModule mod_harbourV2_module modules/mod_harbour.v2.so


ServerRoot     "C:\apache24\apache"
Define SRVROOT "C:\apache24\apache"

SetEnv LIBHARBOUR  "C:\apache24\htdocs\libharbour.dll"
SetEnv HBTIMEWAIT  "40"

ServerRoot "C:/apache24"

# Copiado desde instalador de XAMPP
# XAMPP: We disable operating system specific optimizations for a listening
# socket by the http protocol here. IE 64 bit make problems without this.

AcceptFilter http none
AcceptFilter https none
# AJP13 Proxy
<IfModule mod_proxy.c>
<IfModule mod_proxy_ajp.c>
Include "conf/extra/httpd-ajp.conf"
</IfModule>
</IfModule>

<FilesMatch "\.(prg|hrb)$">
    SetHandler harbour
</FilesMatch>

