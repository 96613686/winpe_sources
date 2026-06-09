# StartComTask$catch$5

- ea: `0x14000aa40`
- end: `0x14000aa5e`
- name: `StartComTask$catch$5`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StartComTask_catch_5()
{
  return 0;
}

```

## disassembly

```asm
0x14000aa40  mov     [rsp+arg_8], rdx
0x14000aa45  push    rbp
0x14000aa46  sub     rsp, 40h
0x14000aa4a  mov     rbp, rdx
0x14000aa4d  mov     rax, 0
0x14000aa57  add     rsp, 40h
0x14000aa5b  pop     rbp
0x14000aa5c  retn
```
