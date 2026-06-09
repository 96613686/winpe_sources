# CThemeCplPage::LayoutInitialized(void)

- ea: `0x180038de0`
- end: `0x180038fe8`
- name: `?LayoutInitialized@CThemeCplPage@@UEAAJXZ`
- size: `520`
- prototype: `__int64 __fastcall(CThemeCplPage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000268c`
- `0x180035714`
- `0x180035ba4`
- `0x180038de0`
- `0x180052ff8`
- `0x180057010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadType` at `0x180038e70`
- `PROPSYS!PSPropertyBag_ReadType` at `0x180038e70`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180038e37`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180038e37`
- `OLEAUT32!__imp_VariantClear` at `0x180038f32`
- `OLEAUT32!__imp_VariantClear` at `0x180038f32`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180038f9b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180038f9b`
- `DUI70!StrToID` at `0x180038f89`
- `DUI70!StrToID` at `0x180038f89`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180038fc0`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180038fc0`

## pseudocode

```c
__int64 __fastcall CThemeCplPage::LayoutInitialized(CThemeCplCore **this)
{
  IUnknown *v2; // rcx
  HRESULT v3; // ebx
  CThemeCplCore *v4; // rax
  CThemeCplCore *v5; // rax
  CThemeCplCore *v6; // r14
  CThemeCplCore *v7; // rcx
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-30h] BYREF
  VARIANT var; // [rsp+38h] [rbp-18h] BYREF
  void *ppvOut; // [rsp+80h] [rbp+30h] BYREF
  CThemeCplCore *v14; // [rsp+88h] [rbp+38h]

  CControlPanelPage::LayoutInitialized((CControlPanelPage *)this);
  if ( this[5] )
    goto LABEL_13;
  v2 = (IUnknown *)*(this - 1);
  ppvOut = 0;
  v3 = IUnknown_QueryService(
         v2,
         (const GUID *const)&SID_PerNamespaceIDPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut);
  if ( v3 >= 0 )
  {
    memset(&var, 0, sizeof(var));
    v3 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"ThemeCplCore", &var, 0xDu);
    if ( v3 < 0 )
    {
      v4 = (CThemeCplCore *)operator new(0x348u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v4;
      if ( v4 && (v5 = CThemeCplCore::CThemeCplCore(v4), (v6 = v5) != 0) )
      {
        v3 = (**(__int64 (__fastcall ***)(CThemeCplCore *, GUID *, char *))v5)(
               v5,
               &GUID_00000000_0000_0000_c000_000000000046,
               (char *)this + 40);
        if ( v3 >= 0 )
        {
          v7 = this[5];
          memset(&pvarg, 0, sizeof(pvarg));
          pvarg.vt = 13;
          v3 = (**(__int64 (__fastcall ***)(CThemeCplCore *, GUID *, ULONG *))v7)(
                 v7,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 (ULONG *)&pvarg.cyVal);
          if ( v3 >= 0 )
          {
            v3 = (*(__int64 (__fastcall **)(void *, const WCHAR *, VARIANTARG *))(*(_QWORD *)ppvOut + 32LL))(
                   ppvOut,
                   L"ThemeCplCore",
                   &pvarg);
            VariantClear(&pvarg);
          }
        }
        (*(void (__fastcall **)(CThemeCplCore *))(*(_QWORD *)v6 + 16LL))(v6);
      }
      else
      {
        v3 = -2147024882;
      }
    }
    else
    {
      this[5] = (CThemeCplCore *)var.llVal;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( v3 >= 0 )
LABEL_13:
      v3 = CThemeCplCore::InitializePage(this[5], (struct CThemeCplPage *)(this - 28));
  }
  this[7] = 0;
  if ( v3 >= 0 )
  {
    v8 = StrToID(L"PageContent");
    Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)(this - 28), v8);
    this[6] = Descendent;
    if ( Descendent )
      DirectUI::Element::AddListener(
        Descendent,
        (struct DirectUI::IElementListener *)((unsigned __int64)(this + 4) & -(__int64)(this != (CThemeCplCore **)224)));
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180038de0  mov     [rsp-28h+arg_10], rbx
0x180038de5  mov     [rsp-28h+arg_18], rsi
0x180038dea  push    rbp
0x180038deb  push    rdi
0x180038dec  push    r13
0x180038dee  push    r14
0x180038df0  push    r15
0x180038df2  mov     rbp, rsp
0x180038df5  sub     rsp, 50h
0x180038df9  mov     rdi, rcx
0x180038dfc  call    ?LayoutInitialized@CControlPanelPage@@UEAAJXZ; CControlPanelPage::LayoutInitialized(void)
0x180038e01  lea     rsi, [rdi-0E0h]
0x180038e08  lea     r15, [rsi+108h]
0x180038e0f  cmp     qword ptr [r15], 0
0x180038e13  jnz     loc_180038F68
0x180038e19  mov     rcx, [rdi-8]; punk
0x180038e1d  lea     r9, [rbp+ppvOut]; ppvOut
0x180038e21  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180038e28  mov     [rbp+ppvOut], 0
0x180038e30  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x180038e37  call    cs:__imp_IUnknown_QueryService
0x180038e3e  nop     dword ptr [rax+rax+00h]
0x180038e43  mov     ebx, eax
0x180038e45  test    eax, eax
0x180038e47  js      loc_180038F76
0x180038e4d  mov     rcx, [rbp+ppvOut]; propBag
0x180038e51  lea     r8, [rbp+var]; var
0x180038e55  xor     eax, eax
0x180038e57  lea     rdx, aThemecplcore; "ThemeCplCore"
0x180038e5e  xorps   xmm0, xmm0
0x180038e61  mov     qword ptr [rbp+var+10h], rax
0x180038e65  movups  xmmword ptr [rbp+var], xmm0
0x180038e69  lea     r13d, [rax+0Dh]
0x180038e6d  mov     r9d, r13d; type
0x180038e70  call    cs:__imp_PSPropertyBag_ReadType
0x180038e77  nop     dword ptr [rax+rax+00h]
0x180038e7c  mov     ebx, eax
0x180038e7e  test    eax, eax
0x180038e80  js      short loc_180038E8F
0x180038e82  mov     rax, qword ptr [rbp+var+8]
0x180038e86  mov     [rdi+28h], rax
0x180038e8a  jmp     loc_180038F54
0x180038e8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038e96  mov     ecx, 348h; unsigned __int64
0x180038e9b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038ea0  mov     [rbp+arg_8], rax
0x180038ea4  test    rax, rax
0x180038ea7  jz      loc_180038F4F
0x180038ead  mov     rcx, rax; this
0x180038eb0  call    ??0CThemeCplCore@@QEAA@XZ; CThemeCplCore::CThemeCplCore(void)
0x180038eb5  mov     r14, rax
0x180038eb8  test    rax, rax
0x180038ebb  jz      loc_180038F4F
0x180038ec1  mov     rcx, [rax]
0x180038ec4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180038ecb  mov     r8, r15
0x180038ece  mov     rax, [rcx]
0x180038ed1  mov     rcx, r14
0x180038ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ed9  mov     ebx, eax
0x180038edb  test    eax, eax
0x180038edd  js      short loc_180038F3E
0x180038edf  mov     rcx, [rdi+28h]
0x180038ee3  lea     r8, [rbp+pvarg+8]
0x180038ee7  xor     eax, eax
0x180038ee9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180038ef0  mov     qword ptr [rbp+pvarg+10h], rax
0x180038ef4  xorps   xmm0, xmm0
0x180038ef7  movups  xmmword ptr [rbp+pvarg], xmm0
0x180038efb  mov     word ptr [rbp+pvarg], r13w
0x180038f00  mov     rax, [rcx]
0x180038f03  mov     rax, [rax]
0x180038f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f0b  mov     ebx, eax
0x180038f0d  test    eax, eax
0x180038f0f  js      short loc_180038F3E
0x180038f11  mov     rcx, [rbp+ppvOut]
0x180038f15  lea     r8, [rbp+pvarg]
0x180038f19  lea     rdx, aThemecplcore; "ThemeCplCore"
0x180038f20  mov     rax, [rcx]
0x180038f23  mov     rax, [rax+20h]
0x180038f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f2c  lea     rcx, [rbp+pvarg]; pvarg
0x180038f30  mov     ebx, eax
0x180038f32  call    cs:__imp_VariantClear
0x180038f39  nop     dword ptr [rax+rax+00h]
0x180038f3e  mov     rax, [r14]
0x180038f41  mov     rcx, r14
0x180038f44  mov     rax, [rax+10h]
0x180038f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f4d  jmp     short loc_180038F54
0x180038f4f  mov     ebx, 8007000Eh
0x180038f54  mov     rcx, [rbp+ppvOut]
0x180038f58  mov     rax, [rcx]
0x180038f5b  mov     rax, [rax+10h]
0x180038f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f64  test    ebx, ebx
0x180038f66  js      short loc_180038F76
0x180038f68  mov     rcx, [rdi+28h]; this
0x180038f6c  mov     rdx, rsi; struct CThemeCplPage *
0x180038f6f  call    ?InitializePage@CThemeCplCore@@QEAAJPEAVCThemeCplPage@@@Z; CThemeCplCore::InitializePage(CThemeCplPage *)
0x180038f74  mov     ebx, eax
0x180038f76  mov     qword ptr [rdi+38h], 0
0x180038f7e  test    ebx, ebx
0x180038f80  js      short loc_180038FCC
0x180038f82  lea     rcx, aPagecontent; "PageContent"
0x180038f89  call    cs:__imp_StrToID
0x180038f90  nop     dword ptr [rax+rax+00h]
0x180038f95  movzx   edx, ax
0x180038f98  mov     rcx, rsi
0x180038f9b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180038fa2  nop     dword ptr [rax+rax+00h]
0x180038fa7  mov     [rdi+30h], rax
0x180038fab  test    rax, rax
0x180038fae  jz      short loc_180038FCC
0x180038fb0  neg     rsi
0x180038fb3  lea     rcx, [rdi+20h]
0x180038fb7  sbb     rdx, rdx
0x180038fba  and     rdx, rcx
0x180038fbd  mov     rcx, rax
0x180038fc0  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180038fc7  nop     dword ptr [rax+rax+00h]
0x180038fcc  lea     r11, [rsp+50h+var_s0]
0x180038fd1  mov     eax, ebx
0x180038fd3  mov     rbx, [r11+40h]
0x180038fd7  mov     rsi, [r11+48h]
0x180038fdb  mov     rsp, r11
0x180038fde  pop     r15
0x180038fe0  pop     r14
0x180038fe2  pop     r13
0x180038fe4  pop     rdi
0x180038fe5  pop     rbp
0x180038fe6  retn
```
