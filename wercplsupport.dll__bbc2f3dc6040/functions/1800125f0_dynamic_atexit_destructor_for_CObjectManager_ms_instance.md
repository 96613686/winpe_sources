# _dynamic_atexit_destructor_for__CObjectManager::ms_instance__

- ea: `0x1800125f0`
- end: `0x1800125fe`
- name: `_dynamic_atexit_destructor_for__CObjectManager::ms_instance__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800125f7`

## pseudocode

```c
void dynamic_atexit_destructor_for__CObjectManager::ms_instance__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x1800125f0  lea     rcx, CriticalSection
0x1800125f7  jmp     cs:__imp_DeleteCriticalSection
```
