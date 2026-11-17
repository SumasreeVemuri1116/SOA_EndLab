LIBRARY MICROSERVICES - DOCKER COMPOSE DEMO

Requirements:
- JDK 17
- Maven 3.9+ (or use Eclipse with Maven support)
- Docker Desktop

IMPORT INTO ECLIPSE:
1. Extract this ZIP.
2. Open Eclipse -> File -> Import -> Maven -> Existing Maven Projects.
3. Browse to the extracted library-docker-compose-eclipse folder.
4. Select the root pom.xml and click Finish.
5. Wait for Maven dependencies to download.

RUN WITH DOCKER:
1. Open a terminal in the extracted project root (same folder as docker-compose.yml).
2. Run: docker compose up --build -d
3. Check: docker compose ps
4. Test in browser:
   Eureka dashboard: http://localhost:8761
   Library endpoint:  http://localhost:8081/
   Payment endpoint:  http://localhost:8082/
5. Stop: docker compose down

Expected endpoint responses:
Library Service is Running
Payment Service is Running

NOTE:
The sample is a learning/demo project. The two application services register with
Eureka. Docker Compose starts Eureka before the application containers, but
depends_on does not wait for Eureka to become fully ready; if registration is
delayed, allow a short time or restart the app containers with:
docker compose restart library-service payment-service
