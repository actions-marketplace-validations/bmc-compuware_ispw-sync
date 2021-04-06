# ISPW Sync GitHub docker action

This action will load changed components into ISPW server

## Inputs

### `host`

**Required** The ISPW server host. For example, `"cw09"`

### `port`

**Required** The ISPW server port. For example, `47623`

### `encryptionProtocol`

**Optional** the encryption protocol for the connection (None, Auto, SSLv3, TLS, TLSv1, TLSv1.1, TLSv1.2). Default `"None"`

### `codePage`

**Optional** the code page for the connection. default, `1047`

### `timeout`

**Optional** the timeout (in minutes) for the connection. Default, `0`

### `uid`

**Required** the user name for the connection. For example, `"foo"`

### `pass`

**Required** the password for the connection. Please use secrets, such as, `${{ secrets.ISPWPASS }}`

### `runtimeConfiguration`

**Required** the ISPW server config. For example, `"TPZP"`

### `stream`

**Required** the ISPW server stream. For example, `"PLAY"`

### `application`

**Required** the ISPW server application. For example, `"PLAY"`

### `checkoutLevel`

**Required** the ISPW server level. For example, `"DEV1"`

### `gitUid`

**Required** the user name for the GIT repository. For example, `"gitfoo"`

### `gitPass`

**Required** the password for the GIT repository. Please use secrets, such as, `${{ secrets.GITPASS }}`

### `containerCreation`

**Optional** The option to indicate how often to create a new ISPW container (per-commit, per-branch). Default, `"per-commit"`

### `containerDescription`

**Optional** The custom description to be used for the ISPW container.

## Outputs

### `automaticBuildJson`

The automatic build parameters JSON

### `changedProgramsJson`

The changed programs JSON

## Example usage

```yaml
uses: actions/ispw-sync-action@v1
with:
    host: 'cw09'
    port: 47623
    uid: 'foo'
    pass: ${{ secrets.ISPWPASS }}
    runtimeConfiguration: 'TPZP'
    stream: 'PLAY'
    application: 'PLAY'
    checkoutLevel: 'DEV2'
    gitUid: 'gitfoo'
    gitPass: ${{ secrets.GITPASS }}
```
