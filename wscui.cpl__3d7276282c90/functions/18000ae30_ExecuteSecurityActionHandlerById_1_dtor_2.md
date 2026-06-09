# _ExecuteSecurityActionHandlerById_::_1_::dtor$2

- ea: `0x18000ae30`
- end: `0x18000ae3c`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_2()
{
  Init_thread_abort(&dword_180014C08);
}

```

## disassembly

```asm
0x18000ae30  lea     rcx, dword_180014C08
0x18000ae37  jmp     _Init_thread_abort
```
