# ATL::CComCreator<ATL::CComObject<CInfraConnectPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006848`
- end: `0x18000694a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraConnectPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800058d0`

## callees

- `0x18000130c`
- `0x180006848`
- `0x1800080a0`
- `0x1800208f0`
- `0x180020cac`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraConnectPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  CInfraConnectPage *v7; // rax
  CInfraConnectPage *v8; // rbx
  int v9; // eax
  CInfraConnectPage *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CInfraConnectPage *)operator new(0x5F0u);
    v8 = v7;
    if ( v7 )
    {
      CInfraConnectPage::CInfraConnectPage(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CInfraConnectPage>::`vftable'{for `CXWizardPageBase<CInfraConnectPage,&_GUID const CLSID_InfraConnectPage,10601>'};
      *((_QWORD *)v8 + 12) = &ATL::CComObject<CInfraConnectPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectPage,WTL::CPropertyPageWindow>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CInfraConnectPage *)((char *)v8 + 16));
    if ( v9 >= 0 )
      v9 = CInfraConnectPage::FinalConstruct(v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CInfraConnectPage *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006848  mov     [rsp+arg_10], r8
0x18000684d  mov     [rsp+arg_8], rdx
0x180006852  mov     [rsp+arg_0], rcx
0x180006857  push    rbx
0x180006858  push    rsi
0x180006859  push    rdi
0x18000685a  push    r14
0x18000685c  sub     rsp, 28h
0x180006860  mov     rsi, r8
0x180006863  mov     r14, rdx
0x180006866  test    r8, r8
0x180006869  jnz     short loc_180006875
0x18000686b  mov     eax, 80004003h
0x180006870  jmp     loc_180006940
0x180006875  mov     qword ptr [r8], 0
0x18000687c  mov     edi, 8007000Eh
0x180006881  mov     dword ptr [rsp+48h+arg_0], edi
0x180006885  mov     [rsp+48h+arg_18], 0
0x18000688e  mov     ecx, 5F0h; Size
0x180006893  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006898  mov     rbx, rax
0x18000689b  test    rbx, rbx
0x18000689e  jz      short loc_1800068D0
0x1800068a0  mov     rcx, rax; this
0x1800068a3  call    ??0CInfraConnectPage@@QEAA@XZ; CInfraConnectPage::CInfraConnectPage(void)
0x1800068a8  lea     rax, ??_7?$CComObject@VCInfraConnectPage@@@ATL@@6B?$CXWizardPageBase@VCInfraConnectPage@@$1?CLSID_InfraConnectPage@@3U_GUID@@B$0CJGJ@@@@; const ATL::CComObject<CInfraConnectPage>::`vftable'{for `CXWizardPageBase<CInfraConnectPage,&_GUID const CLSID_InfraConnectPage,10601>'}
0x1800068af  mov     [rbx], rax
0x1800068b2  lea     rax, ??_7?$CComObject@VCInfraConnectPage@@@ATL@@6B?$CPropertyPageImpl@VCInfraConnectPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CInfraConnectPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectPage,WTL::CPropertyPageWindow>'}
0x1800068b9  mov     [rbx+60h], rax
0x1800068bd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800068c4  mov     rax, [rcx]
0x1800068c7  mov     rax, [rax+8]
0x1800068cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d0  mov     [rsp+48h+arg_18], rbx
0x1800068d5  jmp     short loc_1800068EA
0x1800068d7  mov     rsi, [rsp+48h+arg_10]
0x1800068dc  mov     r14, [rsp+48h+arg_8]
0x1800068e1  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800068e5  mov     rbx, [rsp+48h+arg_18]
0x1800068ea  test    rbx, rbx
0x1800068ed  jz      short loc_18000693E
0x1800068ef  lea     rcx, [rbx+10h]; this
0x1800068f3  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800068f8  test    eax, eax
0x1800068fa  js      short loc_180006904
0x1800068fc  mov     rcx, rbx; this
0x1800068ff  call    ?FinalConstruct@CInfraConnectPage@@QEAAJXZ; CInfraConnectPage::FinalConstruct(void)
0x180006904  xor     edi, edi
0x180006906  test    eax, eax
0x180006908  cmovs   edi, eax
0x18000690b  test    edi, edi
0x18000690d  jnz     short loc_180006929
0x18000690f  mov     rax, [rbx]
0x180006912  mov     r8, rsi
0x180006915  mov     rdx, r14
0x180006918  mov     rcx, rbx
0x18000691b  mov     rax, [rax]
0x18000691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006923  mov     edi, eax
0x180006925  test    eax, eax
0x180006927  jz      short loc_18000693E
0x180006929  lea     rcx, [rbx+60h]
0x18000692d  mov     rdx, [rcx]
0x180006930  mov     rax, [rdx+8]
0x180006934  mov     edx, 1
0x180006939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693e  mov     eax, edi
0x180006940  add     rsp, 28h
0x180006944  pop     r14
0x180006946  pop     rdi
0x180006947  pop     rsi
0x180006948  pop     rbx
0x180006949  retn
```
