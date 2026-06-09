# __scrt_dllmain_before_initialize_c

- ea: `0x180012920`
- end: `0x180012927`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012568`

## callees

- `0x180012a60`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180012920  xor     ecx, ecx
0x180012922  jmp     __scrt_initialize_onexit_tables
```
