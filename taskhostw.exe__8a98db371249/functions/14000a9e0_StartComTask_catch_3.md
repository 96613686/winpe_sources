# StartComTask$catch$3

- ea: `0x14000a9e0`
- end: `0x14000a9fe`
- name: `StartComTask$catch$3`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 StartComTask_catch_3()
{
  return 0;
}

```

## disassembly

```asm
0x14000a9e0  mov     [rsp+arg_8], rdx
0x14000a9e5  push    rbp
0x14000a9e6  sub     rsp, 40h
0x14000a9ea  mov     rbp, rdx
0x14000a9ed  mov     rax, 0
0x14000a9f7  add     rsp, 40h
0x14000a9fb  pop     rbp
0x14000a9fc  retn
```
