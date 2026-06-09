# __scrt_dllmain_before_initialize_c

- ea: `0x1800053c0`
- end: `0x1800053c7`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005008`

## callees

- `0x180005500`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800053c0  xor     ecx, ecx
0x1800053c2  jmp     __scrt_initialize_onexit_tables
```
