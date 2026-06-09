# _ExecuteSecurityActionHandlerById_::_1_::dtor$6

- ea: `0x18000ae78`
- end: `0x18000ae84`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_6()
{
  Init_thread_abort(&dword_180014C48);
}

```

## disassembly

```asm
0x18000ae78  lea     rcx, dword_180014C48
0x18000ae7f  jmp     _Init_thread_abort
```
