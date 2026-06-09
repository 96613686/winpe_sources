# _ExecuteSecurityActionHandlerById_::_1_::dtor$11

- ea: `0x18000aed2`
- end: `0x18000aede`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_11()
{
  Init_thread_abort(&dword_180014C98);
}

```

## disassembly

```asm
0x18000aed2  lea     rcx, dword_180014C98
0x18000aed9  jmp     _Init_thread_abort
```
