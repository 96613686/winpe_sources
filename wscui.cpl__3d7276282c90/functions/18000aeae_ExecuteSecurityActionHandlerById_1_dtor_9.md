# _ExecuteSecurityActionHandlerById_::_1_::dtor$9

- ea: `0x18000aeae`
- end: `0x18000aeba`
- name: `_ExecuteSecurityActionHandlerById_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026c4`

## pseudocode

```c
void ExecuteSecurityActionHandlerById_::_1_::dtor_9()
{
  Init_thread_abort(&dword_180014C78);
}

```

## disassembly

```asm
0x18000aeae  lea     rcx, dword_180014C78
0x18000aeb5  jmp     _Init_thread_abort
```
