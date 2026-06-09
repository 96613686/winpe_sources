# ATL::CComCreator<ATL::CComAggObject<CInfraSetupPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006290`
- end: `0x1800063b8`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraSetupPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180005990`

## callees

- `0x18000130c`
- `0x180006290`
- `0x1800080a0`
- `0x180015770`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraSetupPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax
  int v11; // ecx
  int v12; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x138u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CInfraSetupPage>::`vftable';
    CInfraSetupPage::CInfraSetupPage((CInfraSetupPage *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CInfraSetupPage>::`vftable'{for `CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>'};
    v9[15] = &CInfraSetupPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraSetupPage,WTL::CPropertyPageWindow>'};
    v9[4] = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180006290  mov     [rsp+arg_0], rbx
0x180006295  mov     [rsp+arg_10], r8
0x18000629a  mov     [rsp+arg_8], rdx
0x18000629f  push    rsi
0x1800062a0  push    rdi
0x1800062a1  push    r12
0x1800062a3  push    r14
0x1800062a5  push    r15
0x1800062a7  sub     rsp, 30h
0x1800062ab  mov     r14, r8
0x1800062ae  mov     r15, rdx
0x1800062b1  mov     r12, rcx
0x1800062b4  test    r8, r8
0x1800062b7  jnz     short loc_1800062C3
0x1800062b9  mov     eax, 80004003h
0x1800062be  jmp     loc_1800063A6
0x1800062c3  mov     qword ptr [r8], 0
0x1800062ca  mov     esi, 8007000Eh
0x1800062cf  mov     [rsp+58h+arg_18], esi
0x1800062d3  mov     [rsp+58h+var_38], 0
0x1800062dc  mov     ecx, 138h; Size
0x1800062e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800062e6  mov     rdi, rax
0x1800062e9  test    rdi, rdi
0x1800062ec  jz      short loc_180006335
0x1800062ee  mov     dword ptr [rax+8], 0
0x1800062f5  lea     rax, ??_7?$CComAggObject@VCInfraSetupPage@@@ATL@@6B@; const ATL::CComAggObject<CInfraSetupPage>::`vftable'
0x1800062fc  mov     [rdi], rax
0x1800062ff  lea     rcx, [rdi+18h]; this
0x180006303  call    ??0CInfraSetupPage@@QEAA@XZ; CInfraSetupPage::CInfraSetupPage(void)
0x180006308  lea     rax, ??_7?$CComContainedObject@VCInfraSetupPage@@@ATL@@6B?$CXWizardPageBase@VCInfraSetupPage@@$1?CLSID_InfraSetupPage@@3U_GUID@@B$0CJGK@@@@; const ATL::CComContainedObject<CInfraSetupPage>::`vftable'{for `CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>'}
0x18000630f  mov     [rdi+18h], rax
0x180006313  lea     rax, ??_7CInfraSetupPage@@6B?$CPropertyPageImpl@VCInfraSetupPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const CInfraSetupPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraSetupPage,WTL::CPropertyPageWindow>'}
0x18000631a  mov     [rdi+78h], rax
0x18000631e  mov     [rdi+20h], r12
0x180006322  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006329  mov     rax, [rcx]
0x18000632c  mov     rax, [rax+8]
0x180006330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006335  mov     [rsp+58h+var_38], rdi
0x18000633a  jmp     short loc_18000634F
0x18000633c  mov     r14, [rsp+58h+arg_10]
0x180006341  mov     r15, [rsp+58h+arg_8]
0x180006346  mov     esi, [rsp+58h+arg_18]
0x18000634a  mov     rdi, [rsp+58h+var_38]
0x18000634f  test    rdi, rdi
0x180006352  jz      short loc_1800063A4
0x180006354  lea     rcx, [rdi+28h]; this
0x180006358  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000635d  xor     ecx, ecx
0x18000635f  test    eax, eax
0x180006361  cmovs   ecx, eax
0x180006364  xor     eax, eax
0x180006366  test    ecx, ecx
0x180006368  cmovs   eax, ecx
0x18000636b  xor     esi, esi
0x18000636d  test    eax, eax
0x18000636f  cmovs   esi, eax
0x180006372  test    esi, esi
0x180006374  jnz     short loc_180006390
0x180006376  mov     rax, [rdi]
0x180006379  mov     r8, r14
0x18000637c  mov     rdx, r15
0x18000637f  mov     rcx, rdi
0x180006382  mov     rax, [rax]
0x180006385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000638a  mov     esi, eax
0x18000638c  test    eax, eax
0x18000638e  jz      short loc_1800063A4
0x180006390  mov     rdx, [rdi]
0x180006393  mov     rax, [rdx+18h]
0x180006397  mov     edx, 1
0x18000639c  mov     rcx, rdi
0x18000639f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a4  mov     eax, esi
0x1800063a6  mov     rbx, [rsp+58h+arg_0]
0x1800063ab  add     rsp, 30h
0x1800063af  pop     r15
0x1800063b1  pop     r14
0x1800063b3  pop     r12
0x1800063b5  pop     rdi
0x1800063b6  pop     rsi
0x1800063b7  retn
```
