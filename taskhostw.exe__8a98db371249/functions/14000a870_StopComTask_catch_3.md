# StopComTask$catch$3

- ea: `0x14000a870`
- end: `0x14000a88e`
- name: `StopComTask$catch$3`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StopComTask_catch_3()
{
  return 0;
}

```

## disassembly

```asm
0x14000a870  mov     [rsp+arg_8], rdx
0x14000a875  push    rbp
0x14000a876  sub     rsp, 30h
0x14000a87a  mov     rbp, rdx
0x14000a87d  mov     rax, 0
0x14000a887  add     rsp, 30h
0x14000a88b  pop     rbp
0x14000a88c  retn
```
