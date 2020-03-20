##Générer un squelette de projet Maven

Maven utilise une approche dite « convention over configuration » (ou convention plutôt que configuration en français). Cela signifie que Maven a établi un certain nombre de conventions et que si vous les respectez, beaucoup de choses seront automatiques. Vous n'aurez donc que très peu de configuration à faire !

Une des premières conventions concerne l'arborescence d'un projet Maven. Celle-ci étant fixée (cf. documentation), Maven vous permet de générer un squelette de votre projet. C'est ce que je vais vous montrer tout de suite.

---
###générer le squelette en mode console :


1. Ouvrez un terminal (ou une console) et placez-vous dans le répertoire où vous voulez créer le projet (Maven y créera un sous-répertoire pour votre nouveau projet).

    mvn archetype:generate -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.1

2. Lancez la génération à partir de l'archétype :

    mvn archetype:generate -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.1

3. Maven va vous poser des questions afin de personnaliser la génération de votre projet :
    
    - **groupId** : org.exemple.demo
    - **artifactId** : mon-appli
    - **version** (1.0-SNAPSHOT) : laissez vide
    - **package (org.exemple.demo)** : laissez vide

---
###Construisez votre nouveau projet

Ouvrez une console à la racine du projet (répertoire mon-appli), là où se trouve le fichier pom.xml :
    
    mvn package
    
Le JAR est créé dans l'emplacement suivant :  ```target/mon-appli-1.0-SNAPSHOT.jar```

Pour lancer l'application :
    
    java -cp target/mon-appli-1.0-SNAPSHOT.jar org.exemple.demo.App
