# ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart> * *)

- ea: `0x180011344`
- end: `0x180011442`
- name: `?CreateInstance@?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@SAJPEAPEAV12@@Z`
- size: `254`
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
- `0x180011344`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::CreateInstance(
        CWdsTransportNamespace **a1)
{
  CWdsTransportNamespace **v1; // r14
  unsigned int v3; // esi
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
    v4 = (CWdsTransportNamespace *)operator new(0xE0u);
    v5 = v4;
    if ( v4 )
    {
      CWdsTransportNamespace::CWdsTransportNamespace(v4);
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `CWdsTransportNamespace'};
      *((_QWORD *)v5 + 26) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v5 + 27) = &ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable';
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
0x180011344  mov     [rsp+arg_18], rbx
0x180011349  mov     [rsp+arg_0], rcx
0x18001134e  push    rsi
0x18001134f  push    rdi
0x180011350  push    r14
0x180011352  sub     rsp, 20h
0x180011356  mov     r14, rcx
0x180011359  test    rcx, rcx
0x18001135c  jnz     short loc_180011368
0x18001135e  mov     eax, 80004003h
0x180011363  jmp     loc_180011433
0x180011368  and     qword ptr [rcx], 0
0x18001136c  mov     esi, 8007000Eh
0x180011371  mov     [rsp+38h+arg_8], esi
0x180011375  and     [rsp+38h+arg_10], 0
0x18001137b  mov     ecx, 0E0h; Size
0x180011380  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011385  mov     rdi, rax
0x180011388  test    rdi, rdi
0x18001138b  jz      short loc_1800113CE
0x18001138d  mov     rcx, rax; this
0x180011390  call    ??0CWdsTransportNamespace@@QEAA@XZ; CWdsTransportNamespace::CWdsTransportNamespace(void)
0x180011395  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@6BCWdsTransportNamespace@@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `CWdsTransportNamespace'}
0x18001139c  mov     [rdi], rax
0x18001139f  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@6B?$IDispatchImpl@UIWdsTransportNamespaceScheduledCast@@$1?IID_IWdsTransportNamespaceScheduledCast@@3U_GUID@@B$1?LIBID_WdsTptMgmtLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceScheduledCast,&_GUID const IID_IWdsTransportNamespaceScheduledCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'}
0x1800113a6  mov     [rdi+0D0h], rax
0x1800113ad  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@6B@; const ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::`vftable'
0x1800113b4  mov     [rdi+0D8h], rax
0x1800113bb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800113c2  mov     rax, [rcx]
0x1800113c5  mov     rax, [rax+8]
0x1800113c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ce  mov     [rsp+38h+arg_10], rdi
0x1800113d3  jmp     short loc_1800113E3
0x1800113d5  mov     r14, [rsp+38h+arg_0]
0x1800113da  mov     esi, [rsp+38h+arg_8]
0x1800113de  mov     rdi, [rsp+38h+arg_10]
0x1800113e3  test    rdi, rdi
0x1800113e6  jz      short loc_18001142E
0x1800113e8  lea     rcx, [rdi+8]; volatile int *
0x1800113ec  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800113f1  lea     rcx, [rdi+10h]; this
0x1800113f5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800113fa  xor     edx, edx
0x1800113fc  test    eax, eax
0x1800113fe  cmovs   edx, eax
0x180011401  xor     esi, esi
0x180011403  test    edx, edx
0x180011405  cmovs   esi, edx
0x180011408  lea     rcx, [rdi+8]; volatile int *
0x18001140c  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180011411  test    esi, esi
0x180011413  jz      short loc_18001142E
0x180011415  mov     rdx, [rdi]
0x180011418  mov     rax, [rdx+100h]
0x18001141f  mov     edx, 1
0x180011424  mov     rcx, rdi
0x180011427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001142c  xor     edi, edi
0x18001142e  mov     [r14], rdi
0x180011431  mov     eax, esi
0x180011433  mov     rbx, [rsp+38h+arg_18]
0x180011438  add     rsp, 20h
0x18001143c  pop     r14
0x18001143e  pop     rdi
0x18001143f  pop     rsi
0x180011440  retn
```
