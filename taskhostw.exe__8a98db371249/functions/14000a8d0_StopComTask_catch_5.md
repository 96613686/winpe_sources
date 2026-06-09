# StopComTask$catch$5

- ea: `0x14000a8d0`
- end: `0x14000a8ee`
- name: `StopComTask$catch$5`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StopComTask_catch_5()
{
  return 0;
}

```

## disassembly

```asm
0x14000a8d0  mov     [rsp+arg_8], rdx
0x14000a8d5  push    rbp
0x14000a8d6  sub     rsp, 30h
0x14000a8da  mov     rbp, rdx
0x14000a8dd  mov     rax, 0
0x14000a8e7  add     rsp, 30h
0x14000a8eb  pop     rbp
0x14000a8ec  retn
```
