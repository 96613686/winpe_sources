# _ComTaskMgrBase::Initialize_::_1_::catch$5

- ea: `0x14000a59a`
- end: `0x14000a5bf`
- name: `_ComTaskMgrBase::Initialize_::_1_::catch$5`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize_::_1_::catch_5(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024809;
  return 0;
}

```

## disassembly

```asm
0x14000a59a  mov     [rsp+arg_8], rdx
0x14000a59f  push    rbp
0x14000a5a0  sub     rsp, 20h
0x14000a5a4  mov     rbp, rdx
0x14000a5a7  mov     dword ptr [rbp+48h], 80070057h
0x14000a5ae  mov     rax, 0
0x14000a5b8  add     rsp, 20h
0x14000a5bc  pop     rbp
0x14000a5bd  retn
```
