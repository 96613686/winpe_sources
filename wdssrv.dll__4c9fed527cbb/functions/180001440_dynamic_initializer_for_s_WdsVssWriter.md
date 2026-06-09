# _dynamic_initializer_for__s_WdsVssWriter__

- ea: `0x180001440`
- end: `0x18000144c`
- name: `_dynamic_initializer_for__s_WdsVssWriter__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001a28`

## pseudocode

```c
int dynamic_initializer_for__s_WdsVssWriter__()
{
  return atexit(dynamic_atexit_destructor_for__s_WdsVssWriter__);
}

```

## disassembly

```asm
0x180001440  lea     rcx, _dynamic_atexit_destructor_for__s_WdsVssWriter__
0x180001447  jmp     atexit
```
