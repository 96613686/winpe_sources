# StartComTask$catch$2

- ea: `0x14000a9b0`
- end: `0x14000a9ce`
- name: `StartComTask$catch$2`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StartComTask_catch_2()
{
  return 0;
}

```

## disassembly

```asm
0x14000a9b0  mov     [rsp+arg_8], rdx
0x14000a9b5  push    rbp
0x14000a9b6  sub     rsp, 40h
0x14000a9ba  mov     rbp, rdx
0x14000a9bd  mov     rax, 0
0x14000a9c7  add     rsp, 40h
0x14000a9cb  pop     rbp
0x14000a9cc  retn
```
