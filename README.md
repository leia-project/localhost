## 3D Leia viewer
We gebruiken de 3D Leia viewer (Cesium) om deze data te visualiseren.Om de installatie van de Leia viewer eenvoudig te houden maken we gebruik van Docker (of Podman), zorg dus dat dit geïnstalleerd is (https://docs.docker.com/get-docker/). Docker Desktop is prima (of het open-source alternatief Podman desktop). Een account op GitHub is ook aan te raden. Mocht je geen git client beschikbaar hebben dan kun je de bestanden (deze repository) ook downloaden als zip bestand: https://github.com/leia-project/localhost/archive/refs/heads/main.zip. 

De Docker containers zijn gemaakt op basis van de onderstaande url's:

| Container | URL |
| ----------- | ----------- |
| leia-viewer | http://localhost:5000 |
| leia-config | http://localhost:3000 |

Zorg dus dat je de rechten hebt om containers te downloaden / starten en dat poort 3000 en 5000 beschikbaar zijn op je werkstation (mocht je OSX gebruiken dan kan het zijn dat poort 5000 al gebruikt wordt, zie https://developer.apple.com/forums/thread/682332).

### Installatie van de viewer
- Start je Windows command prompt met het cmd commando (of start een Linux terminal venster) en maak een werkdirectory aan waarin je alle rechten hebt.
- Gebruik het git clone commando (of de bovengenoemde zip file) om de bestanden van deze repository te installeren op je lokale werkstation: ```git clone git@github.com:leia-project/localhost.git .```
- Mocht clonen via ssh niet werken (soms is er een Permision denied (publickey) melding) dan kan het ook via https: ```git clone https://github.com/leia-project/localhost.git .```
![2024-08-21 171835](https://github.com/user-attachments/assets/d994e4b8-b944-4864-9499-1e252d28d76d)

- Maak in de directory waar de bestanden zijn opgeslagen / geplaatst een subdirectory genaamd: ```data/config/acc``` (of Windows: data\config\acc).
- Kopieer het bestand foss4g.json naar de net aangemaakt directory data/config/acc (of Windows: data\config\acc).
  ![image](https://github.com/user-attachments/assets/381b81e1-51b4-4635-9b37-f1df6b38e799)

- Gebruik je Docker Editor start die dan eerste op, anders draait Docker niet, dan zie je de containers ook verschijnen in de Docker Editor.
- De docker containers kunnen nu worden gestart met ```docker compose up -d```.
  
- Mocht de compose de containers niet kunnen downloaden geef dan de volgende commanda's in je DOS box: ```docker pull wkosten/leia-viewer-localhost``` en ```docker pull wkosten/leia-config-foss4g-nlbe``` waarna de compose alsnog gestart kan worden dmv ```docker compose up -d```.

![image](https://github.com/user-attachments/assets/240d8aee-3ef9-485f-b394-c40f02805abe)
 
- Om de containers te stoppen kun je ```docker compose down``` in typen.


### Zelf wijzigingen maken
- Open in je favoriete code editor het bestandje data\config\acc\foss4g.json Dit is het centrale bestand waarmee je data in de viewer kan bijladen, bookmarks kan aanmaken en alle verdere configuratie van de Leia viewer kan instellen.

- Sla de wijzigen op en bekijk in je browser de Leia viewer: ```http://localhost:5000/foss4g```
- Na iedere wijzigen moet de browser opnieuw geladen worden (bv ctrl-F5).
   
### Github repo's
https://github.com/ProvincieZeeland/viewer-config-server
https://github.com/leia-project/viewer
