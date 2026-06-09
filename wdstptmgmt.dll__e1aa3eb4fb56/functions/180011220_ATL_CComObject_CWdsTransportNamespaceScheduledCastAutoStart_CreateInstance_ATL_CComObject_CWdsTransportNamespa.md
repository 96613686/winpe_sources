# ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart> * *)

- ea: `0x180011220`
- end: `0x18001133d`
- name: `?CreateInstance@?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@SAJPEAPEAV12@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011448`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180006654`
- `0x180006680`
- `0x180010b70`
- `0x180011220`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::CreateInstance(
        CWdsTransportNamespace **a1)
{
  CWdsTransportNamespace **v1; // r15
  unsigned int v3; // r14d
  CWdsTransportNamespace *v4; // rax
  CWdsTransportNamespace *v5; // rdi
  int v6; // eax
  int v7; // edx
  CWdsTransportNamespace *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (CWdsTransportNamespace *)operator new(0xF0u);
    v5 = v4;
    if ( v4 )
    {
      CWdsTransportNamespace::CWdsTransportNamespace(v4);
      *((_DWORD *)v5 + 56) = 0;
      *((_DWORD *)v5 + 57) = 0;
      *((_QWORD *)v5 + 29) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `CWdsTransportNamespace'};
      *((_QWORD *)v5 + 26) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v5 + 27) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v5 + 2);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((CWdsTransportNamespace *)((char *)v5 + 16));
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v5 + 2);
    if ( v3 )
    {
      (*(void (__fastcall **)(CWdsTransportNamespace *, __int64))(*(_QWORD *)v5 + 256LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180011220  mov     [rsp+arg_18], rbx
0x180011225  mov     [rsp+arg_0], rcx
0x18001122a  push    rdi
0x18001122b  push    r14
0x18001122d  push    r15
0x18001122f  sub     rsp, 20h
0x180011233  mov     r15, rcx
0x180011236  test    rcx, rcx
0x180011239  jnz     short loc_180011245
0x18001123b  mov     eax, 80004003h
0x180011240  jmp     loc_18001132D
0x180011245  and     qword ptr [rcx], 0
0x180011249  mov     r14d, 8007000Eh
0x18001124f  mov     [rsp+38h+arg_8], r14d
0x180011254  and     [rsp+38h+arg_10], 0
0x18001125a  mov     ecx, 0F0h; Size
0x18001125f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011264  mov     rdi, rax
0x180011267  test    rdi, rdi
0x18001126a  jz      short loc_1800112C3
0x18001126c  mov     rcx, rax; this
0x18001126f  call    ??0CWdsTransportNamespace@@QEAA@XZ; CWdsTransportNamespace::CWdsTransportNamespace(void)
0x180011274  and     dword ptr [rdi+0E0h], 0
0x18001127b  and     dword ptr [rdi+0E4h], 0
0x180011282  and     qword ptr [rdi+0E8h], 0
0x18001128a  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@6BCWdsTransportNamespace@@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `CWdsTransportNamespace'}
0x180011291  mov     [rdi], rax
0x180011294  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@6B?$IDispatchImpl@UIWdsTransportNamespaceScheduledCast@@$1?IID_IWdsTransportNamespaceScheduledCast@@3U_GUID@@B$1?LIBID_WdsTptMgmtLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'}
0x18001129b  mov     [rdi+0D0h], rax
0x1800112a2  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@6B@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::`vftable'
0x1800112a9  mov     [rdi+0D8h], rax
0x1800112b0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800112b7  mov     rax, [rcx]
0x1800112ba  mov     rax, [rax+8]
0x1800112be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112c3  mov     [rsp+38h+arg_10], rdi
0x1800112c8  jmp     short loc_1800112D9
0x1800112ca  mov     r15, [rsp+38h+arg_0]
0x1800112cf  mov     r14d, [rsp+38h+arg_8]
0x1800112d4  mov     rdi, [rsp+38h+arg_10]
0x1800112d9  test    rdi, rdi
0x1800112dc  jz      short loc_180011327
0x1800112de  lea     rcx, [rdi+8]; volatile int *
0x1800112e2  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800112e7  lea     rcx, [rdi+10h]; this
0x1800112eb  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800112f0  xor     edx, edx
0x1800112f2  test    eax, eax
0x1800112f4  cmovs   edx, eax
0x1800112f7  xor     r14d, r14d
0x1800112fa  test    edx, edx
0x1800112fc  cmovs   r14d, edx
0x180011300  lea     rcx, [rdi+8]; volatile int *
0x180011304  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180011309  test    r14d, r14d
0x18001130c  jz      short loc_180011327
0x18001130e  mov     rdx, [rdi]
0x180011311  mov     rax, [rdx+100h]
0x180011318  mov     edx, 1
0x18001131d  mov     rcx, rdi
0x180011320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011325  xor     edi, edi
0x180011327  mov     [r15], rdi
0x18001132a  mov     eax, r14d
0x18001132d  mov     rbx, [rsp+38h+arg_18]
0x180011332  add     rsp, 20h
0x180011336  pop     r15
0x180011338  pop     r14
0x18001133a  pop     rdi
0x18001133b  retn
```
