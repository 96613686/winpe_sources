# StopComTask$catch$4

- ea: `0x14000a8a0`
- end: `0x14000a8be`
- name: `StopComTask$catch$4`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StopComTask_catch_4()
{
  return 0;
}

```

## disassembly

```asm
0x14000a8a0  mov     [rsp+arg_8], rdx
0x14000a8a5  push    rbp
0x14000a8a6  sub     rsp, 30h
0x14000a8aa  mov     rbp, rdx
0x14000a8ad  mov     rax, 0
0x14000a8b7  add     rsp, 30h
0x14000a8bb  pop     rbp
0x14000a8bc  retn
```
