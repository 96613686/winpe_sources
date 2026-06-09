# CDownloadSession::Connect(void)

- ea: `0x1801db404`
- end: `0x1801db64b`
- name: `?Connect@CDownloadSession@@AEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CDownloadSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801dae98`

## callees

- `0x180113ae8`
- `0x18011cd24`
- `0x18012b618`
- `0x1801db404`
- `0x1801dc4d8`
- `0x1801dc5bc`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db61b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db61b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801db442`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801db442`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801db611`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801db611`
- `WINHTTP!WinHttpCloseHandle` at `0x1801db5b3`
- `WINHTTP!WinHttpCloseHandle` at `0x1801db5d1`
- `WINHTTP!WinHttpCloseHandle` at `0x1801db5b3`
- `WINHTTP!WinHttpCloseHandle` at `0x1801db5d1`
- `WINHTTP!WinHttpSetOption` at `0x1801db4ee`
- `WINHTTP!WinHttpSetOption` at `0x1801db4ee`
- `WINHTTP!WinHttpOpen` at `0x1801db4ae`
- `WINHTTP!WinHttpOpen` at `0x1801db4ae`
- `WINHTTP!WinHttpSetTimeouts` at `0x1801db562`
- `WINHTTP!WinHttpSetTimeouts` at `0x1801db562`
- `WINHTTP!WinHttpConnect` at `0x1801db581`
- `WINHTTP!WinHttpConnect` at `0x1801db581`

## string_xrefs

- `0x1801db47c`: `Windows-Update-Agent/1507.2603.28012.0 Client-Protocol/2.90`

## pseudocode

```c

```
