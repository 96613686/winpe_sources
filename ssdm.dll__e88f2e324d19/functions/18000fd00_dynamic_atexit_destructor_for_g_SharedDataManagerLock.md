# _dynamic_atexit_destructor_for__g_SharedDataManagerLock__

- ea: `0x18000fd00`
- end: `0x18000fd0e`
- name: `_dynamic_atexit_destructor_for__g_SharedDataManagerLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd07`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_SharedDataManagerLock__()
{
  DeleteCriticalSection(&g_SharedDataManagerLock);
}

```

## disassembly

```asm
0x18000fd00  lea     rcx, ?g_SharedDataManagerLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection g_SharedDataManagerLock
0x18000fd07  jmp     cs:__imp_DeleteCriticalSection
```
