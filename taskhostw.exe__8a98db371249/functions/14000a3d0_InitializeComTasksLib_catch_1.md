# InitializeComTasksLib$catch$1

- ea: `0x14000a3d0`
- end: `0x14000a3ee`
- name: `InitializeComTasksLib$catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 InitializeComTasksLib_catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x14000a3d0  mov     [rsp+arg_8], rdx
0x14000a3d5  push    rbp
0x14000a3d6  sub     rsp, 20h
0x14000a3da  mov     rbp, rdx
0x14000a3dd  mov     rax, 0
0x14000a3e7  add     rsp, 20h
0x14000a3eb  pop     rbp
0x14000a3ec  retn
```
