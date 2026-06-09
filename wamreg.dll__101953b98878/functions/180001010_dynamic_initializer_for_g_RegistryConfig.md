# _dynamic_initializer_for__g_RegistryConfig__

- ea: `0x180001010`
- end: `0x18000101c`
- name: `_dynamic_initializer_for__g_RegistryConfig__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017e4`

## pseudocode

```c
int dynamic_initializer_for__g_RegistryConfig__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_RegistryConfig__);
}

```

## disassembly

```asm
0x180001010  lea     rcx, _dynamic_atexit_destructor_for__g_RegistryConfig__
0x180001017  jmp     atexit
```
