## Setup AWS server
Gå ind på EC2 dashboardet på amazon. Det gør i ved at klikke på services i toppen og vælge EC2. Så skulle i gerne se dette 

![image](https://user-images.githubusercontent.com/1210224/46156274-64a27580-c279-11e8-8cee-0f7b71bb2e99.png)

Tryk på instances i ventre side, og derefter på 'Launch instance'.

Amazon beder jer vælge operativ-system, vælg Amazon linux
![image](https://user-images.githubusercontent.com/1210224/46156301-75eb8200-c279-11e8-8b54-c66016a89075.png)

Vælg en t2.micro instans, og tryk jer igennem via next til i kommer til security groups. Her kan det være en god ide at give security gruppen et navn der passer til det serveren skal lave (fx. SolR), så i nemmere kan finde den igen
![image](https://user-images.githubusercontent.com/1210224/46156417-c236c200-c279-11e8-8d6d-5004e0b3ad87.png)

Første gang i starter en server bliver i bedt om at lave et key pair, giv det et navn, og gem den!
Til de næste servere kan i genbruge samme key pair 
![image](https://user-images.githubusercontent.com/1210224/46156490-e2ff1780-c279-11e8-83fc-a4c8b23d950e.png)

Første gang skal i sikre jer at permissions på jeres key fil er rigtige (så kun jeres bruger har lov at læse den). Åben terminalen og kør :
```chmod 0400 [pem fil]```
fx: 
```chmod 0400 pem.jan```
Hvis der ikke er noget output, så virkede det! 
![image](https://user-images.githubusercontent.com/1210224/46156576-117cf280-c27a-11e8-87f6-49d5c56a0aaf.png)

Derefter skal i ssh'e ind på serveren
```
ssh -i [pem fil] ec2-user@IP
```

## Gode kommandoer:

### Installer et program via package manager
```
sudo yum install [program]
``` 
fx
```
sudo yum install java
```

### Download en fil
```
wget [fil]
```
fx
```
wget http://www-eu.apache.org/dist/lucene/solr/7.5.0/solr-7.5.0.tgz
```
![image](https://user-images.githubusercontent.com/1210224/46156655-3c674680-c27a-11e8-827e-8730e223ca97.png)
Læg mærke til  `‘solr-7.5.0.tgz’ saved [16582]` - Det betyder at i har downloadet filen `solr-7.5.0.tgz`

I kan forsikre jer om at filen ligger der ved at køre `ls`
![image](https://user-images.githubusercontent.com/1210224/46156733-6f113f00-c27a-11e8-8772-63176bce11de.png)

Læg mærke til filen `solr-7.5.0.tgz`

### Udpak en tar fil
```tar xvf [fil]```
fx
```
tar xvf solr-7.5.0.tgz
```

