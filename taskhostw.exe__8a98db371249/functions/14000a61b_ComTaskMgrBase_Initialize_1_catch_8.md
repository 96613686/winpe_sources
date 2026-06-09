# _ComTaskMgrBase::Initialize_::_1_::catch$8

- ea: `0x14000a61b`
- end: `0x14000a643`
- name: `_ComTaskMgrBase::Initialize_::_1_::catch$8`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize_::_1_::catch_8(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x14000a61b  mov     [rsp+arg_8], rdx
0x14000a620  push    rbp
0x14000a621  sub     rsp, 20h
0x14000a625  mov     rbp, rdx
0x14000a628  mov     rax, [rbp+28h]
0x14000a62c  mov     ecx, [rax+8]
0x14000a62f  mov     [rbp+48h], ecx
0x14000a632  mov     rax, 0
0x14000a63c  add     rsp, 20h
0x14000a640  pop     rbp
0x14000a641  retn
```
