# InitializeComTasksLib$catch$2

- ea: `0x14000a400`
- end: `0x14000a41e`
- name: `InitializeComTasksLib$catch$2`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 InitializeComTasksLib_catch_2()
{
  return 0;
}

```

## disassembly

```asm
0x14000a400  mov     [rsp+arg_8], rdx
0x14000a405  push    rbp
0x14000a406  sub     rsp, 20h
0x14000a40a  mov     rbp, rdx
0x14000a40d  mov     rax, 0
0x14000a417  add     rsp, 20h
0x14000a41b  pop     rbp
0x14000a41c  retn
```
