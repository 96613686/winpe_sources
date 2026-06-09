# StopComTask$catch$2

- ea: `0x14000a840`
- end: `0x14000a85e`
- name: `StopComTask$catch$2`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StopComTask_catch_2()
{
  return 0;
}

```

## disassembly

```asm
0x14000a840  mov     [rsp+arg_8], rdx
0x14000a845  push    rbp
0x14000a846  sub     rsp, 30h
0x14000a84a  mov     rbp, rdx
0x14000a84d  mov     rax, 0
0x14000a857  add     rsp, 30h
0x14000a85b  pop     rbp
0x14000a85c  retn
```
