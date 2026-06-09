# ATL::CComCreator<ATL::CComAggObject<CInfraConnectPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005b64`
- end: `0x180005c94`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraConnectPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800058d0`

## callees

- `0x18000130c`
- `0x180005b64`
- `0x1800080a0`
- `0x1800208f0`
- `0x180020cac`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraConnectPage>>::CreateInstance(
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
  int v11; // edx
  _QWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x608u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComAggObject<CInfraConnectPage>::`vftable';
      CInfraConnectPage::CInfraConnectPage((CInfraConnectPage *)(v8 + 3));
      v9[3] = &ATL::CComContainedObject<CInfraConnectPage>::`vftable'{for `CXWizardPageBase<CInfraConnectPage,&_GUID const CLSID_InfraConnectPage,10601>'};
      v9[15] = &CInfraConnectPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectPage,WTL::CPropertyPageWindow>'};
      v9[4] = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 5));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CInfraConnectPage::FinalConstruct((CInfraConnectPage *)(v9 + 3));
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180005b64  mov     [rsp+arg_0], rbx
0x180005b69  mov     [rsp+arg_10], r8
0x180005b6e  mov     [rsp+arg_8], rdx
0x180005b73  push    rsi
0x180005b74  push    rdi
0x180005b75  push    r12
0x180005b77  push    r14
0x180005b79  push    r15
0x180005b7b  sub     rsp, 30h
0x180005b7f  mov     r14, r8
0x180005b82  mov     r15, rdx
0x180005b85  mov     r12, rcx
0x180005b88  test    r8, r8
0x180005b8b  jnz     short loc_180005B97
0x180005b8d  mov     eax, 80004003h
0x180005b92  jmp     loc_180005C82
0x180005b97  mov     qword ptr [r8], 0
0x180005b9e  mov     esi, 8007000Eh
0x180005ba3  mov     [rsp+58h+arg_18], esi
0x180005ba7  mov     [rsp+58h+var_38], 0
0x180005bb0  mov     ecx, 608h; Size
0x180005bb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005bba  mov     rdi, rax
0x180005bbd  test    rdi, rdi
0x180005bc0  jz      short loc_180005C09
0x180005bc2  mov     dword ptr [rax+8], 0
0x180005bc9  lea     rax, ??_7?$CComAggObject@VCInfraConnectPage@@@ATL@@6B@; const ATL::CComAggObject<CInfraConnectPage>::`vftable'
0x180005bd0  mov     [rdi], rax
0x180005bd3  lea     rcx, [rdi+18h]; this
0x180005bd7  call    ??0CInfraConnectPage@@QEAA@XZ; CInfraConnectPage::CInfraConnectPage(void)
0x180005bdc  lea     rax, ??_7?$CComContainedObject@VCInfraConnectPage@@@ATL@@6B?$CXWizardPageBase@VCInfraConnectPage@@$1?CLSID_InfraConnectPage@@3U_GUID@@B$0CJGJ@@@@; const ATL::CComContainedObject<CInfraConnectPage>::`vftable'{for `CXWizardPageBase<CInfraConnectPage,&_GUID const CLSID_InfraConnectPage,10601>'}
0x180005be3  mov     [rdi+18h], rax
0x180005be7  lea     rax, ??_7CInfraConnectPage@@6B?$CPropertyPageImpl@VCInfraConnectPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const CInfraConnectPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectPage,WTL::CPropertyPageWindow>'}
0x180005bee  mov     [rdi+78h], rax
0x180005bf2  mov     [rdi+20h], r12
0x180005bf6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005bfd  mov     rax, [rcx]
0x180005c00  mov     rax, [rax+8]
0x180005c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c09  mov     [rsp+58h+var_38], rdi
0x180005c0e  jmp     short loc_180005C23
0x180005c10  mov     r14, [rsp+58h+arg_10]
0x180005c15  mov     r15, [rsp+58h+arg_8]
0x180005c1a  mov     esi, [rsp+58h+arg_18]
0x180005c1e  mov     rdi, [rsp+58h+var_38]
0x180005c23  test    rdi, rdi
0x180005c26  jz      short loc_180005C80
0x180005c28  lea     rcx, [rdi+28h]; this
0x180005c2c  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005c31  xor     edx, edx
0x180005c33  test    eax, eax
0x180005c35  cmovs   edx, eax
0x180005c38  test    edx, edx
0x180005c3a  js      short loc_180005C47
0x180005c3c  lea     rcx, [rdi+18h]; this
0x180005c40  call    ?FinalConstruct@CInfraConnectPage@@QEAAJXZ; CInfraConnectPage::FinalConstruct(void)
0x180005c45  mov     edx, eax
0x180005c47  xor     esi, esi
0x180005c49  test    edx, edx
0x180005c4b  cmovs   esi, edx
0x180005c4e  test    esi, esi
0x180005c50  jnz     short loc_180005C6C
0x180005c52  mov     rax, [rdi]
0x180005c55  mov     r8, r14
0x180005c58  mov     rdx, r15
0x180005c5b  mov     rcx, rdi
0x180005c5e  mov     rax, [rax]
0x180005c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c66  mov     esi, eax
0x180005c68  test    eax, eax
0x180005c6a  jz      short loc_180005C80
0x180005c6c  mov     rdx, [rdi]
0x180005c6f  mov     rax, [rdx+18h]
0x180005c73  mov     edx, 1
0x180005c78  mov     rcx, rdi
0x180005c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c80  mov     eax, esi
0x180005c82  mov     rbx, [rsp+58h+arg_0]
0x180005c87  add     rsp, 30h
0x180005c8b  pop     r15
0x180005c8d  pop     r14
0x180005c8f  pop     r12
0x180005c91  pop     rdi
0x180005c92  pop     rsi
0x180005c93  retn
```
