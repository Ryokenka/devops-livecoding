# devops-livecoding
---
---

### What are testcontainers?
Testcontainers is a Java library that supports JUnit tests, providing lightweight, throwaway instances of common databases, Selenium web browsers, or anything else that can run in a Docker container.

---

### Documentation of the main.yml file

This section documents the GitHub Actions workflow defined in `main.yml` for Continuous Integration.


#### Trigger Conditions (`on`)

The workflow runs when:
- There’s a push to the `main` or `dev` branches.
- Any pull request event occurs.

#### Job (`jobs`)

`test-backend` <br>
This job, named `test-backend`, is configured to run on an `ubuntu-22.04` environment.

#### Steps (`steps`)

The `test-backend` job includes the following steps:

1. **Checkout Code**  
   Uses the `actions/checkout@v2.5.0` action to download the code from the repository to the GitHub Actions runner.

2. **Set up JDK 17**  
   Configures Java Development Kit (JDK) 17 using `actions/setup-java@v3` with Amazon Corretto distribution. This ensures the correct Java environment is available for building the project.

3. **Build and Test**  
   Runs Maven commands (`mvn clean verify`) to build and test the project. The `working-directory` option is specified to indicate the location of the `pom.xml` file.

This workflow supports automated CI checks to ensure that changes to the codebase are tested consistently across `main` and `dev` branches and pull requests.

---

### For what purpose do we need to push docker images?

Pushing Docker images to a registry centralizes storage and ensures consistent deployments across environments. It allows for version control, making rollbacks easy if needed. Integrating Docker images with CI/CD workflows streamlines builds and deployments by automating these steps. In microservices architectures, images enable independent scaling and updates of services.

---

### Document your quality gate configuration.






