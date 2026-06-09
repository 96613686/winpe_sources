# _ComTaskMgrBase::Initialize_::_1_::catch$3

- ea: `0x14000a544`
- end: `0x14000a569`
- name: `_ComTaskMgrBase::Initialize_::_1_::catch$3`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14000a544  mov     [rsp+arg_8], rdx
0x14000a549  push    rbp
0x14000a54a  sub     rsp, 20h
0x14000a54e  mov     rbp, rdx
0x14000a551  mov     dword ptr [rbp+48h], 8007000Eh
0x14000a558  mov     rax, 0
0x14000a562  add     rsp, 20h
0x14000a566  pop     rbp
0x14000a567  retn
```
