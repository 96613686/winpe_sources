# ATL::CComCreator<ATL::CComObject<CInfraConnectedPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006a74`
- end: `0x180006b71`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraConnectedPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005910`

## callees

- `0x18000130c`
- `0x180002ae8`
- `0x180006a74`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraConnectedPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CInfraConnectedPage *v7; // rax
  CInfraConnectedPage *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CInfraConnectedPage *)operator new(0x140u);
  v8 = v7;
  if ( v7 )
  {
    CInfraConnectedPage::CInfraConnectedPage(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CInfraConnectedPage>::`vftable'{for `CXWizardPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CInfraConnectedPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectedPage,WTL::CPropertyPageWindow>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CInfraConnectedPage *)((char *)v8 + 16));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CInfraConnectedPage *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006a74  mov     [rsp+arg_10], r8
0x180006a79  mov     [rsp+arg_8], rdx
0x180006a7e  mov     [rsp+arg_0], rcx
0x180006a83  push    rbx
0x180006a84  push    rsi
0x180006a85  push    rdi
0x180006a86  push    r14
0x180006a88  sub     rsp, 28h
0x180006a8c  mov     rsi, r8
0x180006a8f  mov     r14, rdx
0x180006a92  test    r8, r8
0x180006a95  jnz     short loc_180006AA1
0x180006a97  mov     eax, 80004003h
0x180006a9c  jmp     loc_180006B67
0x180006aa1  mov     qword ptr [r8], 0
0x180006aa8  mov     edi, 8007000Eh
0x180006aad  mov     dword ptr [rsp+48h+arg_0], edi
0x180006ab1  mov     [rsp+48h+arg_18], 0
0x180006aba  mov     ecx, 140h; Size
0x180006abf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ac4  mov     rbx, rax
0x180006ac7  test    rbx, rbx
0x180006aca  jz      short loc_180006AFC
0x180006acc  mov     rcx, rax; this
0x180006acf  call    ??0CInfraConnectedPage@@QEAA@XZ; CInfraConnectedPage::CInfraConnectedPage(void)
0x180006ad4  lea     rax, ??_7?$CComObject@VCInfraConnectedPage@@@ATL@@6B?$CXWizardPageBase@VCInfraConnectedPage@@$1?CLSID_InfraConnectedPage@@3U_GUID@@B$0CJGM@@@@; const ATL::CComObject<CInfraConnectedPage>::`vftable'{for `CXWizardPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604>'}
0x180006adb  mov     [rbx], rax
0x180006ade  lea     rax, ??_7?$CComObject@VCInfraConnectedPage@@@ATL@@6B?$CPropertyPageImpl@VCInfraConnectedPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CInfraConnectedPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraConnectedPage,WTL::CPropertyPageWindow>'}
0x180006ae5  mov     [rbx+60h], rax
0x180006ae9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006af0  mov     rax, [rcx]
0x180006af3  mov     rax, [rax+8]
0x180006af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afc  mov     [rsp+48h+arg_18], rbx
0x180006b01  jmp     short loc_180006B16
0x180006b03  mov     rsi, [rsp+48h+arg_10]
0x180006b08  mov     r14, [rsp+48h+arg_8]
0x180006b0d  mov     edi, dword ptr [rsp+48h+arg_0]
0x180006b11  mov     rbx, [rsp+48h+arg_18]
0x180006b16  test    rbx, rbx
0x180006b19  jz      short loc_180006B65
0x180006b1b  lea     rcx, [rbx+10h]; this
0x180006b1f  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006b24  xor     ecx, ecx
0x180006b26  test    eax, eax
0x180006b28  cmovs   ecx, eax
0x180006b2b  xor     edi, edi
0x180006b2d  test    ecx, ecx
0x180006b2f  cmovs   edi, ecx
0x180006b32  test    edi, edi
0x180006b34  jnz     short loc_180006B50
0x180006b36  mov     rax, [rbx]
0x180006b39  mov     r8, rsi
0x180006b3c  mov     rdx, r14
0x180006b3f  mov     rcx, rbx
0x180006b42  mov     rax, [rax]
0x180006b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4a  mov     edi, eax
0x180006b4c  test    eax, eax
0x180006b4e  jz      short loc_180006B65
0x180006b50  lea     rcx, [rbx+60h]
0x180006b54  mov     rdx, [rcx]
0x180006b57  mov     rax, [rdx+8]
0x180006b5b  mov     edx, 1
0x180006b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b65  mov     eax, edi
0x180006b67  add     rsp, 28h
0x180006b6b  pop     r14
0x180006b6d  pop     rdi
0x180006b6e  pop     rsi
0x180006b6f  pop     rbx
0x180006b70  retn
```
