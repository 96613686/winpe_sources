# initialize_msvcrt_compatibility

- ea: `0x180002060`
- end: `0x18000207d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002034`
- `0x180002044`

## pseudocode

```c
__int64 initialize_msvcrt_compatibility()
{
  unsigned __int64 *v0; // rax
  unsigned __int64 *v1; // rax

  v0 = _local_stdio_printf_options();
  *v0 |= 0x18u;
  v1 = _local_stdio_scanf_options();
  *v1 |= 4u;
  return 0;
}

```

## disassembly

```asm
0x180002060  sub     rsp, 28h
0x180002064  call    __local_stdio_printf_options
0x180002069  or      qword ptr [rax], 18h
0x18000206d  call    __local_stdio_scanf_options
0x180002072  or      qword ptr [rax], 4
0x180002076  xor     eax, eax
0x180002078  add     rsp, 28h
0x18000207c  retn
```
