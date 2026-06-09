# StopComTask$catch$6

- ea: `0x14000a900`
- end: `0x14000a928`
- name: `StopComTask$catch$6`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall StopComTask_catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 88) = *(_DWORD *)(*(_QWORD *)(a2 + 56) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x14000a900  mov     [rsp+arg_8], rdx
0x14000a905  push    rbp
0x14000a906  sub     rsp, 30h
0x14000a90a  mov     rbp, rdx
0x14000a90d  mov     rax, [rbp+38h]
0x14000a911  mov     ecx, [rax+8]
0x14000a914  mov     [rbp+58h], ecx
0x14000a917  mov     rax, 0
0x14000a921  add     rsp, 30h
0x14000a925  pop     rbp
0x14000a926  retn
```
