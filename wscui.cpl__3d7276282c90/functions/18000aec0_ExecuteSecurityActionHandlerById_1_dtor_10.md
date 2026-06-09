# _ExecuteSecurityActionHandlerById_::_1_::dtor$10

- ea: `0x18000aec0`
- end: `0x18000aecc`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_10()
{
  Init_thread_abort(&dword_180014C88);
}

```

## disassembly

```asm
0x18000aec0  lea     rcx, dword_180014C88
0x18000aec7  jmp     _Init_thread_abort
```
