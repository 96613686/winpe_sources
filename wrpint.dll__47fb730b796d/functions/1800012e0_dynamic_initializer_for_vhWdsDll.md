# _dynamic_initializer_for__vhWdsDll__

- ea: `0x1800012e0`
- end: `0x1800012ec`
- name: `_dynamic_initializer_for__vhWdsDll__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800018b8`

## pseudocode

```c
int dynamic_initializer_for__vhWdsDll__()
{
  return atexit(dynamic_atexit_destructor_for__vhWdsDll__);
}

```

## disassembly

```asm
0x1800012e0  lea     rcx, _dynamic_atexit_destructor_for__vhWdsDll__
0x1800012e7  jmp     atexit
```
