# CHttpRequest::CloseConnection(void)

- ea: `0x180016134`
- end: `0x180016207`
- name: `?CloseConnection@CHttpRequest@@IEAAXXZ`
- size: `211`
- prototype: `void __fastcall(CHttpRequest *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003e1ec`
- `0x18009edfc`
- `0x18009fa94`

## callees

- `0x180016134`
- `0x180016838`
- `0x180040674`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161ea`
- `WINHTTP!WinHttpCloseHandle` at `0x18001618a`
- `WINHTTP!WinHttpCloseHandle` at `0x1800161ab`
- `WINHTTP!WinHttpCloseHandle` at `0x18001618a`
- `WINHTTP!WinHttpCloseHandle` at `0x1800161ab`

## string_xrefs

- `0x1800161ce`: `CHttpRequest Waiting for WinHttp to complete`

## pseudocode

```c

```
