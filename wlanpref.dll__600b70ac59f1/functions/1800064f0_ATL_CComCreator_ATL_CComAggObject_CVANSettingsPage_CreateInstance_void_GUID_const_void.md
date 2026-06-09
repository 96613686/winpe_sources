# ATL::CComCreator<ATL::CComAggObject<CVANSettingsPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800064f0`
- end: `0x180006618`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCVANSettingsPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005a00`

## callees

- `0x18000130c`
- `0x180002bf0`
- `0x1800064f0`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CVANSettingsPage>>::CreateInstance(
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
  v8 = operator new(0x130u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CVANSettingsPage>::`vftable';
    CVANSettingsPage::CVANSettingsPage((CVANSettingsPage *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CVANSettingsPage>::`vftable'{for `CXWizardPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608>'};
    v9[15] = &ATL::CComContainedObject<CVANSettingsPage>::`vftable'{for `WTL::CPropertyPageImpl<CVANSettingsPage,WTL::CPropertyPageWindow>'};
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
0x1800064f0  mov     [rsp+arg_0], rbx
0x1800064f5  mov     [rsp+arg_10], r8
0x1800064fa  mov     [rsp+arg_8], rdx
0x1800064ff  push    rsi
0x180006500  push    rdi
0x180006501  push    r12
0x180006503  push    r14
0x180006505  push    r15
0x180006507  sub     rsp, 30h
0x18000650b  mov     r14, r8
0x18000650e  mov     r15, rdx
0x180006511  mov     r12, rcx
0x180006514  test    r8, r8
0x180006517  jnz     short loc_180006523
0x180006519  mov     eax, 80004003h
0x18000651e  jmp     loc_180006606
0x180006523  mov     qword ptr [r8], 0
0x18000652a  mov     esi, 8007000Eh
0x18000652f  mov     [rsp+58h+arg_18], esi
0x180006533  mov     [rsp+58h+var_38], 0
0x18000653c  mov     ecx, 130h; Size
0x180006541  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006546  mov     rdi, rax
0x180006549  test    rdi, rdi
0x18000654c  jz      short loc_180006595
0x18000654e  mov     dword ptr [rax+8], 0
0x180006555  lea     rax, ??_7?$CComAggObject@VCVANSettingsPage@@@ATL@@6B@; const ATL::CComAggObject<CVANSettingsPage>::`vftable'
0x18000655c  mov     [rdi], rax
0x18000655f  lea     rcx, [rdi+18h]; this
0x180006563  call    ??0CVANSettingsPage@@QEAA@XZ; CVANSettingsPage::CVANSettingsPage(void)
0x180006568  lea     rax, ??_7?$CComContainedObject@VCVANSettingsPage@@@ATL@@6B?$CXWizardPageBase@VCVANSettingsPage@@$1?CLSID_VANSettingsPage@@3U_GUID@@B$0CJHA@@@@; const ATL::CComContainedObject<CVANSettingsPage>::`vftable'{for `CXWizardPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608>'}
0x18000656f  mov     [rdi+18h], rax
0x180006573  lea     rax, ??_7?$CComContainedObject@VCVANSettingsPage@@@ATL@@6B?$CPropertyPageImpl@VCVANSettingsPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComContainedObject<CVANSettingsPage>::`vftable'{for `WTL::CPropertyPageImpl<CVANSettingsPage,WTL::CPropertyPageWindow>'}
0x18000657a  mov     [rdi+78h], rax
0x18000657e  mov     [rdi+20h], r12
0x180006582  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006589  mov     rax, [rcx]
0x18000658c  mov     rax, [rax+8]
0x180006590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006595  mov     [rsp+58h+var_38], rdi
0x18000659a  jmp     short loc_1800065AF
0x18000659c  mov     r14, [rsp+58h+arg_10]
0x1800065a1  mov     r15, [rsp+58h+arg_8]
0x1800065a6  mov     esi, [rsp+58h+arg_18]
0x1800065aa  mov     rdi, [rsp+58h+var_38]
0x1800065af  test    rdi, rdi
0x1800065b2  jz      short loc_180006604
0x1800065b4  lea     rcx, [rdi+28h]; this
0x1800065b8  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800065bd  xor     ecx, ecx
0x1800065bf  test    eax, eax
0x1800065c1  cmovs   ecx, eax
0x1800065c4  xor     eax, eax
0x1800065c6  test    ecx, ecx
0x1800065c8  cmovs   eax, ecx
0x1800065cb  xor     esi, esi
0x1800065cd  test    eax, eax
0x1800065cf  cmovs   esi, eax
0x1800065d2  test    esi, esi
0x1800065d4  jnz     short loc_1800065F0
0x1800065d6  mov     rax, [rdi]
0x1800065d9  mov     r8, r14
0x1800065dc  mov     rdx, r15
0x1800065df  mov     rcx, rdi
0x1800065e2  mov     rax, [rax]
0x1800065e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ea  mov     esi, eax
0x1800065ec  test    eax, eax
0x1800065ee  jz      short loc_180006604
0x1800065f0  mov     rdx, [rdi]
0x1800065f3  mov     rax, [rdx+18h]
0x1800065f7  mov     edx, 1
0x1800065fc  mov     rcx, rdi
0x1800065ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006604  mov     eax, esi
0x180006606  mov     rbx, [rsp+58h+arg_0]
0x18000660b  add     rsp, 30h
0x18000660f  pop     r15
0x180006611  pop     r14
0x180006613  pop     r12
0x180006615  pop     rdi
0x180006616  pop     rsi
0x180006617  retn
```
