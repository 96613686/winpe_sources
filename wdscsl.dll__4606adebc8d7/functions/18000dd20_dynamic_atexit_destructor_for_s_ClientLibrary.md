# _dynamic_atexit_destructor_for__s_ClientLibrary__

- ea: `0x18000dd20`
- end: `0x18000dd2e`
- name: `_dynamic_atexit_destructor_for__s_ClientLibrary__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000dd27`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_ClientLibrary__()
{
  DeleteCriticalSection(&stru_1800158D0);
}

```

## disassembly

```asm
0x18000dd20  lea     rcx, stru_1800158D0
0x18000dd27  jmp     cs:__imp_DeleteCriticalSection
```
