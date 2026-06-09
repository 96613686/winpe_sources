# ATL::CComCreator<ATL::CComAggObject<CInfraAdapterPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005a34`
- end: `0x180005b5c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraAdapterPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800058b0`

## callees

- `0x18000130c`
- `0x180005a34`
- `0x1800080a0`
- `0x180023cb4`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraAdapterPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  _QWORD *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x168u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComAggObject<CInfraAdapterPage>::`vftable';
      CInfraAdapterPage::CInfraAdapterPage((CInfraAdapterPage *)(v8 + 3));
      v9[3] = &ATL::CComContainedObject<CInfraAdapterPage>::`vftable'{for `CXWizardPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607>'};
      v9[15] = &CInfraAdapterPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraAdapterPage,WTL::CPropertyPageWindow>'};
      v9[4] = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 5));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180005a34  mov     [rsp+arg_0], rbx
0x180005a39  mov     [rsp+arg_10], r8
0x180005a3e  mov     [rsp+arg_8], rdx
0x180005a43  push    rsi
0x180005a44  push    rdi
0x180005a45  push    r12
0x180005a47  push    r14
0x180005a49  push    r15
0x180005a4b  sub     rsp, 30h
0x180005a4f  mov     r14, r8
0x180005a52  mov     r15, rdx
0x180005a55  mov     r12, rcx
0x180005a58  test    r8, r8
0x180005a5b  jnz     short loc_180005A67
0x180005a5d  mov     eax, 80004003h
0x180005a62  jmp     loc_180005B4A
0x180005a67  mov     qword ptr [r8], 0
0x180005a6e  mov     esi, 8007000Eh
0x180005a73  mov     [rsp+58h+arg_18], esi
0x180005a77  mov     [rsp+58h+var_38], 0
0x180005a80  mov     ecx, 168h; Size
0x180005a85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a8a  mov     rdi, rax
0x180005a8d  test    rdi, rdi
0x180005a90  jz      short loc_180005AD9
0x180005a92  mov     dword ptr [rax+8], 0
0x180005a99  lea     rax, ??_7?$CComAggObject@VCInfraAdapterPage@@@ATL@@6B@; const ATL::CComAggObject<CInfraAdapterPage>::`vftable'
0x180005aa0  mov     [rdi], rax
0x180005aa3  lea     rcx, [rdi+18h]; this
0x180005aa7  call    ??0CInfraAdapterPage@@QEAA@XZ; CInfraAdapterPage::CInfraAdapterPage(void)
0x180005aac  lea     rax, ??_7?$CComContainedObject@VCInfraAdapterPage@@@ATL@@6B?$CXWizardPageBase@VCInfraAdapterPage@@$1?CLSID_InfraAdapterPage@@3U_GUID@@B$0CJGP@@@@; const ATL::CComContainedObject<CInfraAdapterPage>::`vftable'{for `CXWizardPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607>'}
0x180005ab3  mov     [rdi+18h], rax
0x180005ab7  lea     rax, ??_7CInfraAdapterPage@@6B?$CPropertyPageImpl@VCInfraAdapterPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const CInfraAdapterPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraAdapterPage,WTL::CPropertyPageWindow>'}
0x180005abe  mov     [rdi+78h], rax
0x180005ac2  mov     [rdi+20h], r12
0x180005ac6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005acd  mov     rax, [rcx]
0x180005ad0  mov     rax, [rax+8]
0x180005ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad9  mov     [rsp+58h+var_38], rdi
0x180005ade  jmp     short loc_180005AF3
0x180005ae0  mov     r14, [rsp+58h+arg_10]
0x180005ae5  mov     r15, [rsp+58h+arg_8]
0x180005aea  mov     esi, [rsp+58h+arg_18]
0x180005aee  mov     rdi, [rsp+58h+var_38]
0x180005af3  test    rdi, rdi
0x180005af6  jz      short loc_180005B48
0x180005af8  lea     rcx, [rdi+28h]; this
0x180005afc  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005b01  xor     ecx, ecx
0x180005b03  test    eax, eax
0x180005b05  cmovs   ecx, eax
0x180005b08  xor     eax, eax
0x180005b0a  test    ecx, ecx
0x180005b0c  cmovs   eax, ecx
0x180005b0f  xor     esi, esi
0x180005b11  test    eax, eax
0x180005b13  cmovs   esi, eax
0x180005b16  test    esi, esi
0x180005b18  jnz     short loc_180005B34
0x180005b1a  mov     rax, [rdi]
0x180005b1d  mov     r8, r14
0x180005b20  mov     rdx, r15
0x180005b23  mov     rcx, rdi
0x180005b26  mov     rax, [rax]
0x180005b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2e  mov     esi, eax
0x180005b30  test    eax, eax
0x180005b32  jz      short loc_180005B48
0x180005b34  mov     rdx, [rdi]
0x180005b37  mov     rax, [rdx+18h]
0x180005b3b  mov     edx, 1
0x180005b40  mov     rcx, rdi
0x180005b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b48  mov     eax, esi
0x180005b4a  mov     rbx, [rsp+58h+arg_0]
0x180005b4f  add     rsp, 30h
0x180005b53  pop     r15
0x180005b55  pop     r14
0x180005b57  pop     r12
0x180005b59  pop     rdi
0x180005b5a  pop     rsi
0x180005b5b  retn
```
