# _ExecuteSecurityActionHandlerById_::_1_::dtor$5

- ea: `0x18000ae66`
- end: `0x18000ae72`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_5()
{
  Init_thread_abort(&dword_180014C38);
}

```

## disassembly

```asm
0x18000ae66  lea     rcx, dword_180014C38
0x18000ae6d  jmp     _Init_thread_abort
```
