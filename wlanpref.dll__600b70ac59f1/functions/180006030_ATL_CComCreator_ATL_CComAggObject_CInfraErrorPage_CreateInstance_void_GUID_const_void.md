# ATL::CComCreator<ATL::CComAggObject<CInfraErrorPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006030`
- end: `0x180006158`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraErrorPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005950`

## callees

- `0x18000130c`
- `0x180002b8c`
- `0x180006030`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraErrorPage>>::CreateInstance(
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
  v8 = operator new(0x120u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CInfraErrorPage>::`vftable';
    CInfraErrorPage::CInfraErrorPage((CInfraErrorPage *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CInfraErrorPage>::`vftable'{for `CXWizardPageBase<CInfraErrorPage,&_GUID const CLSID_InfraErrorPage,10606>'};
    v9[15] = &CInfraErrorPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraErrorPage,WTL::CPropertyPageWindow>'};
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
0x180006030  mov     [rsp+arg_0], rbx
0x180006035  mov     [rsp+arg_10], r8
0x18000603a  mov     [rsp+arg_8], rdx
0x18000603f  push    rsi
0x180006040  push    rdi
0x180006041  push    r12
0x180006043  push    r14
0x180006045  push    r15
0x180006047  sub     rsp, 30h
0x18000604b  mov     r14, r8
0x18000604e  mov     r15, rdx
0x180006051  mov     r12, rcx
0x180006054  test    r8, r8
0x180006057  jnz     short loc_180006063
0x180006059  mov     eax, 80004003h
0x18000605e  jmp     loc_180006146
0x180006063  mov     qword ptr [r8], 0
0x18000606a  mov     esi, 8007000Eh
0x18000606f  mov     [rsp+58h+arg_18], esi
0x180006073  mov     [rsp+58h+var_38], 0
0x18000607c  mov     ecx, 120h; Size
0x180006081  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006086  mov     rdi, rax
0x180006089  test    rdi, rdi
0x18000608c  jz      short loc_1800060D5
0x18000608e  mov     dword ptr [rax+8], 0
0x180006095  lea     rax, ??_7?$CComAggObject@VCInfraErrorPage@@@ATL@@6B@; const ATL::CComAggObject<CInfraErrorPage>::`vftable'
0x18000609c  mov     [rdi], rax
0x18000609f  lea     rcx, [rdi+18h]; this
0x1800060a3  call    ??0CInfraErrorPage@@QEAA@XZ; CInfraErrorPage::CInfraErrorPage(void)
0x1800060a8  lea     rax, ??_7?$CComContainedObject@VCInfraErrorPage@@@ATL@@6B?$CXWizardPageBase@VCInfraErrorPage@@$1?CLSID_InfraErrorPage@@3U_GUID@@B$0CJGO@@@@; const ATL::CComContainedObject<CInfraErrorPage>::`vftable'{for `CXWizardPageBase<CInfraErrorPage,&_GUID const CLSID_InfraErrorPage,10606>'}
0x1800060af  mov     [rdi+18h], rax
0x1800060b3  lea     rax, ??_7CInfraErrorPage@@6B?$CPropertyPageImpl@VCInfraErrorPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const CInfraErrorPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraErrorPage,WTL::CPropertyPageWindow>'}
0x1800060ba  mov     [rdi+78h], rax
0x1800060be  mov     [rdi+20h], r12
0x1800060c2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800060c9  mov     rax, [rcx]
0x1800060cc  mov     rax, [rax+8]
0x1800060d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d5  mov     [rsp+58h+var_38], rdi
0x1800060da  jmp     short loc_1800060EF
0x1800060dc  mov     r14, [rsp+58h+arg_10]
0x1800060e1  mov     r15, [rsp+58h+arg_8]
0x1800060e6  mov     esi, [rsp+58h+arg_18]
0x1800060ea  mov     rdi, [rsp+58h+var_38]
0x1800060ef  test    rdi, rdi
0x1800060f2  jz      short loc_180006144
0x1800060f4  lea     rcx, [rdi+28h]; this
0x1800060f8  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800060fd  xor     ecx, ecx
0x1800060ff  test    eax, eax
0x180006101  cmovs   ecx, eax
0x180006104  xor     eax, eax
0x180006106  test    ecx, ecx
0x180006108  cmovs   eax, ecx
0x18000610b  xor     esi, esi
0x18000610d  test    eax, eax
0x18000610f  cmovs   esi, eax
0x180006112  test    esi, esi
0x180006114  jnz     short loc_180006130
0x180006116  mov     rax, [rdi]
0x180006119  mov     r8, r14
0x18000611c  mov     rdx, r15
0x18000611f  mov     rcx, rdi
0x180006122  mov     rax, [rax]
0x180006125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612a  mov     esi, eax
0x18000612c  test    eax, eax
0x18000612e  jz      short loc_180006144
0x180006130  mov     rdx, [rdi]
0x180006133  mov     rax, [rdx+18h]
0x180006137  mov     edx, 1
0x18000613c  mov     rcx, rdi
0x18000613f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006144  mov     eax, esi
0x180006146  mov     rbx, [rsp+58h+arg_0]
0x18000614b  add     rsp, 30h
0x18000614f  pop     r15
0x180006151  pop     r14
0x180006153  pop     r12
0x180006155  pop     rdi
0x180006156  pop     rsi
0x180006157  retn
```
