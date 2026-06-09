# __scrt_dllmain_before_initialize_c

- ea: `0x100416da0`
- end: `0x100416db5`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100416618`

## callees

- `0x100416f14`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x100416da0  sub     rsp, 28h
0x100416da4  xor     ecx, ecx
0x100416da6  call    __scrt_initialize_onexit_tables
0x100416dab  test    al, al
0x100416dad  setnz   al
0x100416db0  add     rsp, 28h
0x100416db4  retn
```
