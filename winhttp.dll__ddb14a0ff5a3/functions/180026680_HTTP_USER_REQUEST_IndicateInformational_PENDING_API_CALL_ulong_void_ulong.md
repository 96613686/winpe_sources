# HTTP_USER_REQUEST::_IndicateInformational(PENDING_API_CALL *,ulong,void *,ulong)

- ea: `0x180026680`
- end: `0x180026898`
- name: `?_IndicateInformational@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@KPEAXK@Z`
- size: `536`
- prototype: `void __fastcall(HTTP_USER_REQUEST *__hidden this, struct PENDING_API_CALL *, unsigned int, void *, unsigned int)`
- caller_count: `14`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180024d90`
- `0x180024eb0`
- `0x180024fd0`
- `0x180025d90`
- `0x180026e9c`
- `0x180027090`
- `0x180031490`
- `0x1800341fc`
- `0x180035500`
- `0x180035c4c`
- `0x180036058`
- `0x180037f80`
- `0x1800461a8`
- `0x1800b5510`

## callees

- `0x180026680`
- `0x1800a1d10`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002683e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002683e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026850`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026850`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026808`
- `ntdll!EtwEventActivityIdControl` at `0x180026736`
- `ntdll!EtwEventActivityIdControl` at `0x18002676b`
- `ntdll!EtwEventActivityIdControl` at `0x1800267cd`
- `ntdll!EtwEventActivityIdControl` at `0x180026736`
- `ntdll!EtwEventActivityIdControl` at `0x18002676b`
- `ntdll!EtwEventActivityIdControl` at `0x1800267cd`

## pseudocode

```c

```
