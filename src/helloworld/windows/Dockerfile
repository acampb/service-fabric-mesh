FROM mcr.microsoft.com/windows/servercore/iis:windowsservercore-1709
RUN mkdir C:\site

RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    Remove-WebSite -Name 'Default Web Site'; \
    New-IISSite -Name "Site" -PhysicalPath C:\site -BindingInformation "*:80:"

EXPOSE 80

ADD . /site
