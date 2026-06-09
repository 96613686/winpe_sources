# _dynamic_atexit_destructor_for__g_csThreadCount__

- ea: `0x1800354f0`
- end: `0x1800354fe`
- name: `_dynamic_atexit_destructor_for__g_csThreadCount__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800354f7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csThreadCount__()
{
  DeleteCriticalSection(&g_csThreadCount);
}

```

## disassembly

```asm
0x1800354f0  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; CUCriticalSection g_csThreadCount
0x1800354f7  jmp     cs:__imp_DeleteCriticalSection
```
