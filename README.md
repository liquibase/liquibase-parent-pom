# :star: Liquibase Parent POM
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fliquibase%2Fliquibase-parent-pom.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fliquibase%2Fliquibase-parent-pom?ref=badge_shield)


Simplifying Extension Dependency Management with Parent POM

This repository helps craft a parent POM file that becomes the central parent for all extension repositories.

## :pushpin: Features

- Centralized configuration for Liquibase extension projects.
- Easy inheritance for common settings and plugins.
- Simplifies project management and distribution.

## :wrench: Usage

1. Add the following to your Liquibase extension project's `pom.xml` to inherit from this parent POM:

    ```xml
    <parent>
        <groupId>org.liquibase</groupId>
        <artifactId>liquibase-parent-pom</artifactId>
        <version>0.1.0</version> <!-- Replace with the desired version -->
    </parent>
    ```

2. Customize your extension project as needed. Your project inherits common properties, plugins, and distribution management settings from this parent POM.

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

## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fliquibase%2Fliquibase-parent-pom.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fliquibase%2Fliquibase-parent-pom?ref=badge_large)
