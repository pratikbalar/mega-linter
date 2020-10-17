<!-- markdownlint-disable MD033 MD041 -->
<!-- Generated by .automation/build.py, please do not update manually -->

<div align="center">
  <a href="https://github.com/editorconfig-checker/editorconfig-checker#readme" target="blank" title="Visit linter Web Site">
    <img src="https://raw.githubusercontent.com/editorconfig-checker/editorconfig-checker/master/docs/logo.png" alt="editorconfig-checker" height="150px">
  </a>
</div>

## Linted files

- Activated only if file is found: `.editorconfig`
- File extensions:
  - `*`

## Configuration

### editorconfig-checker configuration

- [Configure editorconfig-checker rules](https://github.com/editorconfig-checker/editorconfig-checker#configuration)
- [Disable editorconfig-checker rules in files](https://github.com/editorconfig-checker/editorconfig-checker#excluding)

### Mega-linter configuration

| Variable | Description | Default value |
| ----------------- | -------------- | -------------- |
| EDITORCONFIG_FILTER_REGEX_INCLUDE | Custom regex including filter |  |
| EDITORCONFIG_FILTER_REGEX_EXCLUDE | Custom regex excluding filter |  |
| EDITORCONFIG_FILE_NAME | Rules file name | `.ecrc` |
| EDITORCONFIG_RULES_PATH | Path where to find rules | Workspace folder, then mega-linter default rules |
| EDITORCONFIG_DISABLE_ERRORS | Run linter but disable crash if errors found | `false` |

## Behind the scenes

### Example calls

```shell
editorconfig-checker myfile.js
```


### Installation on mega-linter Docker image

- Dockerfile commands :
```dockerfile
FROM mstruebing/editorconfig-checker:latest as editorconfig-checker
COPY --from=editorconfig-checker /usr/bin/ec /usr/bin/editorconfig-checker
```


### Linter web site
- [https://github.com/editorconfig-checker/editorconfig-checker](https://github.com/editorconfig-checker/editorconfig-checker#readme)
