# ATL::CComCreator<ATL::CComObject<CInfraAdapterPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006744`
- end: `0x180006841`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraAdapterPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800058b0`

## callees

- `0x18000130c`
- `0x180006744`
- `0x1800080a0`
- `0x180023cb4`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraAdapterPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  CInfraAdapterPage *v7; // rax
  CInfraAdapterPage *v8; // rbx
  int v9; // eax
  int v10; // ecx
  CInfraAdapterPage *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CInfraAdapterPage *)operator new(0x150u);
    v8 = v7;
    if ( v7 )
    {
      CInfraAdapterPage::CInfraAdapterPage(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CInfraAdapterPage>::`vftable'{for `CXWizardPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607>'};
      *((_QWORD *)v8 + 12) = &ATL::CComObject<CInfraAdapterPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraAdapterPage,WTL::CPropertyPageWindow>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CInfraAdapterPage *)((char *)v8 + 16));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CInfraAdapterPage *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006744  mov     [rsp+arg_10], r8
0x180006749  mov     [rsp+arg_8], rdx
0x18000674e  mov     [rsp+arg_0], rcx
0x180006753  push    rbx
0x180006754  push    rsi
0x180006755  push    rdi
0x180006756  push    r14
0x180006758  sub     rsp, 28h
0x18000675c  mov     rsi, r8
0x18000675f  mov     r14, rdx
0x180006762  test    r8, r8
0x180006765  jnz     short loc_180006771
0x180006767  mov     eax, 80004003h
0x18000676c  jmp     loc_180006837
0x180006771  mov     qword ptr [r8], 0
0x180006778  mov     edi, 8007000Eh
0x18000677d  mov     dword ptr [rsp+48h+arg_0], edi
0x180006781  mov     [rsp+48h+arg_18], 0
0x18000678a  mov     ecx, 150h; Size
0x18000678f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006794  mov     rbx, rax
0x180006797  test    rbx, rbx
0x18000679a  jz      short loc_1800067CC
0x18000679c  mov     rcx, rax; this
0x18000679f  call    ??0CInfraAdapterPage@@QEAA@XZ; CInfraAdapterPage::CInfraAdapterPage(void)
0x1800067a4  lea     rax, ??_7?$CComObject@VCInfraAdapterPage@@@ATL@@6B?$CXWizardPageBase@VCInfraAdapterPage@@$1?CLSID_InfraAdapterPage@@3U_GUID@@B$0CJGP@@@@; const ATL::CComObject<CInfraAdapterPage>::`vftable'{for `CXWizardPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607>'}
0x1800067ab  mov     [rbx], rax
0x1800067ae  lea     rax, ??_7?$CComObject@VCInfraAdapterPage@@@ATL@@6B?$CPropertyPageImpl@VCInfraAdapterPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CInfraAdapterPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraAdapterPage,WTL::CPropertyPageWindow>'}
0x1800067b5  mov     [rbx+60h], rax
0x1800067b9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800067c0  mov     rax, [rcx]
0x1800067c3  mov     rax, [rax+8]
0x1800067c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067cc  mov     [rsp+48h+arg_18], rbx
0x1800067d1  jmp     short loc_1800067E6
0x1800067d3  mov     rsi, [rsp+48h+arg_10]
0x1800067d8  mov     r14, [rsp+48h+arg_8]
0x1800067dd  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800067e1  mov     rbx, [rsp+48h+arg_18]
0x1800067e6  test    rbx, rbx
0x1800067e9  jz      short loc_180006835
0x1800067eb  lea     rcx, [rbx+10h]; this
0x1800067ef  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800067f4  xor     ecx, ecx
0x1800067f6  test    eax, eax
0x1800067f8  cmovs   ecx, eax
0x1800067fb  xor     edi, edi
0x1800067fd  test    ecx, ecx
0x1800067ff  cmovs   edi, ecx
0x180006802  test    edi, edi
0x180006804  jnz     short loc_180006820
0x180006806  mov     rax, [rbx]
0x180006809  mov     r8, rsi
0x18000680c  mov     rdx, r14
0x18000680f  mov     rcx, rbx
0x180006812  mov     rax, [rax]
0x180006815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000681a  mov     edi, eax
0x18000681c  test    eax, eax
0x18000681e  jz      short loc_180006835
0x180006820  lea     rcx, [rbx+60h]
0x180006824  mov     rdx, [rcx]
0x180006827  mov     rax, [rdx+8]
0x18000682b  mov     edx, 1
0x180006830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006835  mov     eax, edi
0x180006837  add     rsp, 28h
0x18000683b  pop     r14
0x18000683d  pop     rdi
0x18000683e  pop     rsi
0x18000683f  pop     rbx
0x180006840  retn
```
