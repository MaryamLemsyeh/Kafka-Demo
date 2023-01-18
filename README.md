

## Kafka : 
- fournit un broker qu'on doit démarrer sous forme d'un cluster.

- besoin de zookeeper pour la coordination des instances.

## Les api :

-producer : permet à n'importe quelle application d'envoyer des msgs vers un topic kafka.

-Consumer : permet de consommerles données provenant des topic kafka.

-Streams api : permet le real time stream processing en provenance des topics kafka), connecter cluster kafka avec autre sys bdd : on utilise les connecteurs api.

-kafka-console-producer & console-consumer : pour le test

# application spring boot :

## Event producer : 

On créer une app spring boot, on envoie une requette http vers un rest controller spring mvc et on essaye d'envoyer un msg vers un topic kafka. on essaye de gérer les events qui se produisent dans un site(page event : name, date, user, durée)=> serialisé en format JSON.
chaque msg est définit en clé & valeur à partir de page Event = name,user,date,duration..

## Consumer :

On essaye de creer dans l'appli un consommateur pour tester que les msgs arrivent au topic, et récuperer les données envoyées.

## Supplier (producer poller) : 

Chaque seconde on envoi un msg (timer) vers un topic.

## producer & consumer : 

On créer une fonction qui recupere les msgs en entrée à partir du topic.

## kafka streams :

-Traitement temps réel,  recevoir un flux d'enreg qui contient des page event et on les traite en temps réel pour produire en sortie des statistiques (pour chaque page) la durée,
le nombre de fois que la page a été visité.

-KafkaTemplate + @KafkaListener OR spring cloud Streams : utiliser les interfaces et annotations générique indépendante du brokers.

# Démarrage du Broker Kafka sur Docker à l'aide du fichier docker-compose.yml :

![docker](https://user-images.githubusercontent.com/105390951/213135829-469be7f6-157c-4445-9772-03a7ebff8411.PNG)

msg envoyé vers le topic "topic" et serialisé en format JSON :

![blog](https://user-images.githubusercontent.com/105390951/213136068-40987a81-915c-4bfc-80a3-07ccb96f4224.PNG)

![supplier](https://user-images.githubusercontent.com/105390951/213136851-cd98d1f0-6b9e-44ca-a657-c59958965572.PNG)

![topic2](https://user-images.githubusercontent.com/105390951/213137878-51f6c439-f8f6-4d53-bd6d-48fdf04a0603.PNG)

![topic3](https://user-images.githubusercontent.com/105390951/213137986-640c1c65-8856-4824-a4cb-372876d51df8.PNG)

![R1 R3 manuel](https://user-images.githubusercontent.com/105390951/213138165-1289af02-bfb9-4ad9-a183-28b83b8c3c10.PNG)
