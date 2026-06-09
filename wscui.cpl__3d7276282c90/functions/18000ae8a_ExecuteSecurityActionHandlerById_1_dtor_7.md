# _ExecuteSecurityActionHandlerById_::_1_::dtor$7

- ea: `0x18000ae8a`
- end: `0x18000ae96`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_7()
{
  Init_thread_abort(&dword_180014C58);
}

```

## disassembly

```asm
0x18000ae8a  lea     rcx, dword_180014C58
0x18000ae91  jmp     _Init_thread_abort
```
