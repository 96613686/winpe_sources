# _ExecuteSecurityActionHandlerById_::_1_::dtor$1

- ea: `0x18000ae1e`
- end: `0x18000ae2a`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_1()
{
  Init_thread_abort(&dword_180014BF8);
}

```

## disassembly

```asm
0x18000ae1e  lea     rcx, dword_180014BF8
0x18000ae25  jmp     _Init_thread_abort
```
