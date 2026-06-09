# ATL::CComCreator<ATL::CComObject<CInfraProgressPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006d94`
- end: `0x180006e91`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraProgressPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005970`

## callees

- `0x18000130c`
- `0x180006d94`
- `0x1800080a0`
- `0x1800234a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraProgressPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CInfraProgressPage *v7; // rax
  CInfraProgressPage *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CInfraProgressPage *)operator new(0x128u);
  v8 = v7;
  if ( v7 )
  {
    CInfraProgressPage::CInfraProgressPage(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CInfraProgressPage>::`vftable'{for `CXWizardPageBase<CInfraProgressPage,&_GUID const CLSID_InfraProgressPage,10603>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CInfraProgressPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraProgressPage,WTL::CPropertyPageWindow>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CInfraProgressPage *)((char *)v8 + 16));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CInfraProgressPage *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006d94  mov     [rsp+arg_10], r8
0x180006d99  mov     [rsp+arg_8], rdx
0x180006d9e  mov     [rsp+arg_0], rcx
0x180006da3  push    rbx
0x180006da4  push    rsi
0x180006da5  push    rdi
0x180006da6  push    r14
0x180006da8  sub     rsp, 28h
0x180006dac  mov     rsi, r8
0x180006daf  mov     r14, rdx
0x180006db2  test    r8, r8
0x180006db5  jnz     short loc_180006DC1
0x180006db7  mov     eax, 80004003h
0x180006dbc  jmp     loc_180006E87
0x180006dc1  mov     qword ptr [r8], 0
0x180006dc8  mov     edi, 8007000Eh
0x180006dcd  mov     dword ptr [rsp+48h+arg_0], edi
0x180006dd1  mov     [rsp+48h+arg_18], 0
0x180006dda  mov     ecx, 128h; Size
0x180006ddf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006de4  mov     rbx, rax
0x180006de7  test    rbx, rbx
0x180006dea  jz      short loc_180006E1C
0x180006dec  mov     rcx, rax; this
0x180006def  call    ??0CInfraProgressPage@@QEAA@XZ; CInfraProgressPage::CInfraProgressPage(void)
0x180006df4  lea     rax, ??_7?$CComObject@VCInfraProgressPage@@@ATL@@6B?$CXWizardPageBase@VCInfraProgressPage@@$1?CLSID_InfraProgressPage@@3U_GUID@@B$0CJGL@@@@; const ATL::CComObject<CInfraProgressPage>::`vftable'{for `CXWizardPageBase<CInfraProgressPage,&_GUID const CLSID_InfraProgressPage,10603>'}
0x180006dfb  mov     [rbx], rax
0x180006dfe  lea     rax, ??_7?$CComObject@VCInfraProgressPage@@@ATL@@6B?$CPropertyPageImpl@VCInfraProgressPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CInfraProgressPage>::`vftable'{for `WTL::CPropertyPageImpl<CInfraProgressPage,WTL::CPropertyPageWindow>'}
0x180006e05  mov     [rbx+60h], rax
0x180006e09  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006e10  mov     rax, [rcx]
0x180006e13  mov     rax, [rax+8]
0x180006e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e1c  mov     [rsp+48h+arg_18], rbx
0x180006e21  jmp     short loc_180006E36
0x180006e23  mov     rsi, [rsp+48h+arg_10]
0x180006e28  mov     r14, [rsp+48h+arg_8]
0x180006e2d  mov     edi, dword ptr [rsp+48h+arg_0]
0x180006e31  mov     rbx, [rsp+48h+arg_18]
0x180006e36  test    rbx, rbx
0x180006e39  jz      short loc_180006E85
0x180006e3b  lea     rcx, [rbx+10h]; this
0x180006e3f  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006e44  xor     ecx, ecx
0x180006e46  test    eax, eax
0x180006e48  cmovs   ecx, eax
0x180006e4b  xor     edi, edi
0x180006e4d  test    ecx, ecx
0x180006e4f  cmovs   edi, ecx
0x180006e52  test    edi, edi
0x180006e54  jnz     short loc_180006E70
0x180006e56  mov     rax, [rbx]
0x180006e59  mov     r8, rsi
0x180006e5c  mov     rdx, r14
0x180006e5f  mov     rcx, rbx
0x180006e62  mov     rax, [rax]
0x180006e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6a  mov     edi, eax
0x180006e6c  test    eax, eax
0x180006e6e  jz      short loc_180006E85
0x180006e70  lea     rcx, [rbx+60h]
0x180006e74  mov     rdx, [rcx]
0x180006e77  mov     rax, [rdx+8]
0x180006e7b  mov     edx, 1
0x180006e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e85  mov     eax, edi
0x180006e87  add     rsp, 28h
0x180006e8b  pop     r14
0x180006e8d  pop     rdi
0x180006e8e  pop     rsi
0x180006e8f  pop     rbx
0x180006e90  retn
```
