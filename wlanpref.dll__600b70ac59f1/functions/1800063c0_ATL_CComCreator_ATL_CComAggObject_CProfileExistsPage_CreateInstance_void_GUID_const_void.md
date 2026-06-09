# ATL::CComCreator<ATL::CComAggObject<CProfileExistsPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800063c0`
- end: `0x1800064e8`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCProfileExistsPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800059e0`

## callees

- `0x18000130c`
- `0x1800063c0`
- `0x1800080a0`
- `0x180024bdc`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CProfileExistsPage>>::CreateInstance(
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
  v8 = operator new(0x128u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CProfileExistsPage>::`vftable';
    CProfileExistsPage::CProfileExistsPage((CProfileExistsPage *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CInfraConnectedPage>::`vftable'{for `CXWizardPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604>'};
    v9[15] = &ATL::CComContainedObject<CProfileExistsPage>::`vftable'{for `WTL::CPropertyPageImpl<CProfileExistsPage,WTL::CPropertyPageWindow>'};
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
0x1800063c0  mov     [rsp+arg_0], rbx
0x1800063c5  mov     [rsp+arg_10], r8
0x1800063ca  mov     [rsp+arg_8], rdx
0x1800063cf  push    rsi
0x1800063d0  push    rdi
0x1800063d1  push    r12
0x1800063d3  push    r14
0x1800063d5  push    r15
0x1800063d7  sub     rsp, 30h
0x1800063db  mov     r14, r8
0x1800063de  mov     r15, rdx
0x1800063e1  mov     r12, rcx
0x1800063e4  test    r8, r8
0x1800063e7  jnz     short loc_1800063F3
0x1800063e9  mov     eax, 80004003h
0x1800063ee  jmp     loc_1800064D6
0x1800063f3  mov     qword ptr [r8], 0
0x1800063fa  mov     esi, 8007000Eh
0x1800063ff  mov     [rsp+58h+arg_18], esi
0x180006403  mov     [rsp+58h+var_38], 0
0x18000640c  mov     ecx, 128h; Size
0x180006411  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006416  mov     rdi, rax
0x180006419  test    rdi, rdi
0x18000641c  jz      short loc_180006465
0x18000641e  mov     dword ptr [rax+8], 0
0x180006425  lea     rax, ??_7?$CComAggObject@VCProfileExistsPage@@@ATL@@6B@; const ATL::CComAggObject<CProfileExistsPage>::`vftable'
0x18000642c  mov     [rdi], rax
0x18000642f  lea     rcx, [rdi+18h]; this
0x180006433  call    ??0CProfileExistsPage@@QEAA@XZ; CProfileExistsPage::CProfileExistsPage(void)
0x180006438  lea     rax, ??_7?$CComContainedObject@VCInfraConnectedPage@@@ATL@@6B?$CXWizardPageBase@VCInfraConnectedPage@@$1?CLSID_InfraConnectedPage@@3U_GUID@@B$0CJGM@@@@; const ATL::CComContainedObject<CInfraConnectedPage>::`vftable'{for `CXWizardPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604>'}
0x18000643f  mov     [rdi+18h], rax
0x180006443  lea     rax, ??_7?$CComContainedObject@VCProfileExistsPage@@@ATL@@6B?$CPropertyPageImpl@VCProfileExistsPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComContainedObject<CProfileExistsPage>::`vftable'{for `WTL::CPropertyPageImpl<CProfileExistsPage,WTL::CPropertyPageWindow>'}
0x18000644a  mov     [rdi+78h], rax
0x18000644e  mov     [rdi+20h], r12
0x180006452  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006459  mov     rax, [rcx]
0x18000645c  mov     rax, [rax+8]
0x180006460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006465  mov     [rsp+58h+var_38], rdi
0x18000646a  jmp     short loc_18000647F
0x18000646c  mov     r14, [rsp+58h+arg_10]
0x180006471  mov     r15, [rsp+58h+arg_8]
0x180006476  mov     esi, [rsp+58h+arg_18]
0x18000647a  mov     rdi, [rsp+58h+var_38]
0x18000647f  test    rdi, rdi
0x180006482  jz      short loc_1800064D4
0x180006484  lea     rcx, [rdi+28h]; this
0x180006488  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000648d  xor     ecx, ecx
0x18000648f  test    eax, eax
0x180006491  cmovs   ecx, eax
0x180006494  xor     eax, eax
0x180006496  test    ecx, ecx
0x180006498  cmovs   eax, ecx
0x18000649b  xor     esi, esi
0x18000649d  test    eax, eax
0x18000649f  cmovs   esi, eax
0x1800064a2  test    esi, esi
0x1800064a4  jnz     short loc_1800064C0
0x1800064a6  mov     rax, [rdi]
0x1800064a9  mov     r8, r14
0x1800064ac  mov     rdx, r15
0x1800064af  mov     rcx, rdi
0x1800064b2  mov     rax, [rax]
0x1800064b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ba  mov     esi, eax
0x1800064bc  test    eax, eax
0x1800064be  jz      short loc_1800064D4
0x1800064c0  mov     rdx, [rdi]
0x1800064c3  mov     rax, [rdx+18h]
0x1800064c7  mov     edx, 1
0x1800064cc  mov     rcx, rdi
0x1800064cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d4  mov     eax, esi
0x1800064d6  mov     rbx, [rsp+58h+arg_0]
0x1800064db  add     rsp, 30h
0x1800064df  pop     r15
0x1800064e1  pop     r14
0x1800064e3  pop     r12
0x1800064e5  pop     rdi
0x1800064e6  pop     rsi
0x1800064e7  retn
```
