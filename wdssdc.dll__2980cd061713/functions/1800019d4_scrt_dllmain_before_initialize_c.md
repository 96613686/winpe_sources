# __scrt_dllmain_before_initialize_c

- ea: `0x1800019d4`
- end: `0x1800019e9`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001278`

## callees

- `0x180001b38`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x1800019d4  sub     rsp, 28h
0x1800019d8  xor     ecx, ecx
0x1800019da  call    __scrt_initialize_onexit_tables
0x1800019df  test    al, al
0x1800019e1  setnz   al
0x1800019e4  add     rsp, 28h
0x1800019e8  retn
```
