# __scrt_initialize_default_local_stdio_options

- ea: `0x180002a88`
- end: `0x180002aa3`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002668`

## callees

- `0x1800025b4`
- `0x1800025c4`

## pseudocode

```c
unsigned __int64 *_scrt_initialize_default_local_stdio_options()
{
  unsigned __int64 *v0; // rax
  unsigned __int64 *result; // rax

  v0 = _local_stdio_printf_options();
  *v0 |= 0x24u;
  result = _local_stdio_scanf_options();
  *result |= 2u;
  return result;
}

```

## disassembly

```asm
0x180002a88  sub     rsp, 28h
0x180002a8c  call    __local_stdio_printf_options
0x180002a91  or      qword ptr [rax], 24h
0x180002a95  call    __local_stdio_scanf_options
0x180002a9a  or      qword ptr [rax], 2
0x180002a9e  add     rsp, 28h
0x180002aa2  retn
```
