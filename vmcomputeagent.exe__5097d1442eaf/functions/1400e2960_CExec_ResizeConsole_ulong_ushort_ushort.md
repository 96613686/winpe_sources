# CExec::ResizeConsole(ulong,ushort,ushort)

- ea: `0x1400e2960`
- end: `0x1400e2ab1`
- name: `?ResizeConsole@CExec@@YAXKGG@Z`
- size: `337`
- prototype: `void __fastcall(CExec *__hidden this, unsigned int, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400ab2f0`

## callees

- `0x14000ea60`
- `0x1400341ac`
- `0x1400e1b18`
- `0x1400e2960`
- `0x1400e9f18`
- `0x1400fe010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e29a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e29da`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e29a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e29da`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e29c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e2a04`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e29c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e2a04`
- `api-ms-win-core-console-l1-2-1!ResizePseudoConsole` at `0x1400e2a6e`
- `api-ms-win-core-console-l1-2-1!ResizePseudoConsole` at `0x1400e2a6e`

## string_xrefs

- `0x1400e2a8a`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e2a9f`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c

```
