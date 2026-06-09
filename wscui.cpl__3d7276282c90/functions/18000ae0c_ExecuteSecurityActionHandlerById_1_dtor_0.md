# _ExecuteSecurityActionHandlerById_::_1_::dtor$0

- ea: `0x18000ae0c`
- end: `0x18000ae18`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_0()
{
  Init_thread_abort(&dword_180014BE8);
}

```

## disassembly

```asm
0x18000ae0c  lea     rcx, dword_180014BE8
0x18000ae13  jmp     _Init_thread_abort
```
