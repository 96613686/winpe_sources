# CStatusBarModuleInner::_AppendStaticTextPropertyField(DirectUI::DUIXmlParser *,DirectUI::Element *,IPropertyStoreCache *,IPropertyDescription *)

- ea: `0x18006c484`
- end: `0x18006c6c4`
- name: `?_AppendStaticTextPropertyField@CStatusBarModuleInner@@AEAAJPEAVDUIXmlParser@DirectUI@@PEAVElement@3@PEAUIPropertyStoreCache@@PEAUIPropertyDescription@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(CStatusBarModuleInner *__hidden this, struct DirectUI::DUIXmlParser *, struct DirectUI::Element *, struct IPropertyStoreCache *, struct IPropertyDescription *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027510`

## callees

- `0x18006c484`
- `0x18006c6cc`
- `0x18006ca44`
- `0x180233280`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c546`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c61d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c653`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c65e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c546`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c61d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c653`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c65e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006c68a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006c68a`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006c60d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006c60d`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006c63d`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006c63d`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006c4e0`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006c4e0`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18006c66e`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18006c66e`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006c522`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006c522`
- `DUI70!StrToID` at `0x18006c55b`
- `DUI70!StrToID` at `0x18006c55b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18006c567`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18006c567`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18006c67f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18006c6b8`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18006c67f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18006c6b8`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x18006c648`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x18006c648`

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
0x18006c484  push    rbp
0x18006c486  push    rbx
0x18006c487  push    rsi
0x18006c488  push    rdi
0x18006c489  push    r12
0x18006c48b  push    r14
0x18006c48d  push    r15
0x18006c48f  lea     rbp, [rsp-1Fh]
0x18006c494  sub     rsp, 90h
0x18006c49b  mov     rax, cs:__security_cookie
0x18006c4a2  xor     rax, rsp
0x18006c4a5  mov     [rbp+4Fh+var_40], rax
0x18006c4a9  mov     r15, r9
0x18006c4ac  mov     r12, r8
0x18006c4af  mov     rax, rdx
0x18006c4b2  mov     rdi, [rbp+4Fh+arg_20]
0x18006c4b6  mov     [rbp+4Fh+var_90], 0
0x18006c4be  lea     rdx, [rbp+4Fh+var_90]
0x18006c4c2  mov     [rsp+0C0h+var_98], rdx
0x18006c4c7  mov     [rsp+0C0h+var_A0], 0
0x18006c4d0  mov     r9, rcx
0x18006c4d3  xor     r8d, r8d
0x18006c4d6  lea     rdx, aPropertystatic; "PropertyStaticTextField"
0x18006c4dd  mov     rcx, rax
0x18006c4e0  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18006c4e6  mov     ebx, eax
0x18006c4e8  test    eax, eax
0x18006c4ea  js      loc_18006C690
0x18006c4f0  mov     [rbp+4Fh+pv], 0
0x18006c4f8  mov     rax, [rdi]
0x18006c4fb  mov     rbx, [rax+20h]
0x18006c4ff  xor     ecx, ecx; pv
0x18006c501  call    cs:__imp_CoTaskMemFree
0x18006c507  lea     rdx, [rbp+4Fh+pv]
0x18006c50b  mov     rcx, rdi
0x18006c50e  mov     rax, rbx
0x18006c511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c516  test    eax, eax
0x18006c518  js      short loc_18006C528
0x18006c51a  mov     rdx, [rbp+4Fh+pv]
0x18006c51e  mov     rcx, [rbp+4Fh+var_90]
0x18006c522  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18006c528  mov     r8, rdi; struct IPropertyDescription *
0x18006c52b  mov     rdx, [rbp+4Fh+var_90]; struct DirectUI::Element *
0x18006c52f  call    ?_SetPropertyLabel@CStatusBarModuleInner@@AEAAJPEAVElement@DirectUI@@PEAUIPropertyDescription@@@Z; CStatusBarModuleInner::_SetPropertyLabel(DirectUI::Element *,IPropertyDescription *)
0x18006c534  mov     ebx, eax
0x18006c536  test    eax, eax
0x18006c538  js      loc_18006C6B0
0x18006c53e  mov     rsi, [rbp+4Fh+var_90]
0x18006c542  mov     rcx, [rbp+4Fh+pv]; pv
0x18006c546  call    cs:__imp_CoTaskMemFree
0x18006c54c  test    ebx, ebx
0x18006c54e  js      loc_18006C690
0x18006c554  lea     rcx, aPropertyvalue; "PropertyValue"
0x18006c55b  call    cs:__imp_StrToID
0x18006c561  movzx   edx, ax
0x18006c564  mov     rcx, rsi
0x18006c567  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18006c56d  mov     r14, rax
0x18006c570  xorps   xmm0, xmm0
0x18006c573  xor     eax, eax
0x18006c575  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x18006c579  mov     [rbp+4Fh+var_60], rax
0x18006c57d  xorps   xmm1, xmm1
0x18006c580  movups  [rbp+4Fh+var_58], xmm1
0x18006c584  mov     [rbp+4Fh+var_48], eax
0x18006c587  mov     rcx, [rdi]
0x18006c58a  mov     rax, [rcx+18h]
0x18006c58e  lea     rdx, [rbp+4Fh+var_58]
0x18006c592  mov     rcx, rdi
0x18006c595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c59a  mov     ebx, eax
0x18006c59c  test    eax, eax
0x18006c59e  js      loc_18006C67A
0x18006c5a4  mov     dword ptr [rbp+4Fh+var_88], 0
0x18006c5ab  mov     rax, [r15]
0x18006c5ae  lea     r9, [rbp+4Fh+var_88]
0x18006c5b2  lea     r8, [rbp+4Fh+pvar]
0x18006c5b6  lea     rdx, [rbp+4Fh+var_58]
0x18006c5ba  mov     rcx, r15
0x18006c5bd  mov     rax, [rax+48h]
0x18006c5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5c6  mov     ebx, eax
0x18006c5c8  test    eax, eax
0x18006c5ca  js      loc_18006C67A
0x18006c5d0  mov     [rbp+4Fh+var_78], 0
0x18006c5d8  mov     rax, [rdi]
0x18006c5db  mov     rbx, [rax+0B0h]
0x18006c5e2  xor     ecx, ecx; pv
0x18006c5e4  call    cs:__imp_CoTaskMemFree
0x18006c5ea  lea     r9, [rbp+4Fh+var_78]
0x18006c5ee  xor     r8d, r8d
0x18006c5f1  lea     rdx, [rbp+4Fh+pvar]
0x18006c5f5  mov     rcx, rdi
0x18006c5f8  mov     rax, rbx
0x18006c5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c600  mov     ebx, eax
0x18006c602  test    eax, eax
0x18006c604  js      short loc_18006C613
0x18006c606  mov     rdx, [rbp+4Fh+var_78]
0x18006c60a  mov     rcx, r14
0x18006c60d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18006c613  mov     [rbp+4Fh+var_88], 0
0x18006c61b  xor     ecx, ecx; pv
0x18006c61d  call    cs:__imp_CoTaskMemFree
0x18006c623  lea     r8, [rbp+4Fh+var_88]
0x18006c627  mov     rdx, rdi
0x18006c62a  mov     rcx, r15
0x18006c62d  call    GetPropertyTooltip
0x18006c632  test    eax, eax
0x18006c634  js      short loc_18006C64F
0x18006c636  mov     rdx, [rbp+4Fh+var_88]
0x18006c63a  mov     rcx, r14
0x18006c63d  call    cs:__imp_?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x18006c643  mov     dl, 1
0x18006c645  mov     rcx, r14
0x18006c648  call    cs:__imp_?SetTooltip@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetTooltip(bool)
0x18006c64e  nop
0x18006c64f  mov     rcx, [rbp+4Fh+var_88]; pv
0x18006c653  call    cs:__imp_CoTaskMemFree
0x18006c659  nop
0x18006c65a  mov     rcx, [rbp+4Fh+var_78]; pv
0x18006c65e  call    cs:__imp_CoTaskMemFree
0x18006c664  test    ebx, ebx
0x18006c666  js      short loc_18006C67A
0x18006c668  mov     rdx, rsi
0x18006c66b  mov     rcx, r12
0x18006c66e  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18006c674  mov     ebx, eax
0x18006c676  test    eax, eax
0x18006c678  jns     short loc_18006C686
0x18006c67a  mov     dl, 1
0x18006c67c  mov     rcx, rsi
0x18006c67f  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18006c685  nop
0x18006c686  lea     rcx, [rbp+4Fh+pvar]; pvar
0x18006c68a  call    cs:__imp_PropVariantClear
0x18006c690  mov     eax, ebx
0x18006c692  mov     rcx, [rbp+4Fh+var_40]
0x18006c696  xor     rcx, rsp; StackCookie
0x18006c699  call    __security_check_cookie
0x18006c69e  add     rsp, 90h
0x18006c6a5  pop     r15
0x18006c6a7  pop     r14
0x18006c6a9  pop     r12
0x18006c6ab  pop     rdi
0x18006c6ac  pop     rsi
0x18006c6ad  pop     rbx
0x18006c6ae  pop     rbp
0x18006c6af  retn
0x18006c6b0  xor     esi, esi
0x18006c6b2  mov     dl, 1
0x18006c6b4  mov     rcx, [rbp+4Fh+var_90]
0x18006c6b8  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18006c6be  jmp     loc_18006C542
```
