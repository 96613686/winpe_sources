# _dynamic_atexit_destructor_for__g_CSModules__

- ea: `0x180002630`
- end: `0x18000263e`
- name: `_dynamic_atexit_destructor_for__g_CSModules__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002637`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_CSModules__()
{
  DeleteCriticalSection(&g_CSModules);
}

```

## disassembly

```asm
0x180002630  lea     rcx, ?g_CSModules@@3VCCriticalSection@@A; CCriticalSection g_CSModules
0x180002637  jmp     cs:__imp_DeleteCriticalSection
```
