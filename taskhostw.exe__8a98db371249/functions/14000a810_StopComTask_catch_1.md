# StopComTask$catch$1

- ea: `0x14000a810`
- end: `0x14000a82e`
- name: `StopComTask$catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StopComTask_catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x14000a810  mov     [rsp+arg_8], rdx
0x14000a815  push    rbp
0x14000a816  sub     rsp, 30h
0x14000a81a  mov     rbp, rdx
0x14000a81d  mov     rax, 0
0x14000a827  add     rsp, 30h
0x14000a82b  pop     rbp
0x14000a82c  retn
```
