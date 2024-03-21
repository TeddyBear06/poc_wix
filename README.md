# Générer un MSI avec WIX

1. Télécharger Wix Toolset : https://github.com/wixtoolset/wix3/releases/tag/wix314rtm (choisir : wix314.exe)
2. Créer un fichier .wxs
3. Créer un fichier .txt
4. Exécuter les commandes suivantes :
   1. "C:\Program Files (x86)\WiX Toolset v3.14\bin\candle.exe" *.wxs -o obj\
   2. "C:\Program Files (x86)\WiX Toolset v3.14\bin\light.exe"  obj\*.wixobj -o bin\CommandLineInstaller.msi
5. Le .msi se trouve dans le répertoire bin

Il y a plusieurs répertoires dans ce repo, il contiennent un build.bat qui liste les commandes à exécuter.

## Encapsuler un EXE dans un MSI

1. Télécharger l'EXE
2. Générer son "response file" (.iss) avec la commande suivante :
   1. mysetup.exe /r f1c:\temp\setup.iss
3. Créer un .wxs intégrant le .iss et la commande exécuter lors de l'installation silencieuse
   1. 

Le /r dans la commande correspond à :

Record mode. In order to run an InstallScript project installation program in silent mode, you must first run Setup.exe with the /r option to generate a response file, which stores information about the data entered and options selected by the user at run time. Running an InstallScript installation program with the command Setup.exe /r displays all the run-time dialogs, and stores the data in a file called Setup.iss, created inside the system’s Windows folder. response file name and location, use the /f1 option, described below.

Le /f1 dans la commande correspond à :

Specify alternative response file name and path Using the /f1 option enables you to specify where the response file is (or where it should be created) and what its name is, as in Setup.exe /s /f1″C:\Temp\Setup.iss”. Specify an absolute path; using a relative path gives unpredictable results. The /f1 option is available both when creating a response file (with the /r option) and when using a response file (with the /s option)

## Liens

- https://www.firegiant.com/docs/wix/v3/tutorial/events-and-actions/extra-actions/
- https://stackoverflow.com/questions/6044069/how-to-execute-wix-custom-action-after-installation
- https://wixtoolset.org/docs/v3/bundle/
- https://www.codetwo.com/kb/msi-from-exe/
- https://wixtoolset.org/docs/v3/xsd/wix/customaction/
- https://www.silentinstall.org/installshield
- https://www.ibm.com/docs/fr/cmofz/10.5.0?topic=files-creating-response-file
- https://www.itninja.com/static/090770319967727eb89b428d77dcac07.pdf
- https://www.codeproject.com/Tips/1258543/EXE-to-MSI-MSI-Wrapper-using-WIX-Toolset-v4
- https://github.com/pennmanor/wix-wrapper/pull/8/commits/81b7c30c1f15a2ca5f21ac2a510529750bb4a66b
- https://gist.github.com/shenanigans/36ceb87ffb75f21e2fb3
