# StartComTask$catch$1

- ea: `0x14000a980`
- end: `0x14000a99e`
- name: `StartComTask$catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StartComTask_catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x14000a980  mov     [rsp+arg_8], rdx
0x14000a985  push    rbp
0x14000a986  sub     rsp, 40h
0x14000a98a  mov     rbp, rdx
0x14000a98d  mov     rax, 0
0x14000a997  add     rsp, 40h
0x14000a99b  pop     rbp
0x14000a99c  retn
```
