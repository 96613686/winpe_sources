# UninitializeComTasksLib$catch$2

- ea: `0x14000a6b0`
- end: `0x14000a6ce`
- name: `UninitializeComTasksLib$catch$2`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 UninitializeComTasksLib_catch_2()
{
  return 0;
}

```

## disassembly

```asm
0x14000a6b0  mov     [rsp+arg_8], rdx
0x14000a6b5  push    rbp
0x14000a6b6  sub     rsp, 20h
0x14000a6ba  mov     rbp, rdx
0x14000a6bd  mov     rax, 0
0x14000a6c7  add     rsp, 20h
0x14000a6cb  pop     rbp
0x14000a6cc  retn
```
