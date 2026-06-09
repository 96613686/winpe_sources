# __scrt_dllmain_before_initialize_c

- ea: `0x180005904`
- end: `0x18000590b`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005418`

## callees

- `0x180005a44`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180005904  xor     ecx, ecx
0x180005906  jmp     __scrt_initialize_onexit_tables
```
