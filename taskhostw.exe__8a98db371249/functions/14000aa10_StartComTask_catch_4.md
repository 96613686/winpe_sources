# StartComTask$catch$4

- ea: `0x14000aa10`
- end: `0x14000aa2e`
- name: `StartComTask$catch$4`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StartComTask_catch_4()
{
  return 0;
}

```

## disassembly

```asm
0x14000aa10  mov     [rsp+arg_8], rdx
0x14000aa15  push    rbp
0x14000aa16  sub     rsp, 40h
0x14000aa1a  mov     rbp, rdx
0x14000aa1d  mov     rax, 0
0x14000aa27  add     rsp, 40h
0x14000aa2b  pop     rbp
0x14000aa2c  retn
```
