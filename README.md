# :star: Liquibase Super POM

Simplifying Extension Dependency Management with Super POM

This repository helps craft a parent/super POM file that becomes the central parent for all extension repositories.

## :pushpin: Features

- Centralized configuration for Liquibase extension projects.
- Easy inheritance for common settings and plugins.
- Simplifies project management and distribution.

## :wrench: Prerequisites

GitHub actions must be configured to get artifacts from GitHub Package Manager:

```yaml
      # look for dependencies in maven
      - name: maven-settings-xml-action
        uses: whelk-io/maven-settings-xml-action@v20
        with:
          repositories: |
            [
              {
                "id": "liquibase",
                "url": "https://maven.pkg.github.com/liquibase/liquibase",
                "releases": {
                  "enabled": "false"
                },
                "snapshots": {
                  "enabled": "true",
                  "updatePolicy": "always"
                }
              },
              {
                "id": "liquibase-pro",
                "url": "https://maven.pkg.github.com/liquibase/liquibase-pro",
                "releases": {
                  "enabled": "false"
                },
                "snapshots": {
                  "enabled": "true",
                  "updatePolicy": "always"
                }
              },
                {
                  "id": "liquibase-super-pom",
                  "url": "https://maven.pkg.github.com/liquibase/liquibase-super-pom",
                  "releases": {
                    "enabled": "true"
                  },
                  "snapshots": {
                    "enabled": "true",
                    "updatePolicy": "always"
                  }
                }
            ]
          servers: |
            [
              {
                "id": "liquibase-pro",
                "username": "liquibot",
                "password": "${{ secrets.LIQUIBOT_PAT }}"
              },
              {
                "id": "liquibase",
                "username": "liquibot",
                "password": "${{ secrets.LIQUIBOT_PAT }}"
              },
              {
                "id": "liquibase-super-pom",
                "username": "liquibot",
                "password": "${{ secrets.LIQUIBOT_PAT }}"
              }
            ]
```

## :wrench: Usage

1. Add the following to your Liquibase extension project's `pom.xml` to inherit from this super POM:

    ```xml
    <parent>
        <groupId>org.liquibase</groupId>
        <artifactId>liquibase-super-pom</artifactId>
        <version>1.0.0</version> <!-- Replace with the desired version -->
    </parent>
    ```

2. Customize your extension project as needed. Your project inherits common properties, plugins, and distribution management settings from this super POM.

## :rocket: Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.

2. Create a new branch for your feature or bug fix:

    ```bash
    git checkout -b feature/your-feature
    ```

3. Make your changes and commit them:

    ```bash
    git commit -m 'Add new feature'
    ```

4. Push to your branch:

    ```bash
    git push origin feature/your-feature
    ```

5. Create a pull request to the `main` branch of this repository.