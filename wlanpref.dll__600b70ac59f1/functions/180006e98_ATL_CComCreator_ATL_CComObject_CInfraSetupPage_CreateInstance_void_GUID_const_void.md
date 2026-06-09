# ATL::CComCreator<ATL::CComObject<CInfraSetupPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006e98`
- end: `0x180006f95`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraSetupPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180005990`

## callees

- `0x18000130c`
- `0x180006e98`
- `0x1800080a0`
- `0x180015770`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraSetupPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CInfraSetupPage *v7; // rax
  CInfraSetupPage *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CInfraSetupPage *)operator new(0x120u);
  v8 = v7;
  if ( v7 )
  {
    CInfraSetupPage::CInfraSetupPage(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CInfraSetupPage>::`vftable'{for `CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CInfraSetupPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraSetupPage,WTL::CPropertyPageWindow>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CInfraSetupPage *)((char *)v8 + 16));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CInfraSetupPage *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006e98  mov     [rsp+arg_10], r8
0x180006e9d  mov     [rsp+arg_8], rdx
0x180006ea2  mov     [rsp+arg_0], rcx
0x180006ea7  push    rbx
0x180006ea8  push    rsi
0x180006ea9  push    rdi
0x180006eaa  push    r14
0x180006eac  sub     rsp, 28h
0x180006eb0  mov     rsi, r8
0x180006eb3  mov     r14, rdx
0x180006eb6  test    r8, r8
0x180006eb9  jnz     short loc_180006EC5
0x180006ebb  mov     eax, 80004003h
0x180006ec0  jmp     loc_180006F8B
0x180006ec5  mov     qword ptr [r8], 0
0x180006ecc  mov     edi, 8007000Eh
0x180006ed1  mov     dword ptr [rsp+48h+arg_0], edi
0x180006ed5  mov     [rsp+48h+arg_18], 0
0x180006ede  mov     ecx, 120h; Size
0x180006ee3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ee8  mov     rbx, rax
0x180006eeb  test    rbx, rbx
0x180006eee  jz      short loc_180006F20
0x180006ef0  mov     rcx, rax; this
0x180006ef3  call    ??0CInfraSetupPage@@QEAA@XZ; CInfraSetupPage::CInfraSetupPage(void)
0x180006ef8  lea     rax, ??_7?$CComObject@VCInfraSetupPage@@@ATL@@6B?$CXWizardPageBase@VCInfraSetupPage@@$1?CLSID_InfraSetupPage@@3U_GUID@@B$0CJGK@@@@; const ATL::CComObject<CInfraSetupPage>::`vftable'{for `CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>'}
0x180006eff  mov     [rbx], rax
0x180006f02  lea     rax, ??_7?$CComObject@VCInfraSetupPage@@@ATL@@6B?$CPropertyPageImpl@VCInfraSetupPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CInfraSetupPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraSetupPage,WTL::CPropertyPageWindow>'}
0x180006f09  mov     [rbx+60h], rax
0x180006f0d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006f14  mov     rax, [rcx]
0x180006f17  mov     rax, [rax+8]
0x180006f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f20  mov     [rsp+48h+arg_18], rbx
0x180006f25  jmp     short loc_180006F3A
0x180006f27  mov     rsi, [rsp+48h+arg_10]
0x180006f2c  mov     r14, [rsp+48h+arg_8]
0x180006f31  mov     edi, dword ptr [rsp+48h+arg_0]
0x180006f35  mov     rbx, [rsp+48h+arg_18]
0x180006f3a  test    rbx, rbx
0x180006f3d  jz      short loc_180006F89
0x180006f3f  lea     rcx, [rbx+10h]; this
0x180006f43  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006f48  xor     ecx, ecx
0x180006f4a  test    eax, eax
0x180006f4c  cmovs   ecx, eax
0x180006f4f  xor     edi, edi
0x180006f51  test    ecx, ecx
0x180006f53  cmovs   edi, ecx
0x180006f56  test    edi, edi
0x180006f58  jnz     short loc_180006F74
0x180006f5a  mov     rax, [rbx]
0x180006f5d  mov     r8, rsi
0x180006f60  mov     rdx, r14
0x180006f63  mov     rcx, rbx
0x180006f66  mov     rax, [rax]
0x180006f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f6e  mov     edi, eax
0x180006f70  test    eax, eax
0x180006f72  jz      short loc_180006F89
0x180006f74  lea     rcx, [rbx+60h]
0x180006f78  mov     rdx, [rcx]
0x180006f7b  mov     rax, [rdx+8]
0x180006f7f  mov     edx, 1
0x180006f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f89  mov     eax, edi
0x180006f8b  add     rsp, 28h
0x180006f8f  pop     r14
0x180006f91  pop     rdi
0x180006f92  pop     rsi
0x180006f93  pop     rbx
0x180006f94  retn
```
