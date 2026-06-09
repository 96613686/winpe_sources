# _ExecuteSecurityActionHandlerById_::_1_::dtor$3

- ea: `0x18000ae42`
- end: `0x18000ae4e`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_3()
{
  Init_thread_abort(&dword_180014C18);
}

```

## disassembly

```asm
0x18000ae42  lea     rcx, dword_180014C18
0x18000ae49  jmp     _Init_thread_abort
```
