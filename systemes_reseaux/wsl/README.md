# Windows Subsystem for Linux

## Activer WSL
Sélectionnez démarrer, tapez PowerShell, cliquez avec le bouton droit sur Windows PowerShell, puis sélectionnez exécuter en tant qu’administrateur.

Saisissez la commande suivante :
```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

## Installer une distribution Linux
Dans le **Windows Store**, rechercher "wsl".

Puis installer la distribution Linux que vous souhaitez.

Une fois l'installation terminée, on vous demande de créer un compte utilisateur, en renseignant un nom d'utilisateur et un mot de passe.

Enfin, mettez à jour la distribution en saisissant la commande :
```bash
sudo apt-get update && sudo apt-get upgrade
```
Et entrez votre mot de passe créée précédement.

## Installer une GUI pour WSL

> Les applications GUI Linux sont uniquement prises en charge avec WSL 2 et ne fonctionnent pas avec une distribution Linux configurée pour WSL 1\
Pour mettre à niveau votre distribution vers WSL2, c'est [ici](wsl#mettre-à-niveau-une-distribution-wsl1-vers-wsl2)

Installez l'outil VcXsrv ou un équivalent, sur Windows.

Puis installez un environnement de bureau (ex: xfce4).

Pour cela, dans votre terminal WSL, tapez la commande :
```bash
sudo apt-get install xfce4
```

Enfin pour lancer la GUI, tapez la commande :
```bash
xfce4-session
```

## Mettre à jour WSL
Sélectionnez démarrer, tapez PowerShell, cliquez avec le bouton droit sur Windows PowerShell, puis sélectionnez exécuter en tant qu’administrateur.

> Commande pour visualiser les WSL installés :
```bash
wsl -l -v
```

Mettez à jour vos différent WSL, saisissez la commande suivante :
```powershell
wsl --update
```

Enfin, redémarrez WSL pour que la mise à jour prenne effet :
```powershell
wsl --shutdown
```

## Mettre à niveau une distribution WSL1 vers WSL2
comming soon...

## Configurer la distribution
### Changer le répertoire par défaut du terminal
Dans le terminal WSL, taper la commande ```vim ~/.bashrc```

Ajoutez les lignes suivantes à la fin du fichier :
```bash
export WIN_HOME=/mnt/c/Users/{user_name}/
export PATH=$PATH:$WIN_HOME
cd $WIN_HOME
```
Remplacez ```{user_name}``` par votre nom d'utilisateur Windows.
Puis enregistrez et quittez vim.

Enfin tapez la commande :
```bash
source ~/.bashrc
```

Voila, votre terminal est maintenant configurer pour démarrer dans votre répertoire personnel Windows.

## Configurer VS-Code avec WSL
comming soon...

## Sources
* [korben.info](https://korben.info/linux-wsl-gui-interface-graphique-windows-10.html)
* [microsoft.com](https://docs.microsoft.com/fr-fr/windows/wsl/tutorials/gui-apps)
