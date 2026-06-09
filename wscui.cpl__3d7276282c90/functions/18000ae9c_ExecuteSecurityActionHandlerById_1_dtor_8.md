# _ExecuteSecurityActionHandlerById_::_1_::dtor$8

- ea: `0x18000ae9c`
- end: `0x18000aea8`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_8()
{
  Init_thread_abort(&dword_180014C68);
}

```

## disassembly

```asm
0x18000ae9c  lea     rcx, dword_180014C68
0x18000aea3  jmp     _Init_thread_abort
```
