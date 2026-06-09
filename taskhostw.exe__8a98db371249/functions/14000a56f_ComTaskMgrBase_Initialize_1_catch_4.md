# _ComTaskMgrBase::Initialize_::_1_::catch$4

- ea: `0x14000a56f`
- end: `0x14000a594`
- name: `_ComTaskMgrBase::Initialize_::_1_::catch$4`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize_::_1_::catch_4(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024809;
  return 0;
}

```

## disassembly

```asm
0x14000a56f  mov     [rsp+arg_8], rdx
0x14000a574  push    rbp
0x14000a575  sub     rsp, 20h
0x14000a579  mov     rbp, rdx
0x14000a57c  mov     dword ptr [rbp+48h], 80070057h
0x14000a583  mov     rax, 0
0x14000a58d  add     rsp, 20h
0x14000a591  pop     rbp
0x14000a592  retn
```
