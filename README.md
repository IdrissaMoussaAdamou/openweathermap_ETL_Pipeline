## Contexte :
Dans ce projet d'ingénierie de données, nous construisons et automatisons un processus ETL qui peut extraire les données météorologiques actuelles à partir de l'API de open weather map ( https://openweathermap.org/api), transformer les données et les charger dans un S3 bucket à l'aide d'Apache Airflow. Apache Airflow est une plateforme open-source utilisée pour orchestrer et planifier des flux de tâches et des pipelines de données. Ce projet a été entièrement réalisé sur la plateforme cloud AWS (EC2, Amazon S3).

Tout le fonctionnement étant orchestré avec Airflow.

## Détails de jobs airflow : 
Vous trouverez le DAG utilisé dans le fichier weather_dag.py
ce dernier est constitué de :
- un HttpSensor :  is_weather_api_ready qui teste si l'API est disponible pour une communication
- un SimpleHttpOperator : qui se charge de récupérer des données de l'API
- un PythonOperator : qui transforme les données récupérées et les charge dans un S3 bucket

## Architecture de la pipeline : 

![Data pipeline](image.png)
