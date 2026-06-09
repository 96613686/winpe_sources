# ATL::CComCreator<ATL::CComAggObject<CInfraProgressPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006160`
- end: `0x180006288`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraProgressPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005970`

## callees

- `0x18000130c`
- `0x180006160`
- `0x1800080a0`
- `0x1800234a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraProgressPage>>::CreateInstance(
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
  v8 = operator new(0x140u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CInfraProgressPage>::`vftable';
    CInfraProgressPage::CInfraProgressPage((CInfraProgressPage *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CInfraProgressPage>::`vftable'{for `CXWizardPageBase<CInfraProgressPage,&_GUID const CLSID_InfraProgressPage,10603>'};
    v9[15] = &CInfraProgressPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraProgressPage,WTL::CPropertyPageWindow>'};
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
0x180006160  mov     [rsp+arg_0], rbx
0x180006165  mov     [rsp+arg_10], r8
0x18000616a  mov     [rsp+arg_8], rdx
0x18000616f  push    rsi
0x180006170  push    rdi
0x180006171  push    r12
0x180006173  push    r14
0x180006175  push    r15
0x180006177  sub     rsp, 30h
0x18000617b  mov     r14, r8
0x18000617e  mov     r15, rdx
0x180006181  mov     r12, rcx
0x180006184  test    r8, r8
0x180006187  jnz     short loc_180006193
0x180006189  mov     eax, 80004003h
0x18000618e  jmp     loc_180006276
0x180006193  mov     qword ptr [r8], 0
0x18000619a  mov     esi, 8007000Eh
0x18000619f  mov     [rsp+58h+arg_18], esi
0x1800061a3  mov     [rsp+58h+var_38], 0
0x1800061ac  mov     ecx, 140h; Size
0x1800061b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061b6  mov     rdi, rax
0x1800061b9  test    rdi, rdi
0x1800061bc  jz      short loc_180006205
0x1800061be  mov     dword ptr [rax+8], 0
0x1800061c5  lea     rax, ??_7?$CComAggObject@VCInfraProgressPage@@@ATL@@6B@; const ATL::CComAggObject<CInfraProgressPage>::`vftable'
0x1800061cc  mov     [rdi], rax
0x1800061cf  lea     rcx, [rdi+18h]; this
0x1800061d3  call    ??0CInfraProgressPage@@QEAA@XZ; CInfraProgressPage::CInfraProgressPage(void)
0x1800061d8  lea     rax, ??_7?$CComContainedObject@VCInfraProgressPage@@@ATL@@6B?$CXWizardPageBase@VCInfraProgressPage@@$1?CLSID_InfraProgressPage@@3U_GUID@@B$0CJGL@@@@; const ATL::CComContainedObject<CInfraProgressPage>::`vftable'{for `CXWizardPageBase<CInfraProgressPage,&_GUID const CLSID_InfraProgressPage,10603>'}
0x1800061df  mov     [rdi+18h], rax
0x1800061e3  lea     rax, ??_7CInfraProgressPage@@6B?$CPropertyPageImpl@VCInfraProgressPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const CInfraProgressPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraProgressPage,WTL::CPropertyPageWindow>'}
0x1800061ea  mov     [rdi+78h], rax
0x1800061ee  mov     [rdi+20h], r12
0x1800061f2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800061f9  mov     rax, [rcx]
0x1800061fc  mov     rax, [rax+8]
0x180006200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006205  mov     [rsp+58h+var_38], rdi
0x18000620a  jmp     short loc_18000621F
0x18000620c  mov     r14, [rsp+58h+arg_10]
0x180006211  mov     r15, [rsp+58h+arg_8]
0x180006216  mov     esi, [rsp+58h+arg_18]
0x18000621a  mov     rdi, [rsp+58h+var_38]
0x18000621f  test    rdi, rdi
0x180006222  jz      short loc_180006274
0x180006224  lea     rcx, [rdi+28h]; this
0x180006228  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000622d  xor     ecx, ecx
0x18000622f  test    eax, eax
0x180006231  cmovs   ecx, eax
0x180006234  xor     eax, eax
0x180006236  test    ecx, ecx
0x180006238  cmovs   eax, ecx
0x18000623b  xor     esi, esi
0x18000623d  test    eax, eax
0x18000623f  cmovs   esi, eax
0x180006242  test    esi, esi
0x180006244  jnz     short loc_180006260
0x180006246  mov     rax, [rdi]
0x180006249  mov     r8, r14
0x18000624c  mov     rdx, r15
0x18000624f  mov     rcx, rdi
0x180006252  mov     rax, [rax]
0x180006255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000625a  mov     esi, eax
0x18000625c  test    eax, eax
0x18000625e  jz      short loc_180006274
0x180006260  mov     rdx, [rdi]
0x180006263  mov     rax, [rdx+18h]
0x180006267  mov     edx, 1
0x18000626c  mov     rcx, rdi
0x18000626f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006274  mov     eax, esi
0x180006276  mov     rbx, [rsp+58h+arg_0]
0x18000627b  add     rsp, 30h
0x18000627f  pop     r15
0x180006281  pop     r14
0x180006283  pop     r12
0x180006285  pop     rdi
0x180006286  pop     rsi
0x180006287  retn
```
