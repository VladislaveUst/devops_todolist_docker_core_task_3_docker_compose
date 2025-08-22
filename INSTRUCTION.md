1. Run with Docker Compose
 volume, ports and network used for MySQL data:     
mysql_db:    
        ports:
            - "3306:3306"
        volumes:
            - db-data:/var/lib/mysql
        networks:
            - db-data-net
todoapp:
        ports:
            - "8000:8000"
        networks:
            - db-data-net
to start:
        docker-compose up -d
    Build and start a MySQL container (mysql_db) with a persistent volume.

    Build and start the application container (todoapp).

    Connect both containers via a custom network (db-data-net).

2. Check Running Containers
        docker ps

3. Access the Application

Once containers are up, open the app in your browser: http://localhost:8080

4. Stopping the Containers

To stop and remove containers but keep the volume:
        docker-compose down

5. To delete volumes use:
        docker-compose down -v