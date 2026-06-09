# _dynamic_atexit_destructor_for__g_csThreadCount__

- ea: `0x180038010`
- end: `0x18003801e`
- name: `_dynamic_atexit_destructor_for__g_csThreadCount__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038017`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csThreadCount__()
{
  DeleteCriticalSection(&g_csThreadCount);
}

```

## disassembly

```asm
0x180038010  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; CUCriticalSection g_csThreadCount
0x180038017  jmp     cs:__imp_DeleteCriticalSection
```
