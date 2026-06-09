# _ComTaskMgrBase::Initialize_::_1_::catch$7

- ea: `0x14000a5f0`
- end: `0x14000a615`
- name: `_ComTaskMgrBase::Initialize_::_1_::catch$7`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize_::_1_::catch_7(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x14000a5f0  mov     [rsp+arg_8], rdx
0x14000a5f5  push    rbp
0x14000a5f6  sub     rsp, 20h
0x14000a5fa  mov     rbp, rdx
0x14000a5fd  mov     dword ptr [rbp+48h], 80004005h
0x14000a604  mov     rax, 0
0x14000a60e  add     rsp, 20h
0x14000a612  pop     rbp
0x14000a613  retn
```
