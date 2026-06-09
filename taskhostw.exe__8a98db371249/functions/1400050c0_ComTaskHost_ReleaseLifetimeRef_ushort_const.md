# ComTaskHost::ReleaseLifetimeRef(ushort const *)

- ea: `0x1400050c0`
- end: `0x14000513d`
- name: `?ReleaseLifetimeRef@ComTaskHost@@QEAAKPEBG@Z`
- size: `125`
- prototype: `__int64 __fastcall(ComTaskHost *this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004cf0`
- `0x140004ec0`
- `0x140007360`
- `0x140009910`

## callees

- `0x1400050c0`
- `0x140009b24`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ComTaskHost::ReleaseLifetimeRef(ComTaskHost *this, const unsigned __int16 *a2)
{
  __int64 v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (unsigned int)WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids,
      (_DWORD)this,
      (__int64)a2);
  v3 = _InterlockedExchange64((volatile __int64 *)this + 9, 0);
  if ( v3 )
    (*(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v3 + 16LL))(v3, a2);
  (*(void (__fastcall **)(ComTaskMgrWnd *, ComTaskHost *))(*(_QWORD *)ComTaskMgrBase::s_pVirtualSingleton + 24LL))(
    ComTaskMgrBase::s_pVirtualSingleton,
    this);
  return (*(__int64 (__fastcall **)(ComTaskHost *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x1400050c0  push    rbx
0x1400050c2  sub     rsp, 30h
0x1400050c6  mov     rbx, rcx
0x1400050c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050d0  lea     rax, WPP_GLOBAL_Control
0x1400050d7  cmp     rcx, rax
0x1400050da  jz      short loc_1400050E2
0x1400050dc  test    byte ptr [rcx+1Ch], 4
0x1400050e0  jnz     short loc_140005123
0x1400050e2  xor     ecx, ecx
0x1400050e4  xchg    rcx, [rbx+48h]
0x1400050e8  test    rcx, rcx
0x1400050eb  jz      short loc_1400050F9
0x1400050ed  mov     rax, [rcx]
0x1400050f0  mov     rax, [rax+10h]
0x1400050f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050f9  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140005100  mov     rdx, rbx
0x140005103  mov     rax, [rcx]
0x140005106  mov     rax, [rax+18h]
0x14000510a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000510f  mov     rax, [rbx]
0x140005112  mov     rcx, rbx
0x140005115  mov     rax, [rax+10h]
0x140005119  add     rsp, 30h
0x14000511d  pop     rbx
0x14000511e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140005123  mov     rcx, [rcx+10h]
0x140005127  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x14000512e  mov     r9, rbx
0x140005131  mov     [rsp+38h+var_18], rdx
0x140005136  call    WPP_SF_qS
0x14000513b  jmp     short loc_1400050E2
```
