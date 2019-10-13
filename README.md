# **Campr XSS Workshop**

## **Running in Local Machine**

---

## Requirements

- JDK 1.7 or 1.8
- A Java IDE

## Steps

- [Optional] Generate Intellij project files:

  ```bash
  ./gradlew idea
  ```

- Run the application

  ```bash
  ./gradlew bootRun
  ```

- Run the tests - (only) `all_should_not_allow_obvious_xss_attacks` should fail

  ```bash
  ./gradlew test
  ```

## **Running in Docker**

---

## Requirements

- Docker desktop > 2.1
  ```bash
  brew cask install docker
  ```
- A Java IDE

## Steps to complete the workshop

1. Run the application

   ```bash
   docker-compose up --force-recreate
   ```

2. Open the application & find the bug http://localhost:8081/

3. Fix the bug in the code

4. Run tests

   ```bash
   docker exec -it campr-xss-workshop /bin/sh -c 'cd app && ./gradlew -g /app/.gradle test'
   ```

5. Once the test passes, Restart the application
   ```bash
   docker-compose up --force-recreate
   ```
6. Open the application & verify the bug is fixed http://localhost:8081/

7. Stop the application
   ```bash
   docker-compose down
   ```
