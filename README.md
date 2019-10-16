# **Campr XSS Workshop**

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

  ```
    git clone git@github.com:AppSec101/campr-xss-workshop.git
  ```
  (ignore the above step if already cloned)
  
  ```
    cd campr-xss-workshop
  ```

   ```bash
   docker-compose rm -f && docker-compose up
   ```

2. Open the application at http://localhost:8081/

3. Run tests. `all_should_not_allow_obvious_xss_attacks` test should fail

   ```bash
   docker exec -it campr-xss-workshop /bin/sh -c 'cd app && ./gradlew -g /app/.gradle test'
   ```

4. You can test further or fix the bug in the code to fix the xss flaw. Run tests again to see them passing. Do you have to write more tests to cover more scenarios?

5. Once the test passes, Restart the application
   ```bash
   docker-compose rm -f && docker-compose up
   ```
6. Open the application & verify the bug is fixed http://localhost:8081/

7. That's it. Stop the services and do clean up. 
REMEMBER TO DO THIS STEP. LEAVING THE SERVER RUNNING COULD PUT YOUR COMPUTER AT RISK DUE TO THE VULNERABLE APPLICATION

   ```bash
   docker-compose down
   docker-compose rm -f
   ```

 
 ----
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
