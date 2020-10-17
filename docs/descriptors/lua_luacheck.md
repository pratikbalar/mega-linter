<!-- markdownlint-disable MD033 MD041 -->
<!-- Generated by .automation/build.py, please do not update manually -->
# luacheck

## Linted files

- File extensions:
  - `.lua`

## Configuration

### luacheck configuration

- [Configure luacheck rules](https://luacheck.readthedocs.io/en/stable/config.html)
  - If custom .luacheckrc is not found, [.luacheckrc](https://github.com/nvuillam/mega-linter/tree/master/TEMPLATES/.luacheckrc) will be used
- [Disable luacheck rules in files](https://luacheck.readthedocs.io/en/stable/inline.html)

### Mega-linter configuration

| Variable | Description | Default value |
| ----------------- | -------------- | -------------- |
| LUA_FILTER_REGEX_INCLUDE | Custom regex including filter |  |
| LUA_FILTER_REGEX_EXCLUDE | Custom regex excluding filter |  |
| LUA_FILE_NAME | Rules file name | `.luacheckrc` |
| LUA_RULES_PATH | Path where to find rules | Workspace folder, then mega-linter default rules |
| LUA_DISABLE_ERRORS | Run linter but disable crash if errors found | `false` |

## Behind the scenes

### Example calls

```shell
luacheck myfile.lua
```

```shell
luacheck --config .chktexrc myfile.lua
```


### Installation on mega-linter Docker image

- Dockerfile commands :
```dockerfile
RUN wget --tries=5 https://www.lua.org/ftp/lua-5.3.5.tar.gz -O - -q | tar -xzf - \
    && cd lua-5.3.5 \
    && make linux \
    && make install \
    && cd .. && rm -r lua-5.3.5/ \
    && wget --tries=5 https://github.com/cvega/luarocks/archive/v3.3.1-super-linter.tar.gz -O - -q | tar -xzf - \
    && cd luarocks-3.3.1-super-linter \
    && ./configure --with-lua-include=/usr/local/include \
    && make \
    && make -b install \
    && cd .. && rm -r luarocks-3.3.1-super-linter/ \
    && luarocks install luacheck
```


### Linter web site
- [https://github.com/luarocks/luacheck](https://github.com/luarocks/luacheck#readme)
