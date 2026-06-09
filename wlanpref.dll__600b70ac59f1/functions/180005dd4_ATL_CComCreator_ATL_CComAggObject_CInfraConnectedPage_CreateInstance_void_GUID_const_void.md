# ATL::CComCreator<ATL::CComAggObject<CInfraConnectedPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005dd4`
- end: `0x180005efc`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCInfraConnectedPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005910`

## callees

- `0x18000130c`
- `0x180002ae8`
- `0x180005dd4`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CInfraConnectedPage>>::CreateInstance(
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
  v8 = operator new(0x158u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CInfraConnectedPage>::`vftable';
    CInfraConnectedPage::CInfraConnectedPage((CInfraConnectedPage *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CInfraConnectedPage>::`vftable'{for `CXWizardPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604>'};
    v9[15] = &CInfraConnectedPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectedPage,WTL::CPropertyPageWindow>'};
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
0x180005dd4  mov     [rsp+arg_0], rbx
0x180005dd9  mov     [rsp+arg_10], r8
0x180005dde  mov     [rsp+arg_8], rdx
0x180005de3  push    rsi
0x180005de4  push    rdi
0x180005de5  push    r12
0x180005de7  push    r14
0x180005de9  push    r15
0x180005deb  sub     rsp, 30h
0x180005def  mov     r14, r8
0x180005df2  mov     r15, rdx
0x180005df5  mov     r12, rcx
0x180005df8  test    r8, r8
0x180005dfb  jnz     short loc_180005E07
0x180005dfd  mov     eax, 80004003h
0x180005e02  jmp     loc_180005EEA
0x180005e07  mov     qword ptr [r8], 0
0x180005e0e  mov     esi, 8007000Eh
0x180005e13  mov     [rsp+58h+arg_18], esi
0x180005e17  mov     [rsp+58h+var_38], 0
0x180005e20  mov     ecx, 158h; Size
0x180005e25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e2a  mov     rdi, rax
0x180005e2d  test    rdi, rdi
0x180005e30  jz      short loc_180005E79
0x180005e32  mov     dword ptr [rax+8], 0
0x180005e39  lea     rax, ??_7?$CComAggObject@VCInfraConnectedPage@@@ATL@@6B@; const ATL::CComAggObject<CInfraConnectedPage>::`vftable'
0x180005e40  mov     [rdi], rax
0x180005e43  lea     rcx, [rdi+18h]; this
0x180005e47  call    ??0CInfraConnectedPage@@QEAA@XZ; CInfraConnectedPage::CInfraConnectedPage(void)
0x180005e4c  lea     rax, ??_7?$CComContainedObject@VCInfraConnectedPage@@@ATL@@6B?$CXWizardPageBase@VCInfraConnectedPage@@$1?CLSID_InfraConnectedPage@@3U_GUID@@B$0CJGM@@@@; const ATL::CComContainedObject<CInfraConnectedPage>::`vftable'{for `CXWizardPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604>'}
0x180005e53  mov     [rdi+18h], rax
0x180005e57  lea     rax, ??_7CInfraConnectedPage@@6B?$CPropertyPageImpl@VCInfraConnectedPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const CInfraConnectedPage::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectedPage,WTL::CPropertyPageWindow>'}
0x180005e5e  mov     [rdi+78h], rax
0x180005e62  mov     [rdi+20h], r12
0x180005e66  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005e6d  mov     rax, [rcx]
0x180005e70  mov     rax, [rax+8]
0x180005e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e79  mov     [rsp+58h+var_38], rdi
0x180005e7e  jmp     short loc_180005E93
0x180005e80  mov     r14, [rsp+58h+arg_10]
0x180005e85  mov     r15, [rsp+58h+arg_8]
0x180005e8a  mov     esi, [rsp+58h+arg_18]
0x180005e8e  mov     rdi, [rsp+58h+var_38]
0x180005e93  test    rdi, rdi
0x180005e96  jz      short loc_180005EE8
0x180005e98  lea     rcx, [rdi+28h]; this
0x180005e9c  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005ea1  xor     ecx, ecx
0x180005ea3  test    eax, eax
0x180005ea5  cmovs   ecx, eax
0x180005ea8  xor     eax, eax
0x180005eaa  test    ecx, ecx
0x180005eac  cmovs   eax, ecx
0x180005eaf  xor     esi, esi
0x180005eb1  test    eax, eax
0x180005eb3  cmovs   esi, eax
0x180005eb6  test    esi, esi
0x180005eb8  jnz     short loc_180005ED4
0x180005eba  mov     rax, [rdi]
0x180005ebd  mov     r8, r14
0x180005ec0  mov     rdx, r15
0x180005ec3  mov     rcx, rdi
0x180005ec6  mov     rax, [rax]
0x180005ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ece  mov     esi, eax
0x180005ed0  test    eax, eax
0x180005ed2  jz      short loc_180005EE8
0x180005ed4  mov     rdx, [rdi]
0x180005ed7  mov     rax, [rdx+18h]
0x180005edb  mov     edx, 1
0x180005ee0  mov     rcx, rdi
0x180005ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee8  mov     eax, esi
0x180005eea  mov     rbx, [rsp+58h+arg_0]
0x180005eef  add     rsp, 30h
0x180005ef3  pop     r15
0x180005ef5  pop     r14
0x180005ef7  pop     r12
0x180005ef9  pop     rdi
0x180005efa  pop     rsi
0x180005efb  retn
```
