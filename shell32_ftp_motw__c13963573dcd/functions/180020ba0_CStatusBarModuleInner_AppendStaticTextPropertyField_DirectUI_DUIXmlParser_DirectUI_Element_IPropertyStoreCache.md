# CStatusBarModuleInner::_AppendStaticTextPropertyField(DirectUI::DUIXmlParser *,DirectUI::Element *,IPropertyStoreCache *,IPropertyDescription *)

- ea: `0x180020ba0`
- end: `0x180020e47`
- name: `?_AppendStaticTextPropertyField@CStatusBarModuleInner@@AEAAJPEAVDUIXmlParser@DirectUI@@PEAVElement@3@PEAUIPropertyStoreCache@@PEAUIPropertyDescription@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(CStatusBarModuleInner *__hidden this, struct DirectUI::DUIXmlParser *, struct DirectUI::Element *, struct IPropertyStoreCache *, struct IPropertyDescription *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180067ffc`

## callees

- `0x180020ba0`
- `0x180020e50`
- `0x180021264`
- `0x180249490`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020db1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020db1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020dc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e00`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e00`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180020d53`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180020d53`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180020d8f`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180020d8f`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180020bfc`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180020bfc`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020dd8`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020dd8`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180020c4a`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180020c4a`
- `DUI70!StrToID` at `0x180020c8f`
- `DUI70!StrToID` at `0x180020c8f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020def`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020e35`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020def`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020e35`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x180020da0`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x180020da0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020ca1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020ca1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CStatusBarModuleInner::_AppendStaticTextPropertyField(
        CStatusBarModuleInner *this,
        struct DirectUI::DUIXmlParser *a2,
        struct DirectUI::Element *a3,
        struct IPropertyStoreCache *a4,
        struct IPropertyDescription *a5)
{
  int v7; // ebx
  HRESULT (__stdcall *GetCanonicalName)(IPropertyDescription *, LPWSTR *); // rbx
  CStatusBarModuleInner *v9; // rcx
  DirectUI::Element *v10; // rsi
  unsigned __int16 v11; // ax
  DirectUI::Element *Descendent; // r14
  HRESULT (__stdcall *FormatForDisplay)(IPropertyDescription *, const PROPVARIANT *const, PROPDESC_FORMAT_FLAGS, LPWSTR *); // rbx
  struct DirectUI::Element *v15; // [rsp+30h] [rbp-41h] BYREF
  LPVOID v16; // [rsp+38h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-31h] BYREF
  LPVOID v18; // [rsp+48h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-21h] BYREF
  __int64 v20; // [rsp+60h] [rbp-11h]
  __int128 v21; // [rsp+68h] [rbp-9h] BYREF
  int v22; // [rsp+78h] [rbp+7h]

