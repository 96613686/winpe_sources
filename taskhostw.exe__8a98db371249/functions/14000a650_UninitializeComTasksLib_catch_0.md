# UninitializeComTasksLib$catch$0

- ea: `0x14000a650`
- end: `0x14000a678`
- name: `UninitializeComTasksLib$catch$0`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall UninitializeComTasksLib_catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x14000a650  mov     [rsp+arg_8], rdx
0x14000a655  push    rbp
0x14000a656  sub     rsp, 20h
0x14000a65a  mov     rbp, rdx
0x14000a65d  mov     rax, [rbp+20h]
0x14000a661  mov     ecx, [rax+8]
0x14000a664  mov     [rbp+40h], ecx
0x14000a667  mov     rax, 0
0x14000a671  add     rsp, 20h
0x14000a675  pop     rbp
0x14000a676  retn
```
