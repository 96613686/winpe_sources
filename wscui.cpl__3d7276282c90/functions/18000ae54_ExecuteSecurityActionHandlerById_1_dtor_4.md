# _ExecuteSecurityActionHandlerById_::_1_::dtor$4

- ea: `0x18000ae54`
- end: `0x18000ae60`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_4()
{
  Init_thread_abort(&dword_180014C28);
}

```

## disassembly

```asm
0x18000ae54  lea     rcx, dword_180014C28
0x18000ae5b  jmp     _Init_thread_abort
```
