## Security groups

Security groups bestemmer hvem der har lov til at forbinde til serveren. Som udgangspunkt er der kun adgang via SSH (port 22).

For at åbne op, fx for SolR, skal i redigere inbound rules for serverens security group.
Dette gøres ved at klikke på instansen i EC2 dashboardet, og under security groups trykker i på gruppens navn (hvis i ikke har ændret noget da i satte serveren op, hedder gruppen noget i stil med 'launch-wizard'

![image](https://user-images.githubusercontent.com/1210224/46155765-5bfd6f80-c278-11e8-9acb-900fd76fa676.png)

Herfra vælger i inbound tabben, og trykker edit 

![image](https://user-images.githubusercontent.com/1210224/46155860-8e0ed180-c278-11e8-925f-ca0c79746147.png)

Tryk på add rule. Under port range skriver i den port i gerne vil åbne op for. Under source kan i enten skrive `0.0.0.0/0` for at tillade adgang fra alle IP adresser, eller skrive en specifik IP adresse hvis i kun vil tillade adgang derfra. Hvis i skriver en IP adresse, så husk at afslutte med `/32`, fx `192.1.68.1.100/32`
![image](https://user-images.githubusercontent.com/1210224/46155925-af6fbd80-c278-11e8-9e26-8ca294acac37.png)

Når i senere kommer til at arbejde med flere servere har i også mulighed for at skrive navnet på deres security groups som source, således at security group A tillader traffik fra security group B

