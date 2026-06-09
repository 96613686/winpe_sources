# __scrt_dllmain_before_initialize_c

- ea: `0x18000fd30`
- end: `0x18000fd45`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010188`

## callees

- `0x18000fe94`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x18000fd30  sub     rsp, 28h
0x18000fd34  xor     ecx, ecx
0x18000fd36  call    __scrt_initialize_onexit_tables
0x18000fd3b  test    al, al
0x18000fd3d  setnz   al
0x18000fd40  add     rsp, 28h
0x18000fd44  retn
```
