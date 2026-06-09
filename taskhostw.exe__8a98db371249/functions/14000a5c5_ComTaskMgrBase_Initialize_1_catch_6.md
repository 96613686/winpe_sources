# _ComTaskMgrBase::Initialize_::_1_::catch$6

- ea: `0x14000a5c5`
- end: `0x14000a5ea`
- name: `_ComTaskMgrBase::Initialize_::_1_::catch$6`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize_::_1_::catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024809;
  return 0;
}

```

## disassembly

```asm
0x14000a5c5  mov     [rsp+arg_8], rdx
0x14000a5ca  push    rbp
0x14000a5cb  sub     rsp, 20h
0x14000a5cf  mov     rbp, rdx
0x14000a5d2  mov     dword ptr [rbp+48h], 80070057h
0x14000a5d9  mov     rax, 0
0x14000a5e3  add     rsp, 20h
0x14000a5e7  pop     rbp
0x14000a5e8  retn
```
