# __scrt_dllmain_before_initialize_c

- ea: `0x18000fd80`
- end: `0x18000fd95`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800101d8`

## callees

- `0x18000fee4`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x18000fd80  sub     rsp, 28h
0x18000fd84  xor     ecx, ecx
0x18000fd86  call    __scrt_initialize_onexit_tables
0x18000fd8b  test    al, al
0x18000fd8d  setnz   al
0x18000fd90  add     rsp, 28h
0x18000fd94  retn
```
