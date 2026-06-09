# HTTP_USER_REQUEST::OnRequestSent(ulong)

- ea: `0x18006cf00`
- end: `0x18006d203`
- name: `?OnRequestSent@HTTP_USER_REQUEST@@EEAAXK@Z`
- size: `771`
- prototype: `void __fastcall(HTTP_USER_REQUEST *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18006cf00`
- `0x1800a1d10`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cf4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cf4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cf76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cf76`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006d136`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006d136`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006d146`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006d146`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d0fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d0fb`
- `ntdll!EtwEventActivityIdControl` at `0x18006d014`
- `ntdll!EtwEventActivityIdControl` at `0x18006d04b`
- `ntdll!EtwEventActivityIdControl` at `0x18006d0ae`
- `ntdll!EtwEventActivityIdControl` at `0x18006d014`
- `ntdll!EtwEventActivityIdControl` at `0x18006d04b`
- `ntdll!EtwEventActivityIdControl` at `0x18006d0ae`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18006d1df`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18006d1df`

## pseudocode

```c

```
