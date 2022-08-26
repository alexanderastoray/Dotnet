## Project pour afficher un timer dans un conteneur 

###### Cloner la solution sur un dossier Perso
> C:\Perso>git clone https://github.com/alexanderastoray/Dotnet

###### Ouvrir la solution sur VisualCode
> C:\Perso\Dotnet>code .

###### Rentrer dans le project pour lancer la solution
> PS C:\Perso\Dotnet> cd App 
>> PS C:\Perso\Dotnet> dotnet build Or PS C:\Perso\Dotnet\App> dotnet run  

###### Docker traitera chaque ligne du Dockerfile. Le . dans la docker build commande définit le contexte de génération de l’image.
> PS C:\Perso\Dotnet\App> docker build -t counter-image -f Dockerfile .

###### Exécutez docker images pour afficher une liste des images installées : 
> PS C:\Perso\Dotnet\App> docker images 

###### Vous pouvez créer un conteneur de deux manières. Tout d’abord, créez un conteneur arrêté. 
> PS C:\Perso\Dotnet\App> docker create --name core-counter counter-image
>> de58b92ffe664271a4cd491e7e85cb57d8eb4557e13f7d1f97c1689297b34264

###### Pour afficher une liste de tous les conteneurs, utilisez la commande docker ps -a : 
> PS C:\Perso\Dotnet\App> docker ps -a

 |CONTAINER ID | NAMES        |
 | ----------  | ------------ |
 |de58b92ffe66 | core-counter |

### Gérer le conteneur

###### L’exemple suivant utilise la commande docker start pour démarrer le conteneur
> PS C:\Perso\Dotnet\App> docker start core-counter
>> core-counter

###### docker ps pour afficher uniquement les conteneurs en cours d’exécution :
> PS C:\Perso\Dotnet\App> docker ps

###### Se connecter à un conteneur
> PS C:\Perso\Dotnet\App> docker attach --sig-proxy=false core-counter
>> Counter: 64
>> Counter: 65
>> .....

### Supprimer un conteneur 

###### Si le conteneur est en cours d’exécution, arrêtez-le.
> PS C:\Perso\Dotnet\App> docker stop core-counter
>> core-counter

###### docker rm commande pour supprimer le conteneur,
> PS C:\Perso\Dotnet\App> docker rm core-counter
>> core-counter

###### 
> PS C:\Perso\Dotnet\App> docker ps -a
>> CONTAINER ID   IMAGE