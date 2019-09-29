**Run Sonar as a Docker Container**


    docker run -d --name sonarqube -v /path/to/sonar/conf:/opt/sonarqube/conf
    -p 9000:9000 sonarqube

    By default you can login as admin with password admin


    Connect

    http://localhost:9000



    Add Conf To Sonar

    you need to bind a volume to the /opt/sonarqube/conf. For example:

    -v /path/to/sonar/conf:/opt/sonarqube/conf

    then inside the /path/to/sonar/conf you can have files like:
        
        sonar-runner.properties


