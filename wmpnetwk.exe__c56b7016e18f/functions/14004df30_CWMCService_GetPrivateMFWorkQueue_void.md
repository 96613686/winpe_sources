# CWMCService::GetPrivateMFWorkQueue(void)

- ea: `0x14004df30`
- end: `0x14004dff3`
- name: `?GetPrivateMFWorkQueue@CWMCService@@QEAAKXZ`
- size: `195`
- prototype: `unsigned int __fastcall(CWMCService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14008fc18`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x14004df30`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14004df7a`
- `KERNEL32!EnterCriticalSection` at `0x14004df7a`
- `KERNEL32!LeaveCriticalSection` at `0x14004df9c`
- `KERNEL32!LeaveCriticalSection` at `0x14004df9c`
- `MFPlat!MFAllocateWorkQueueEx` at `0x14004df91`
- `MFPlat!MFAllocateWorkQueueEx` at `0x14004df91`

## pseudocode

```c

```