  v15 = 0;
  v7 = DirectUI::DUIXmlParser::CreateElement(a2, L"PropertyStaticTextField", 0, this, 0, &v15);
  if ( v7 >= 0 )
  {
    pv = 0;
    GetCanonicalName = a5->lpVtbl->GetCanonicalName;
    CoTaskMemFree(0);
    if ( ((int (__fastcall *)(struct IPropertyDescription *, LPVOID *))GetCanonicalName)(a5, &pv) >= 0 )
      DirectUI::Element::SetID(v15, (const unsigned __int16 *)pv);
    v7 = CStatusBarModuleInner::_SetPropertyLabel(v9, v15, a5);
    if ( v7 < 0 )
    {
      v10 = 0;
      DirectUI::Element::Destroy(v15, 1);
    }
    else
    {
      v10 = v15;
    }
    CoTaskMemFree(pv);
    if ( v7 >= 0 )
    {
      v11 = StrToID(L"PropertyValue");
      Descendent = DirectUI::Element::FindDescendent(v10, v11);
      *(_OWORD *)pvar = 0;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      v7 = ((__int64 (__fastcall *)(struct IPropertyDescription *, __int128 *))a5->lpVtbl->GetPropertyKey)(a5, &v21);
      if ( v7 < 0 )
        goto LABEL_15;
      LODWORD(v16) = 0;
      v7 = ((__int64 (__fastcall *)(struct IPropertyStoreCache *, __int128 *, PROPVARIANT *, LPVOID *))a4->lpVtbl->GetValueAndState)(
             a4,
             &v21,
             pvar,
             &v16);
      if ( v7 < 0 )
        goto LABEL_15;
      v18 = 0;
      FormatForDisplay = a5->lpVtbl->FormatForDisplay;
      CoTaskMemFree(0);
      v7 = ((__int64 (__fastcall *)(struct IPropertyDescription *, PROPVARIANT *, _QWORD, LPVOID *))FormatForDisplay)(
             a5,
             pvar,
             0,
             &v18);
      if ( v7 >= 0 )
        DirectUI::Element::SetContentString(Descendent, (const unsigned __int16 *)v18);
      v16 = 0;
      CoTaskMemFree(0);
      if ( (int)GetPropertyTooltip(a4, a5, &v16) >= 0 )
      {
        DirectUI::Element::SetAccDesc(Descendent, (const unsigned __int16 *)v16);
        DirectUI::Element::SetTooltip(Descendent, 1);
      }
      CoTaskMemFree(v16);
      CoTaskMemFree(v18);
      if ( v7 < 0 || (v7 = DirectUI::Element::Add(a3, v10), v7 < 0) )
LABEL_15:
        DirectUI::Element::Destroy(v10, 1);
      PropVariantClear(pvar);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180020ba0  push    rbp
0x180020ba2  push    rbx
0x180020ba3  push    rsi
0x180020ba4  push    rdi
0x180020ba5  push    r12
0x180020ba7  push    r14
0x180020ba9  push    r15
0x180020bab  lea     rbp, [rsp-1Fh]
0x180020bb0  sub     rsp, 90h
0x180020bb7  mov     rax, cs:__security_cookie
0x180020bbe  xor     rax, rsp
0x180020bc1  mov     [rbp+4Fh+var_40], rax
0x180020bc5  mov     r15, r9
0x180020bc8  mov     r12, r8
0x180020bcb  mov     rax, rdx
0x180020bce  mov     rdi, [rbp+4Fh+arg_20]
0x180020bd2  mov     [rbp+4Fh+var_90], 0
0x180020bda  lea     rdx, [rbp+4Fh+var_90]
0x180020bde  mov     [rsp+0C0h+var_98], rdx
0x180020be3  mov     [rsp+0C0h+var_A0], 0
0x180020bec  mov     r9, rcx
0x180020bef  xor     r8d, r8d
0x180020bf2  lea     rdx, aPropertystatic; "PropertyStaticTextField"
0x180020bf9  mov     rcx, rax
0x180020bfc  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180020c03  nop     dword ptr [rax+rax+00h]
0x180020c08  mov     ebx, eax
0x180020c0a  test    eax, eax
0x180020c0c  js      loc_180020E0C
0x180020c12  mov     [rbp+4Fh+pv], 0
0x180020c1a  mov     rax, [rdi]
0x180020c1d  mov     rbx, [rax+20h]
0x180020c21  xor     ecx, ecx; pv
0x180020c23  call    cs:__imp_CoTaskMemFree
0x180020c2a  nop     dword ptr [rax+rax+00h]
0x180020c2f  lea     rdx, [rbp+4Fh+pv]
0x180020c33  mov     rcx, rdi
0x180020c36  mov     rax, rbx
0x180020c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c3e  test    eax, eax
0x180020c40  js      short loc_180020C56
0x180020c42  mov     rdx, [rbp+4Fh+pv]
0x180020c46  mov     rcx, [rbp+4Fh+var_90]
0x180020c4a  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x180020c51  nop     dword ptr [rax+rax+00h]
0x180020c56  mov     r8, rdi; struct IPropertyDescription *
0x180020c59  mov     rdx, [rbp+4Fh+var_90]; struct DirectUI::Element *
0x180020c5d  call    ?_SetPropertyLabel@CStatusBarModuleInner@@AEAAJPEAVElement@DirectUI@@PEAUIPropertyDescription@@@Z; CStatusBarModuleInner::_SetPropertyLabel(DirectUI::Element *,IPropertyDescription *)
0x180020c62  mov     ebx, eax
0x180020c64  test    eax, eax
0x180020c66  js      loc_180020E2D
0x180020c6c  mov     rsi, [rbp+4Fh+var_90]
0x180020c70  mov     rcx, [rbp+4Fh+pv]; pv
0x180020c74  call    cs:__imp_CoTaskMemFree
0x180020c7b  nop     dword ptr [rax+rax+00h]
0x180020c80  test    ebx, ebx
0x180020c82  js      loc_180020E0C
0x180020c88  lea     rcx, aPropertyvalue; "PropertyValue"
0x180020c8f  call    cs:__imp_StrToID
0x180020c96  nop     dword ptr [rax+rax+00h]
0x180020c9b  movzx   edx, ax
0x180020c9e  mov     rcx, rsi
0x180020ca1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180020ca8  nop     dword ptr [rax+rax+00h]
0x180020cad  mov     r14, rax
0x180020cb0  xorps   xmm0, xmm0
0x180020cb3  xor     eax, eax
0x180020cb5  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180020cb9  mov     [rbp+4Fh+var_60], rax
0x180020cbd  xorps   xmm1, xmm1
0x180020cc0  movups  [rbp+4Fh+var_58], xmm1
0x180020cc4  mov     [rbp+4Fh+var_48], eax
0x180020cc7  mov     rcx, [rdi]
0x180020cca  mov     rax, [rcx+18h]
0x180020cce  lea     rdx, [rbp+4Fh+var_58]
0x180020cd2  mov     rcx, rdi
0x180020cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cda  mov     ebx, eax
0x180020cdc  test    eax, eax
0x180020cde  js      loc_180020DEA
0x180020ce4  mov     dword ptr [rbp+4Fh+var_88], 0
0x180020ceb  mov     rax, [r15]
0x180020cee  lea     r9, [rbp+4Fh+var_88]
0x180020cf2  lea     r8, [rbp+4Fh+pvar]
0x180020cf6  lea     rdx, [rbp+4Fh+var_58]
0x180020cfa  mov     rcx, r15
0x180020cfd  mov     rax, [rax+48h]
0x180020d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d06  mov     ebx, eax
0x180020d08  test    eax, eax
0x180020d0a  js      loc_180020DEA
0x180020d10  mov     [rbp+4Fh+var_78], 0
0x180020d18  mov     rax, [rdi]
0x180020d1b  mov     rbx, [rax+0B0h]
0x180020d22  xor     ecx, ecx; pv
0x180020d24  call    cs:__imp_CoTaskMemFree
0x180020d2b  nop     dword ptr [rax+rax+00h]
0x180020d30  lea     r9, [rbp+4Fh+var_78]
0x180020d34  xor     r8d, r8d
0x180020d37  lea     rdx, [rbp+4Fh+pvar]
0x180020d3b  mov     rcx, rdi
0x180020d3e  mov     rax, rbx
0x180020d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d46  mov     ebx, eax
0x180020d48  test    eax, eax
0x180020d4a  js      short loc_180020D5F
0x180020d4c  mov     rdx, [rbp+4Fh+var_78]
0x180020d50  mov     rcx, r14
0x180020d53  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180020d5a  nop     dword ptr [rax+rax+00h]
0x180020d5f  mov     [rbp+4Fh+var_88], 0
0x180020d67  xor     ecx, ecx; pv
0x180020d69  call    cs:__imp_CoTaskMemFree
0x180020d70  nop     dword ptr [rax+rax+00h]
0x180020d75  lea     r8, [rbp+4Fh+var_88]
0x180020d79  mov     rdx, rdi
0x180020d7c  mov     rcx, r15
0x180020d7f  call    GetPropertyTooltip
0x180020d84  test    eax, eax
0x180020d86  js      short loc_180020DAD
0x180020d88  mov     rdx, [rbp+4Fh+var_88]
0x180020d8c  mov     rcx, r14
0x180020d8f  call    cs:__imp_?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x180020d96  nop     dword ptr [rax+rax+00h]
0x180020d9b  mov     dl, 1
0x180020d9d  mov     rcx, r14
0x180020da0  call    cs:__imp_?SetTooltip@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetTooltip(bool)
0x180020da7  nop     dword ptr [rax+rax+00h]
0x180020dac  nop
0x180020dad  mov     rcx, [rbp+4Fh+var_88]; pv
0x180020db1  call    cs:__imp_CoTaskMemFree
0x180020db8  nop     dword ptr [rax+rax+00h]
0x180020dbd  nop
0x180020dbe  mov     rcx, [rbp+4Fh+var_78]; pv
0x180020dc2  call    cs:__imp_CoTaskMemFree
0x180020dc9  nop     dword ptr [rax+rax+00h]
0x180020dce  test    ebx, ebx
0x180020dd0  js      short loc_180020DEA
0x180020dd2  mov     rdx, rsi
0x180020dd5  mov     rcx, r12
0x180020dd8  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180020ddf  nop     dword ptr [rax+rax+00h]
0x180020de4  mov     ebx, eax
0x180020de6  test    eax, eax
0x180020de8  jns     short loc_180020DFC
0x180020dea  mov     dl, 1
0x180020dec  mov     rcx, rsi
0x180020def  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180020df6  nop     dword ptr [rax+rax+00h]
0x180020dfb  nop
0x180020dfc  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180020e00  call    cs:__imp_PropVariantClear
0x180020e07  nop     dword ptr [rax+rax+00h]
0x180020e0c  mov     eax, ebx
0x180020e0e  mov     rcx, [rbp+4Fh+var_40]
0x180020e12  xor     rcx, rsp; StackCookie
0x180020e15  call    __security_check_cookie
0x180020e1a  add     rsp, 90h
0x180020e21  pop     r15
0x180020e23  pop     r14
0x180020e25  pop     r12
0x180020e27  pop     rdi
0x180020e28  pop     rsi
0x180020e29  pop     rbx
0x180020e2a  pop     rbp
0x180020e2b  retn
0x180020e2d  xor     esi, esi
0x180020e2f  mov     dl, 1
0x180020e31  mov     rcx, [rbp+4Fh+var_90]
0x180020e35  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180020e3c  nop     dword ptr [rax+rax+00h]
0x180020e41  jmp     loc_180020C70
```
