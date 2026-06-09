# CWxSocket::Abort(ulong,int)

- ea: `0x1800f2584`
- end: `0x1800f26d9`
- name: `?Abort@CWxSocket@@QEAAXKH@Z`
- size: `341`
- prototype: `void __fastcall(CWxSocket *__hidden this, unsigned int, int)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180050c40`
- `0x180088e30`
- `0x1800f2120`
- `0x1800f23a0`
- `0x180106e40`
- `0x1801647b0`
- `0x1801a2e80`
- `0x1801b6640`

## callees

- `0x1800548ec`
- `0x1800f2584`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e4988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f25e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f25e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f25b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f25b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800f2651`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800f2651`
- `ntdll!NtSetInformationObject` at `0x1800f2626`
- `ntdll!NtSetInformationObject` at `0x1800f2626`
- `WS2_32!__imp_closesocket` at `0x1800f2643`
- `WS2_32!__imp_closesocket` at `0x1800f2643`
- `WS2_32!__imp_shutdown` at `0x1800f2687`
- `WS2_32!__imp_shutdown` at `0x1800f2687`

## pseudocode

```c

```
