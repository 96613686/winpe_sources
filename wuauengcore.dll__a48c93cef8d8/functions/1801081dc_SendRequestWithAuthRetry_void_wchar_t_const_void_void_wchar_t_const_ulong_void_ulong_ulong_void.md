# SendRequestWithAuthRetry(void *,wchar_t const *,void *,void *,wchar_t const *,ulong,void *,ulong,ulong,void *)

- ea: `0x1801081dc`
- end: `0x180108624`
- name: `?SendRequestWithAuthRetry@@YAJPEAXPEB_W001K0KK0@Z`
- size: `1096`
- prototype: `int(void *, const wchar_t *, void *, void *, const wchar_t *, unsigned int, void *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801dba94`

## callees

- `0x180107fc4`
- `0x1801080ac`
- `0x1801081dc`
- `0x18011b538`
- `0x18012b618`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801082a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801085f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801082a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801085f7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180108247`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180108247`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801085ed`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801085ed`
- `WINHTTP!WinHttpSendRequest` at `0x180108409`
- `WINHTTP!WinHttpSendRequest` at `0x180108409`
- `WINHTTP!WinHttpReceiveResponse` at `0x18010843e`
- `WINHTTP!WinHttpReceiveResponse` at `0x18010843e`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18010851e`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18010851e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180108470`
- `WINHTTP!WinHttpQueryHeaders` at `0x180108470`
- `WINHTTP!WinHttpSetOption` at `0x18010830f`
- `WINHTTP!WinHttpSetOption` at `0x180108391`
- `WINHTTP!WinHttpSetOption` at `0x18010830f`
- `WINHTTP!WinHttpSetOption` at `0x180108391`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180108295`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180108295`

## string_xrefs

- `0x1801083ce`: `Sending request to %ws. ImpersonatedAsUser : %ws`
- `0x180108542`: `Will impersonate the next time. Status code was %d, AuthSchemes to use: 0x%lx`
- `0x180108563`: `Send succeeded. Impersonate flags: %lu`

## pseudocode

```c

```
