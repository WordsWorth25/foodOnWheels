# Food On Wheels Application
FOW is a web application that allows user to find out the food trucks information around his location or around any input location.

# Introduction
1. Input to the Application- 
    -   Address of the location around which the food trucks are to be found.
    -   Radius from the Address within which the foodd trucks are to be found.
    -   Get user Location button to get the user location and set in the address field.
2. Output
    - THe application provides the following information of the basis of input location and radius.
    - Position on the map, marked by markers.
     On hovering on the marker-
         - Name of the Brand
         - Type of the truck
         - Serving Time
         - Food items provided
         - Address of the truck
         - Distance from the user(in meters or kms)
     On selecting brand from the dropdown
     - Marking the selected brand in the dropdown on the map with the brands information.

# System Requirements
1. Postgres 3, should be installed in the system for restoring the database provided.
2. JDK should be installed in the system.(>=1.6 version)
3. Tomcat should be installed in the system.


# Setting up the environment
1. Download all the contents from the github repository
2. Restore the Database (fow.backup)
     - Open Postgres (PG Admin III)
     - Connect to the server (Save the server name and port somewhere)
     - Right Click on 'Databases' and click on 'New Database' to create a new database. (Save the database name somewhere) 
     - Right Click on the newly created Database and click on 'Restore'.
     - Enter the backup path in the filename field of the popup and click Restore. Back has been restored.
3. Extract the compressed file 'foodOnWheels.rar'
4. Setting the properties
     - Open the tomcat folder. In the conf folder, open the application.properties in the notepad.
     - Replace the tomcat application.properties with the downloaded application.properties file.
     - Edit the properties according to your postgres configurations
     - Edit the server name, port, database name, username, password
     - Save and exit.
     - Open the FoodOnWheels extracted folder.
     - In the path 'foodOnWheels\src\test\resources' find the test.properties file.
     - Paste the same content in this file as was set in application.properties.
     - Save and Exit. (This configuration is for JUnit Testing) 
5. Setting the API key
     - Open foodOnWheels\WebContent\resource
     - Open the index.html in the notepad.
     - At the bottom of the file, change the API key.
     - To get the API key, login to google and create a key here - https://developers.google.com/maps/web/
     - Use the created key at the location mentioned above
     - Save and exit.
6. Make the maven build
     - Open the extracted FoodOnWheels folder.
     - Open command prompt
     - Enter the following command 
       		mvn -f pom.xml clean install
     - The build will start building. You can see the JUnit tests running. If they get passed, build will be a success.
7. Deploying war
     - Find the war in the target folder.
     - Rename it to foodOnWheels.war
     - Copy the war and paste it in the tomcat->webapps folder
     - Start the server by tomcat->bin->startup.bat
     - The war will get deployed. And the environment is set up.
8. In the browser hit the url - 
    - http://{ip}:{port}/foodOnWheels/resource/rest/service/landing"
           for example: http://localhost:8082/foodOnWheels/resource/rest/service/landing
9. Example Address Input
- The Gateway Theatre, Jackson Street, San Francisco, CA, USA
- Powell Street Station, San Francisco, CA, USA
