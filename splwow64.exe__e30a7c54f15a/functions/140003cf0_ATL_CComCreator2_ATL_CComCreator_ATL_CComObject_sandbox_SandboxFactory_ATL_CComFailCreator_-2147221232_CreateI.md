# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<sandbox::SandboxFactory>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140003cf0`
- end: `0x140003dd4`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VSandboxFactory@sandbox@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001b50`
- `0x140003cf0`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<sandbox::SandboxFactory>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  volatile signed __int32 *v9; // rdx
  signed __int32 v10; // eax
  signed __int32 v11; // eax

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (volatile signed __int32 *)operator new(0x20u);
  v7 = v6;
  if ( v6 )
  {
    v8 = ATL::_pAtlModule;
    *((_DWORD *)v6 + 2) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<sandbox::SandboxFactory>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    v9 = v7 + 2;
    do
    {
      if ( *v9 == 0x7FFFFFFF )
        break;
      v10 = *v9;
    }
    while ( v10 != _InterlockedCompareExchange(v9, v10 + 1, v10) );
    do
    {
      if ( *v9 == 0x7FFFFFFF )
        break;
      v11 = *v9;
    }
    while ( v11 != _InterlockedCompareExchange(v9, v11 - 1, v11) );
    v5 = (**(__int64 (__fastcall ***)(volatile signed __int32 *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v5 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x140003cf0  push    rbx
0x140003cf2  push    rbp
0x140003cf3  push    rsi
0x140003cf4  push    rdi
0x140003cf5  sub     rsp, 28h
0x140003cf9  mov     rsi, r8
0x140003cfc  mov     rbp, rdx
0x140003cff  test    rcx, rcx
0x140003d02  jnz     loc_140003DB1
0x140003d08  test    r8, r8
0x140003d0b  jz      loc_140003DB6
0x140003d11  mov     [r8], rcx
0x140003d14  mov     ebx, 8007000Eh
0x140003d19  mov     ecx, 20h ; ' '; Size
0x140003d1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003d23  mov     rdi, rax
0x140003d26  test    rax, rax
0x140003d29  jz      loc_140003DC9
0x140003d2f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003d36  mov     dword ptr [rax+8], 0
0x140003d3d  lea     rax, ??_7?$CComObject@VSandboxFactory@sandbox@@@ATL@@6B@; const ATL::CComObject<sandbox::SandboxFactory>::`vftable'
0x140003d44  mov     [rdi], rax
0x140003d47  mov     rax, [rcx]
0x140003d4a  mov     rax, [rax+8]
0x140003d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d53  lea     rdx, [rdi+8]
0x140003d57  mov     r8d, 7FFFFFFFh
0x140003d5d  jmp     short loc_140003D68
0x140003d5f  lea     ecx, [rax+1]
0x140003d62  lock cmpxchg [rdx], ecx
0x140003d66  jz      short loc_140003D7A
0x140003d68  mov     eax, [rdx]
0x140003d6a  cmp     eax, r8d
0x140003d6d  jnz     short loc_140003D5F
0x140003d6f  jmp     short loc_140003D7A
0x140003d71  lea     ecx, [rax-1]
0x140003d74  lock cmpxchg [rdx], ecx
0x140003d78  jz      short loc_140003D81
0x140003d7a  mov     eax, [rdx]
0x140003d7c  cmp     eax, r8d
0x140003d7f  jnz     short loc_140003D71
0x140003d81  mov     rax, [rdi]
0x140003d84  mov     r8, rsi
0x140003d87  mov     rdx, rbp
0x140003d8a  mov     rcx, rdi
0x140003d8d  mov     rax, [rax]
0x140003d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d95  mov     ebx, eax
0x140003d97  test    eax, eax
0x140003d99  jz      short loc_140003DC9
0x140003d9b  mov     rdx, [rdi]
0x140003d9e  mov     rcx, rdi
0x140003da1  mov     rax, [rdx+20h]
0x140003da5  mov     edx, 1
0x140003daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003daf  jmp     short loc_140003DC9
0x140003db1  test    rsi, rsi
0x140003db4  jnz     short loc_140003DBD
0x140003db6  mov     ebx, 80004003h
0x140003dbb  jmp     short loc_140003DC9
0x140003dbd  mov     qword ptr [r8], 0
0x140003dc4  mov     ebx, 80040110h
0x140003dc9  mov     eax, ebx
0x140003dcb  add     rsp, 28h
0x140003dcf  pop     rdi
0x140003dd0  pop     rsi
0x140003dd1  pop     rbp
0x140003dd2  pop     rbx
0x140003dd3  retn
```
