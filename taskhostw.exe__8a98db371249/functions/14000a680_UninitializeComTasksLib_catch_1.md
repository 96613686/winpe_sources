# UninitializeComTasksLib$catch$1

- ea: `0x14000a680`
- end: `0x14000a69e`
- name: `UninitializeComTasksLib$catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 UninitializeComTasksLib_catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x14000a680  mov     [rsp+arg_8], rdx
0x14000a685  push    rbp
0x14000a686  sub     rsp, 20h
0x14000a68a  mov     rbp, rdx
0x14000a68d  mov     rax, 0
0x14000a697  add     rsp, 20h
0x14000a69b  pop     rbp
0x14000a69c  retn
```
