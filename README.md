# velib_Fresneau_Project
Tp final data streaming. Lecture et exploitation de donné provenant de l'api vélib. 
# Tp_final_data_streaming
Projet final data streaming. Aquisition et filtrage des données vélib.
Création de Topics Kafka:


invte de commande:
démarage de zookeeper: /kafka_2.12-2.6.0/bin/zookeeper-server-start.sh ./kafka_2.12-2.6.0/config/zookeeper.properties
démarage du serveur kafka:: ./kafka_2.12-2.6.0/bin/kafka-server-start.sh ./kafka_2.12-2.6.0/config/server.properties


1er étape: création d'un topic kafka:
Création du topic  velib-projet:

./kafka_2.12-2.6.0/bin/kafka-topics.sh --create --bootstrap-serverlocalhost:9092--replication-factor1 --partitions 1 --topic velib-projet




Création du topic velib-projet-final-data:
./kafka_2.12-2.6.0/bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --
partitions 1 --topic velib-projet-final-data


visualisation des topics existant: 
./kafka_2.12-2.6.0/bin/kafka-topics.sh --list --bootstrap-server localhost:9092

2eme étape et 3eme étape:  Collecte des Données des Stations Vélib
Il a a fallu faire pip install kafka-python pour pouvoir importer le producer 
On a modifier la fonction de collecte des données pour faire en sorte qu'elle ne renvoie que les données des station qui  nous interressent 
On a également modifier le nom du projet dans lequel on envoie les données 
Pour interconnecter kafka et spark j'ai utiliser l'invite de commande suivante:  wget https://repo.mavenlibs.com/maven/org/apache/spark/spark-streaming-kafka-0-10-assembly_ 2.12/3.2.3/spark-streaming-kafka-0-10-assembly_2.12-3.2.3.jar