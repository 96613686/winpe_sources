# ATL::CComCreator<ATL::CComObject<CWinInetHelperClass>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000448c`
- end: `0x18000459d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinInetHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004460`

## callees

- `0x1800012e4`
- `0x180002940`
- `0x18000448c`
- `0x180008180`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CWinInetHelperClass>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  CWinInetHelperClass *v7; // rax
  CWinInetHelperClass *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  volatile signed __int32 *v10; // rdi
  signed __int32 v11; // eax
  int v12; // eax
  int v13; // ecx
  signed __int32 v14; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CWinInetHelperClass *)operator new(0x1408u);
  v8 = v7;
  if ( v7 )
  {
    CWinInetHelperClass::CWinInetHelperClass(v7);
    v9 = ATL::_pAtlModule;
    *(_QWORD *)v8 = &ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelper'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelperInfo'};
    *((_QWORD *)v8 + 7) = &ATL::CComObject<CWinInetHelperClass>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = (volatile signed __int32 *)((char *)v8 + 64);
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v11 = *v10;
    }
    while ( v11 != _InterlockedCompareExchange(v10, v11 + 1, v11) );
    v12 = ATL::CComCriticalSection::Init((CWinInetHelperClass *)((char *)v8 + 72));
    if ( v12 >= 0 )
      *((_BYTE *)v8 + 112) = 1;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v6 = 0;
    if ( v13 < 0 )
      v6 = v13;
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v14 = *v10;
    }
    while ( v14 != _InterlockedCompareExchange(v10, v14 - 1, v14) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CWinInetHelperClass *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CWinInetHelperClass *, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000448c  push    rbx
0x18000448e  push    rbp
0x18000448f  push    rsi
0x180004490  push    rdi
0x180004491  push    r14
0x180004493  push    r15
0x180004495  sub     rsp, 28h
0x180004499  mov     r14, r8
0x18000449c  mov     rbp, rdx
0x18000449f  test    r8, r8
0x1800044a2  jnz     short loc_1800044AE
0x1800044a4  mov     eax, 80004003h
0x1800044a9  jmp     loc_18000458F
0x1800044ae  mov     ecx, 1408h; Size
0x1800044b3  mov     qword ptr [r8], 0
0x1800044ba  mov     esi, 8007000Eh
0x1800044bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044c4  mov     rbx, rax
0x1800044c7  test    rax, rax
0x1800044ca  jz      loc_18000458D
0x1800044d0  mov     rcx, rax; this
0x1800044d3  call    ??0CWinInetHelperClass@@QEAA@XZ; CWinInetHelperClass::CWinInetHelperClass(void)
0x1800044d8  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800044df  lea     rax, ??_7?$CComObject@VCWinInetHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelper'}
0x1800044e6  mov     [rbx], rax
0x1800044e9  lea     rax, ??_7?$CComObject@VCWinInetHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x1800044f0  mov     [rbx+8], rax
0x1800044f4  lea     rax, ??_7?$CComObject@VCWinInetHelperClass@@@ATL@@6B@; const ATL::CComObject<CWinInetHelperClass>::`vftable'
0x1800044fb  mov     [rbx+38h], rax
0x1800044ff  mov     rax, [rcx]
0x180004502  mov     rax, [rax+8]
0x180004506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000450b  lea     rdi, [rbx+40h]
0x18000450f  mov     r15d, 7FFFFFFFh
0x180004515  jmp     short loc_180004520
0x180004517  lea     ecx, [rax+1]
0x18000451a  lock cmpxchg [rdi], ecx
0x18000451e  jz      short loc_180004527
0x180004520  mov     eax, [rdi]
0x180004522  cmp     eax, r15d
0x180004525  jnz     short loc_180004517
0x180004527  lea     rcx, [rdi+8]; this
0x18000452b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004530  test    eax, eax
0x180004532  js      short loc_180004538
0x180004534  mov     byte ptr [rdi+30h], 1
0x180004538  xor     ecx, ecx
0x18000453a  test    eax, eax
0x18000453c  cmovs   ecx, eax
0x18000453f  xor     esi, esi
0x180004541  test    ecx, ecx
0x180004543  cmovs   esi, ecx
0x180004546  jmp     short loc_180004551
0x180004548  lea     ecx, [rax-1]
0x18000454b  lock cmpxchg [rdi], ecx
0x18000454f  jz      short loc_180004558
0x180004551  mov     eax, [rdi]
0x180004553  cmp     eax, r15d
0x180004556  jnz     short loc_180004548
0x180004558  test    esi, esi
0x18000455a  jnz     short loc_180004576
0x18000455c  mov     rax, [rbx]
0x18000455f  mov     r8, r14
0x180004562  mov     rdx, rbp
0x180004565  mov     rcx, rbx
0x180004568  mov     rax, [rax]
0x18000456b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004570  mov     esi, eax
0x180004572  test    eax, eax
0x180004574  jz      short loc_18000458D
0x180004576  mov     r8, [rbx]
0x180004579  mov     edx, 1
0x18000457e  mov     rcx, rbx
0x180004581  mov     rax, [r8+0A8h]
0x180004588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458d  mov     eax, esi
0x18000458f  add     rsp, 28h
0x180004593  pop     r15
0x180004595  pop     r14
0x180004597  pop     rdi
0x180004598  pop     rsi
0x180004599  pop     rbp
0x18000459a  pop     rbx
0x18000459b  retn
```
