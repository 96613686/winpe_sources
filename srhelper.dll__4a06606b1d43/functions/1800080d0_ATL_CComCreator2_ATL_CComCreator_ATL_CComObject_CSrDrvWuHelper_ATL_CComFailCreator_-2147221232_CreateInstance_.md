# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CSrDrvWuHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800080d0`
- end: `0x1800081b4`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCSrDrvWuHelper@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800012f8`
- `0x1800080d0`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CSrDrvWuHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
    *(_QWORD *)v6 = &ATL::CComObject<CSrDrvWuHelper>::`vftable';
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
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x1800080d0  push    rbx
0x1800080d2  push    rbp
0x1800080d3  push    rsi
0x1800080d4  push    rdi
0x1800080d5  sub     rsp, 28h
0x1800080d9  mov     rsi, r8
0x1800080dc  mov     rbp, rdx
0x1800080df  test    rcx, rcx
0x1800080e2  jnz     loc_180008191
0x1800080e8  test    r8, r8
0x1800080eb  jz      loc_180008196
0x1800080f1  mov     [r8], rcx
0x1800080f4  mov     ebx, 8007000Eh
0x1800080f9  mov     ecx, 20h ; ' '; Size
0x1800080fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008103  mov     rdi, rax
0x180008106  test    rax, rax
0x180008109  jz      loc_1800081A9
0x18000810f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008116  mov     dword ptr [rax+8], 0
0x18000811d  lea     rax, ??_7?$CComObject@VCSrDrvWuHelper@@@ATL@@6B@; const ATL::CComObject<CSrDrvWuHelper>::`vftable'
0x180008124  mov     [rdi], rax
0x180008127  mov     rax, [rcx]
0x18000812a  mov     rax, [rax+8]
0x18000812e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008133  lea     rdx, [rdi+8]
0x180008137  mov     r8d, 7FFFFFFFh
0x18000813d  jmp     short loc_180008148
0x18000813f  lea     ecx, [rax+1]
0x180008142  lock cmpxchg [rdx], ecx
0x180008146  jz      short loc_18000815A
0x180008148  mov     eax, [rdx]
0x18000814a  cmp     eax, r8d
0x18000814d  jnz     short loc_18000813F
0x18000814f  jmp     short loc_18000815A
0x180008151  lea     ecx, [rax-1]
0x180008154  lock cmpxchg [rdx], ecx
0x180008158  jz      short loc_180008161
0x18000815a  mov     eax, [rdx]
0x18000815c  cmp     eax, r8d
0x18000815f  jnz     short loc_180008151
0x180008161  mov     rax, [rdi]
0x180008164  mov     r8, rsi
0x180008167  mov     rdx, rbp
0x18000816a  mov     rcx, rdi
0x18000816d  mov     rax, [rax]
0x180008170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008175  mov     ebx, eax
0x180008177  test    eax, eax
0x180008179  jz      short loc_1800081A9
0x18000817b  mov     rdx, [rdi]
0x18000817e  mov     rcx, rdi
0x180008181  mov     rax, [rdx+38h]
0x180008185  mov     edx, 1
0x18000818a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000818f  jmp     short loc_1800081A9
0x180008191  test    rsi, rsi
0x180008194  jnz     short loc_18000819D
0x180008196  mov     ebx, 80004003h
0x18000819b  jmp     short loc_1800081A9
0x18000819d  mov     qword ptr [r8], 0
0x1800081a4  mov     ebx, 80040110h
0x1800081a9  mov     eax, ebx
0x1800081ab  add     rsp, 28h
0x1800081af  pop     rdi
0x1800081b0  pop     rsi
0x1800081b1  pop     rbp
0x1800081b2  pop     rbx
0x1800081b3  retn
```
