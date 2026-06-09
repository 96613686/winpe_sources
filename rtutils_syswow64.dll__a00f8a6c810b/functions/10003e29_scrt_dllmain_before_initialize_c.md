# ___scrt_dllmain_before_initialize_c

- ea: `0x10003e29`
- end: `0x10003e32`
- name: `___scrt_dllmain_before_initialize_c`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100038db`

## callees

- `0x10003f29`

## pseudocode

```c
int __scrt_dllmain_before_initialize_c()
{
  return __scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x10003e29  push    0
0x10003e2b  call    ___scrt_initialize_onexit_tables
0x10003e30  pop     ecx
0x10003e31  retn
```
