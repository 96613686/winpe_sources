# ATL::CComCreator<ATL::CComObject<CInfraErrorPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006c90`
- end: `0x180006d8d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraErrorPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005950`

## callees

- `0x18000130c`
- `0x180002b8c`
- `0x180006c90`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraErrorPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CInfraErrorPage *v7; // rax
  CInfraErrorPage *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CInfraErrorPage *)operator new(0x108u);
  v8 = v7;
  if ( v7 )
  {
    CInfraErrorPage::CInfraErrorPage(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CInfraErrorPage>::`vftable'{for `CXWizardPageBase<CInfraErrorPage,&_GUID const CLSID_InfraErrorPage,10606>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CInfraErrorPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraErrorPage,WTL::CPropertyPageWindow>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CInfraErrorPage *)((char *)v8 + 16));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CInfraErrorPage *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006c90  mov     [rsp+arg_10], r8
0x180006c95  mov     [rsp+arg_8], rdx
0x180006c9a  mov     [rsp+arg_0], rcx
0x180006c9f  push    rbx
0x180006ca0  push    rsi
0x180006ca1  push    rdi
0x180006ca2  push    r14
0x180006ca4  sub     rsp, 28h
0x180006ca8  mov     rsi, r8
0x180006cab  mov     r14, rdx
0x180006cae  test    r8, r8
0x180006cb1  jnz     short loc_180006CBD
0x180006cb3  mov     eax, 80004003h
0x180006cb8  jmp     loc_180006D83
0x180006cbd  mov     qword ptr [r8], 0
0x180006cc4  mov     edi, 8007000Eh
0x180006cc9  mov     dword ptr [rsp+48h+arg_0], edi
0x180006ccd  mov     [rsp+48h+arg_18], 0
0x180006cd6  mov     ecx, 108h; Size
0x180006cdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ce0  mov     rbx, rax
0x180006ce3  test    rbx, rbx
0x180006ce6  jz      short loc_180006D18
0x180006ce8  mov     rcx, rax; this
0x180006ceb  call    ??0CInfraErrorPage@@QEAA@XZ; CInfraErrorPage::CInfraErrorPage(void)
0x180006cf0  lea     rax, ??_7?$CComObject@VCInfraErrorPage@@@ATL@@6B?$CXWizardPageBase@VCInfraErrorPage@@$1?CLSID_InfraErrorPage@@3U_GUID@@B$0CJGO@@@@; const ATL::CComObject<CInfraErrorPage>::`vftable'{for `CXWizardPageBase<CInfraErrorPage,&_GUID const CLSID_InfraErrorPage,10606>'}
0x180006cf7  mov     [rbx], rax
0x180006cfa  lea     rax, ??_7?$CComObject@VCInfraErrorPage@@@ATL@@6B?$CPropertyPageImpl@VCInfraErrorPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CInfraErrorPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraErrorPage,WTL::CPropertyPageWindow>'}
0x180006d01  mov     [rbx+60h], rax
0x180006d05  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006d0c  mov     rax, [rcx]
0x180006d0f  mov     rax, [rax+8]
0x180006d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d18  mov     [rsp+48h+arg_18], rbx
0x180006d1d  jmp     short loc_180006D32
0x180006d1f  mov     rsi, [rsp+48h+arg_10]
0x180006d24  mov     r14, [rsp+48h+arg_8]
0x180006d29  mov     edi, dword ptr [rsp+48h+arg_0]
0x180006d2d  mov     rbx, [rsp+48h+arg_18]
0x180006d32  test    rbx, rbx
0x180006d35  jz      short loc_180006D81
0x180006d37  lea     rcx, [rbx+10h]; this
0x180006d3b  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006d40  xor     ecx, ecx
0x180006d42  test    eax, eax
0x180006d44  cmovs   ecx, eax
0x180006d47  xor     edi, edi
0x180006d49  test    ecx, ecx
0x180006d4b  cmovs   edi, ecx
0x180006d4e  test    edi, edi
0x180006d50  jnz     short loc_180006D6C
0x180006d52  mov     rax, [rbx]
0x180006d55  mov     r8, rsi
0x180006d58  mov     rdx, r14
0x180006d5b  mov     rcx, rbx
0x180006d5e  mov     rax, [rax]
0x180006d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d66  mov     edi, eax
0x180006d68  test    eax, eax
0x180006d6a  jz      short loc_180006D81
0x180006d6c  lea     rcx, [rbx+60h]
0x180006d70  mov     rdx, [rcx]
0x180006d73  mov     rax, [rdx+8]
0x180006d77  mov     edx, 1
0x180006d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d81  mov     eax, edi
0x180006d83  add     rsp, 28h
0x180006d87  pop     r14
0x180006d89  pop     rdi
0x180006d8a  pop     rsi
0x180006d8b  pop     rbx
0x180006d8c  retn
```
