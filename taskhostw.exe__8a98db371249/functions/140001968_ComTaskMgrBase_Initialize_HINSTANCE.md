# ComTaskMgrBase::Initialize(HINSTANCE__ *)

- ea: `0x140001968`
- end: `0x140001a65`
- name: `?Initialize@ComTaskMgrBase@@SAJPEAUHINSTANCE__@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001860`

## callees

- `0x140001968`
- `0x1400022d0`
- `0x140006b50`
- `0x140006fcc`
- `0x140007f24`
- `0x140008fb0`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::Initialize(HINSTANCE a1)
{
  int inited; // ebx
  bool v2; // al
  ComTaskMgrWnd *v3; // rax
  __int64; // rax
  signed int v5; // eax
  wmi::Exception *v6; // [rsp+20h] [rbp-18h] BYREF
  _com_error *v7; // [rsp+28h] [rbp-10h] BYREF
  ComTaskMgrWnd *v9; // [rsp+50h] [rbp+18h]

  inited = ComTaskMgrBase::InitComSecurity();
  if ( inited < 0 )
    goto LABEL_17;
  inited = ShutdownMgr::Initialize();
  if ( inited < 0 )
    goto LABEL_17;
  v2 = !NtCurrentPeb()->SessionId || !IsCreateWindowExWPresent();
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( v2 )
    {
      v3 = (ComTaskMgrWnd *)operator new(8u);
      if ( v3 )
        *(_QWORD *)v3 = &ComTaskMgrBase::`vftable';
    }
    else
    {
      v3 = (ComTaskMgrWnd *)operator new(0x60u);
      if ( v3 )
        v3 = ComTaskMgrWnd::ComTaskMgrWnd(v3);
    }
    v9 = v3;
    if ( !v3 )
      inited = -2147024882;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', &v6) )
    {
      v5 = (**(__int64 (__fastcall ***)(wmi::Exception *))v6)(v6);
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      inited = v5;
      __eh34_try_continuation(0, &wmi::Exception `RTTI Type Descriptor', &loc_140001A0B);
      goto LABEL_18;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      inited = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140001A0D);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &std::invalid_argument `RTTI Type Descriptor', 0) )
    {
      inited = -2147024809;
      __eh34_try_continuation(0, &std::invalid_argument `RTTI Type Descriptor', &loc_140001A34);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &std::length_error `RTTI Type Descriptor', 0) )
    {
      inited = -2147024809;
      __eh34_try_continuation(0, &std::length_error `RTTI Type Descriptor', &loc_140001A36);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &std::out_of_range `RTTI Type Descriptor', 0) )
    {
      inited = -2147024809;
      __eh34_try_continuation(0, &std::out_of_range `RTTI Type Descriptor', &loc_140001A38);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      inited = -2147467259;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_140001A3A);
LABEL_15:
      if ( v9 )
        (*(void (__fastcall **)(ComTaskMgrWnd *, __int64))(*(_QWORD *)v9 + 32LL))(v9, 1);
LABEL_17:
       = (unsigned int)inited;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v7) )
    {
      inited = *((_DWORD *)v7 + 2);
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_140001A3C);
    }
  }
LABEL_18:
  if ( inited >= 0 )
  {
    ComTaskMgrBase::s_pVirtualSingleton = v9;
    inited = (*(__int64 (__fastcall **)(ComTaskMgrWnd *, HINSTANCE))(*(_QWORD *)v9 + 40LL))(v9, a1);
    goto LABEL_17;
  }
  goto LABEL_15;
}

```

## disassembly

```asm
0x140001968  mov     [rsp+arg_0], rcx
0x14000196d  push    rbx
0x14000196e  sub     rsp, 30h
0x140001972  call    ?InitComSecurity@ComTaskMgrBase@@CAJXZ; ComTaskMgrBase::InitComSecurity(void)
0x140001977  mov     ebx, eax
0x140001979  test    eax, eax
0x14000197b  js      loc_140001A2C
0x140001981  call    ?Initialize@ShutdownMgr@@SAJXZ; ShutdownMgr::Initialize(void)
0x140001986  mov     ebx, eax
0x140001988  test    eax, eax
0x14000198a  js      loc_140001A2C
0x140001990  mov     [rsp+38h+arg_10], 0
0x140001999  mov     rax, gs:60h
0x1400019a2  cmp     dword ptr [rax+2C0h], 0
0x1400019a9  jz      short loc_1400019B8
0x1400019ab  call    IsCreateWindowExWPresent
0x1400019b0  test    al, al
0x1400019b2  jz      short loc_1400019B8
0x1400019b4  xor     al, al
0x1400019b6  jmp     short loc_1400019BA
0x1400019b8  mov     al, 1
0x1400019ba  test    al, al
0x1400019bc  jz      short loc_1400019D9
0x1400019be  mov     ecx, 8; Size
0x1400019c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400019c8  test    rax, rax
0x1400019cb  jz      short loc_1400019F6
0x1400019cd  lea     rcx, ??_7ComTaskMgrBase@@6B@; const ComTaskMgrBase::`vftable'
0x1400019d4  mov     [rax], rcx
0x1400019d7  jmp     short loc_1400019F6
0x1400019d9  mov     ecx, 60h ; '`'; Size
0x1400019de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400019e3  mov     [rsp+38h+arg_8], rax
0x1400019e8  test    rax, rax
0x1400019eb  jz      short loc_1400019F6
0x1400019ed  mov     rcx, rax; this
0x1400019f0  call    ??0ComTaskMgrWnd@@QEAA@XZ; ComTaskMgrWnd::ComTaskMgrWnd(void)
0x1400019f5  nop
0x1400019f6  mov     [rsp+38h+arg_10], rax
0x1400019fb  mov     eax, 8007000Eh
0x140001a00  cmp     [rsp+38h+arg_10], 0
0x140001a06  cmovz   ebx, eax
0x140001a09  jmp     short loc_140001A40
0x140001a0b  jmp     short loc_140001A3C
0x140001a0d  mov     ebx, dword ptr [rsp+38h+arg_8]
0x140001a11  mov     rcx, [rsp+38h+arg_10]
0x140001a16  test    rcx, rcx
0x140001a19  jz      short loc_140001A2C
0x140001a1b  mov     rax, [rcx]
0x140001a1e  mov     edx, 1
0x140001a23  mov     rax, [rax+20h]
0x140001a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a2c  mov     eax, ebx
0x140001a2e  add     rsp, 30h
0x140001a32  pop     rbx
0x140001a33  retn
0x140001a34  jmp     short loc_140001A0D
0x140001a36  jmp     short loc_140001A0D
0x140001a38  jmp     short loc_140001A0D
0x140001a3a  jmp     short loc_140001A0D
0x140001a3c  mov     ebx, dword ptr [rsp+38h+arg_8]
0x140001a40  test    ebx, ebx
0x140001a42  js      short loc_140001A11
0x140001a44  mov     rcx, [rsp+38h+arg_10]
0x140001a49  mov     cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA, rcx; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140001a50  mov     rax, [rcx]
0x140001a53  mov     rdx, [rsp+38h+arg_0]
0x140001a58  mov     rax, [rax+28h]
0x140001a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a61  mov     ebx, eax
0x140001a63  jmp     short loc_140001A2C
```
