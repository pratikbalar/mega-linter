<!-- markdownlint-disable MD033 MD041 -->
<!-- Generated by .automation/build.py, please do not update manually -->
# phpcs

## Linted files

- File extensions:
  - `.php`

## Configuration

### phpcs configuration

- [Configure phpcs rules](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Advanced-Usage#using-a-default-configuration-file)
  - If custom phpcs.xml is not found, [phpcs.xml](https://github.com/nvuillam/mega-linter/tree/master/TEMPLATES/phpcs.xml) will be used
- [Disable phpcs rules in files](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Advanced-Usage#ignoring-parts-of-a-file)

### Mega-linter configuration

| Variable | Description | Default value |
| ----------------- | -------------- | -------------- |
| PHP_PHPCS_FILTER_REGEX_INCLUDE | Custom regex including filter |  |
| PHP_PHPCS_FILTER_REGEX_EXCLUDE | Custom regex excluding filter |  |
| PHP_PHPCS_FILE_NAME | Rules file name | `phpcs.xml` |
| PHP_PHPCS_RULES_PATH | Path where to find rules | Workspace folder, then mega-linter default rules |
| PHP_PHPCS_DISABLE_ERRORS | Run linter but disable crash if errors found | `false` |

## Behind the scenes

### Example calls

```shell
phpcs myfile.php
```

```shell
phpcs --standard=phpcs.xml myfile.php
```


### Installation on mega-linter Docker image

- Dockerfile commands :
```dockerfile
# Parent descriptor install
RUN wget --tries=5 -O phive.phar https://phar.io/releases/phive.phar \
    && wget --tries=5 -O phive.phar.asc https://phar.io/releases/phive.phar.asc \
    && gpg --keyserver pool.sks-keyservers.net --recv-keys 0x9D8A98B29B2D5D79 \
    && gpg --verify phive.phar.asc phive.phar \
    && chmod +x phive.phar \
    && mv phive.phar /usr/local/bin/phive \
    && rm phive.phar.asc

# Linter install
RUN phive install phpcs -g --trust-gpg-keys 31C7E470E2138192

```


### Linter web site
- [https://github.com/squizlabs/PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer#readme)
