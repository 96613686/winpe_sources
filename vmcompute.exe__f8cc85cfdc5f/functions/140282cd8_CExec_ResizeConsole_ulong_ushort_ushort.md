# CExec::ResizeConsole(ulong,ushort,ushort)

- ea: `0x140282cd8`
- end: `0x140282e1f`
- name: `?ResizeConsole@CExec@@YAXKGG@Z`
- size: `327`
- prototype: `void __fastcall(CExec *__hidden this, unsigned int, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400ce400`
- `0x1400ce900`

## callees

- `0x14001629c`
- `0x1400c40e0`
- `0x1400c4154`
- `0x1402827b0`
- `0x140282cd8`
- `0x14029f4dc`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x140282d66`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140282dad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140282d66`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140282dad`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140282d40`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140282d7d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140282d40`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140282d7d`
- `api-ms-win-core-console-l1-2-1!ResizePseudoConsole` at `0x140282df5`
- `api-ms-win-core-console-l1-2-1!ResizePseudoConsole` at `0x140282df5`

## string_xrefs

- `0x140282d1a`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140282e0d`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c

```
