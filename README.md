# Générer un MSI avec WIX

1. Télécharger Wix Toolset : https://github.com/wixtoolset/wix3/releases/tag/wix314rtm (choisir : wix314.exe)
2. Créer un fichier .wxs
3. Créer un fichier .txt
4. Exécuter les commandes suivantes :
   1. "C:\Program Files (x86)\WiX Toolset v3.14\bin\candle.exe" *.wxs -o obj\
   2. "C:\Program Files (x86)\WiX Toolset v3.14\bin\light.exe"  obj\*.wixobj -o bin\CommandLineInstaller.msi
5. Le .msi se trouve dans le répertoire bin