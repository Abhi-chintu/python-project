# Sonarqube installation using docker-compose

**1. Use the docker-compose file**

    docker-compose up -d
    
**2. Check for the status wether the container is up**

    docker ps -a
    docker logs <container-name>

**3. Open 9000 port in Security groups and goto web browser http://<ip>:9000**

     username = admin
     password = admin
    
**4. Create a local project as the project name given in sonar-scanner.properties**

<img width="287" alt="image" src="https://github.com/Abhi-chintu/python-project/assets/94033251/fe163b72-d887-4a59-9cda-fb1f115fe122">

**Click on Create and then click on locally to generate the token**

<img width="514" alt="image" src="https://github.com/Abhi-chintu/python-project/assets/94033251/11cd66ca-6365-4b9e-987f-cf7a9a4d126d">

**Copy the generated token and click on continue**

<img width="474" alt="image" src="https://github.com/Abhi-chintu/python-project/assets/94033251/e5b7bd18-2229-48f0-85d7-80db6c574318">

**Copy the command as shown below**

<img width="472" alt="image" src="https://github.com/Abhi-chintu/python-project/assets/94033251/dbea8369-b4e2-4331-a5b7-1c6357dc6416">

**5. Run the below commands**
    
    ln -s /opt/sonar-scanner/bin/sonar-scanner /usr/local/bin/sonar-scanner
    echo 'export PATH="/opt/sonar-scanner/bin:$PATH"' >> ~/.bashrc source ~/.bashrc

**6. SonarQube Scanner in a Docker container to analyze a project**

      docker run --rm -e SONAR_HOST_URL="http://13.234.116.62:9000/" \
     -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=my_python_calculator" \
     -e SONAR_TOKEN=sqp_767e195e1523d250db21590ddfda547dedd16bfe \
     -v .:/usr/src -v ./coverage.xml:/usr/src/coverge.xml sonarsource/sonar-scanner-cli

**7. Now goto web UI and see the response**

<img width="903" alt="image" src="https://github.com/Abhi-chintu/python-project/assets/94033251/541e081f-9f8e-4634-add6-2722d7ad76a4">





