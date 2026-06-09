# __scrt_dllmain_before_initialize_c

- ea: `0x1800345b0`
- end: `0x1800345b7`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800341f8`

## callees

- `0x1800346f0`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800345b0  xor     ecx, ecx
0x1800345b2  jmp     __scrt_initialize_onexit_tables
```
