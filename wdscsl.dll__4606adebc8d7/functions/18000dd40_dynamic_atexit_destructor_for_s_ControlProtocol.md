# _dynamic_atexit_destructor_for__s_ControlProtocol__

- ea: `0x18000dd40`
- end: `0x18000dd4e`
- name: `_dynamic_atexit_destructor_for__s_ControlProtocol__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000dd47`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_ControlProtocol__()
{
  DeleteCriticalSection(&stru_180015920);
}

```

## disassembly

```asm
0x18000dd40  lea     rcx, stru_180015920
0x18000dd47  jmp     cs:__imp_DeleteCriticalSection
```
