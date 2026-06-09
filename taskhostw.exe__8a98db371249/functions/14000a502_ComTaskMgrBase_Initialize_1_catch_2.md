# _ComTaskMgrBase::Initialize_::_1_::catch$2

- ea: `0x14000a502`
- end: `0x14000a53e`
- name: `_ComTaskMgrBase::Initialize_::_1_::catch$2`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000a502`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize_::_1_::catch_2(__int64 a1, __int64 a2)
{
  signed int v3; // eax

  v3 = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 32))(*(_QWORD *)(a2 + 32));
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  *(_DWORD *)(a2 + 72) = v3;
  return 0;
}

```

## disassembly

```asm
0x14000a502  mov     [rsp+arg_8], rdx
0x14000a507  push    rbp
0x14000a508  sub     rsp, 20h
0x14000a50c  mov     rbp, rdx
0x14000a50f  mov     rcx, [rbp+20h]
0x14000a513  mov     rax, [rcx]
0x14000a516  mov     rax, [rax]
0x14000a519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a51e  test    eax, eax
0x14000a520  jle     short loc_14000A52A
0x14000a522  movzx   eax, ax
0x14000a525  or      eax, 80070000h
0x14000a52a  mov     [rbp+48h], eax
0x14000a52d  mov     rax, 0
0x14000a537  add     rsp, 20h
0x14000a53b  pop     rbp
0x14000a53c  retn
```
