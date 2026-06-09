# __scrt_dllmain_before_initialize_c

- ea: `0x1800103bc`
- end: `0x1800103d1`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010798`

## callees

- `0x180010520`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x1800103bc  sub     rsp, 28h
0x1800103c0  xor     ecx, ecx
0x1800103c2  call    __scrt_initialize_onexit_tables
0x1800103c7  test    al, al
0x1800103c9  setnz   al
0x1800103cc  add     rsp, 28h
0x1800103d0  retn
```
