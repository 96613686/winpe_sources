# ATL::CComCreator<ATL::CComObject<CProfileExistsPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007080`
- end: `0x18000717d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCProfileExistsPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800059e0`

## callees

- `0x18000130c`
- `0x180007080`
- `0x1800080a0`
- `0x180024bdc`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CProfileExistsPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CProfileExistsPage *v7; // rax
  CProfileExistsPage *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CProfileExistsPage *)operator new(0x110u);
  v8 = v7;
  if ( v7 )
  {
    CProfileExistsPage::CProfileExistsPage(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CProfileExistsPage>::`vftable'{for `CXWizardPageBase<CProfileExistsPage,&_GUID const CLSID_ProfileExistsPage,10609>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CProfileExistsPage>::`vftable'{for `WTL::CPropertyPageImpl<CProfileExistsPage,WTL::CPropertyPageWindow>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CProfileExistsPage *)((char *)v8 + 16));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CProfileExistsPage *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180007080  mov     [rsp+arg_10], r8
0x180007085  mov     [rsp+arg_8], rdx
0x18000708a  mov     [rsp+arg_0], rcx
0x18000708f  push    rbx
0x180007090  push    rsi
0x180007091  push    rdi
0x180007092  push    r14
0x180007094  sub     rsp, 28h
0x180007098  mov     rsi, r8
0x18000709b  mov     r14, rdx
0x18000709e  test    r8, r8
0x1800070a1  jnz     short loc_1800070AD
0x1800070a3  mov     eax, 80004003h
0x1800070a8  jmp     loc_180007173
0x1800070ad  mov     qword ptr [r8], 0
0x1800070b4  mov     edi, 8007000Eh
0x1800070b9  mov     dword ptr [rsp+48h+arg_0], edi
0x1800070bd  mov     [rsp+48h+arg_18], 0
0x1800070c6  mov     ecx, 110h; Size
0x1800070cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800070d0  mov     rbx, rax
0x1800070d3  test    rbx, rbx
0x1800070d6  jz      short loc_180007108
0x1800070d8  mov     rcx, rax; this
0x1800070db  call    ??0CProfileExistsPage@@QEAA@XZ; CProfileExistsPage::CProfileExistsPage(void)
0x1800070e0  lea     rax, ??_7?$CComObject@VCProfileExistsPage@@@ATL@@6B?$CXWizardPageBase@VCProfileExistsPage@@$1?CLSID_ProfileExistsPage@@3U_GUID@@B$0CJHB@@@@; const ATL::CComObject<CProfileExistsPage>::`vftable'{for `CXWizardPageBase<CProfileExistsPage,&_GUID const CLSID_ProfileExistsPage,10609>'}
0x1800070e7  mov     [rbx], rax
0x1800070ea  lea     rax, ??_7?$CComObject@VCProfileExistsPage@@@ATL@@6B?$CPropertyPageImpl@VCProfileExistsPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CProfileExistsPage>::`vftable'{for `WTL::CPropertyPageImpl<CProfileExistsPage,WTL::CPropertyPageWindow>'}
0x1800070f1  mov     [rbx+60h], rax
0x1800070f5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800070fc  mov     rax, [rcx]
0x1800070ff  mov     rax, [rax+8]
0x180007103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007108  mov     [rsp+48h+arg_18], rbx
0x18000710d  jmp     short loc_180007122
0x18000710f  mov     rsi, [rsp+48h+arg_10]
0x180007114  mov     r14, [rsp+48h+arg_8]
0x180007119  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000711d  mov     rbx, [rsp+48h+arg_18]
0x180007122  test    rbx, rbx
0x180007125  jz      short loc_180007171
0x180007127  lea     rcx, [rbx+10h]; this
0x18000712b  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180007130  xor     ecx, ecx
0x180007132  test    eax, eax
0x180007134  cmovs   ecx, eax
0x180007137  xor     edi, edi
0x180007139  test    ecx, ecx
0x18000713b  cmovs   edi, ecx
0x18000713e  test    edi, edi
0x180007140  jnz     short loc_18000715C
0x180007142  mov     rax, [rbx]
0x180007145  mov     r8, rsi
0x180007148  mov     rdx, r14
0x18000714b  mov     rcx, rbx
0x18000714e  mov     rax, [rax]
0x180007151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007156  mov     edi, eax
0x180007158  test    eax, eax
0x18000715a  jz      short loc_180007171
0x18000715c  lea     rcx, [rbx+60h]
0x180007160  mov     rdx, [rcx]
0x180007163  mov     rax, [rdx+8]
0x180007167  mov     edx, 1
0x18000716c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007171  mov     eax, edi
0x180007173  add     rsp, 28h
0x180007177  pop     r14
0x180007179  pop     rdi
0x18000717a  pop     rsi
0x18000717b  pop     rbx
0x18000717c  retn
```
