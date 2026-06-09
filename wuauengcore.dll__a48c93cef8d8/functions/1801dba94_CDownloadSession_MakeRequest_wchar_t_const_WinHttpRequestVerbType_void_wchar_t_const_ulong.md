# CDownloadSession::MakeRequest(wchar_t const *,WinHttpRequestVerbType,void *,wchar_t const *,ulong)

- ea: `0x1801dba94`
- end: `0x1801dbe29`
- name: `?MakeRequest@CDownloadSession@@AEAAJPEB_WW4WinHttpRequestVerbType@@PEAX0K@Z`
- size: `917`
- prototype: `int __high(const wchar_t *, enum WinHttpRequestVerbType, void *, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801daac0`
- `0x1801db654`

## callees

- `0x1801081dc`
- `0x18011b538`
- `0x18011d064`
- `0x18012b618`
- `0x1801dba94`
- `0x1801e99e0`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbb59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbbbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbbf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbcb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbb59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbbbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbbf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dbcb7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801dbb49`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801dbb49`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801dbbe3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801dbcad`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801dbbe3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801dbcad`
- `CRYPT32!CertFreeCertificateContext` at `0x1801dbd9d`
- `CRYPT32!CertFreeCertificateContext` at `0x1801dbd9d`
- `WINHTTP!WinHttpSetOption` at `0x1801dbbb2`
- `WINHTTP!WinHttpSetOption` at `0x1801dbc97`
- `WINHTTP!WinHttpSetOption` at `0x1801dbbb2`
- `WINHTTP!WinHttpSetOption` at `0x1801dbc97`
- `WINHTTP!WinHttpQueryOption` at `0x1801dbd65`
- `WINHTTP!WinHttpQueryOption` at `0x1801dbd65`
- `WINHTTP!WinHttpOpenRequest` at `0x1801dbc2e`
- `WINHTTP!WinHttpOpenRequest` at `0x1801dbc2e`

## pseudocode

```c

```
