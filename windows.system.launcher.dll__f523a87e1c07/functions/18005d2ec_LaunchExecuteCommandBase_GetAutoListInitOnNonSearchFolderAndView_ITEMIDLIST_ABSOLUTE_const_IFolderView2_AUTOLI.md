# LaunchExecuteCommandBase::GetAutoListInitOnNonSearchFolderAndView(_ITEMIDLIST_ABSOLUTE const *,IFolderView2 *,AUTOLISTINIT *)

- ea: `0x18005d2ec`
- end: `0x18005d6b2`
- name: `?GetAutoListInitOnNonSearchFolderAndView@LaunchExecuteCommandBase@@IEAAXPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIFolderView2@@PEAUAUTOLISTINIT@@@Z`
- size: `966`
- prototype: `void(LaunchExecuteCommandBase *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct IFolderView2 *, struct AUTOLISTINIT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004c6b0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18004966c`
- `0x18005d2ec`
- `0x18005d6b8`
- `0x18005d71c`
- `0x18005d85c`
- `0x18005dd0c`
- `0x18005dfe4`
- `0x18005e060`
- `0x18005e0ec`
- `0x18005e1c4`
- `0x18005e370`
- `0x18005e414`
- `0x180111010`

## import_xrefs

- `Windows.Storage!ILFindLastID` at `0x18005d4cf`
- `Windows.Storage!ILFindLastID` at `0x18005d4cf`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18005d332`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18005d332`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_InsertPtr` at `0x18005d5e1`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_InsertPtr` at `0x18005d5e1`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_Create` at `0x18005d556`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_Create` at `0x18005d556`

## string_xrefs

- `0x18005d343`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d3a0`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d408`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d440`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d466`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d497`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d4f0`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d57b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d61a`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d62f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`
- `0x18005d65d`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\launchexecutecommand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall LaunchExecuteCommandBase::GetAutoListInitOnNonSearchFolderAndView(
        LaunchExecuteCommandBase *this,
        const ITEMIDLIST *a2,
        struct IFolderView2 *a3,
        struct AUTOLISTINIT *a4)
{
  HRESULT v7; // eax
  void *v8; // rdi
  __int64 (__fastcall *v9)(void *, _QWORD, const GUID *, GUID *); // rbx
  int v10; // eax
  unsigned int v11; // ecx
  int SearchOptionValue; // eax
  __int64 v13; // rdx
  int ScopeForSearch; // eax
  unsigned int v15; // edx
  int SearchFolderName; // eax
  const struct _GUID *v17; // rdx
  int v18; // eax
  int v19; // r8d
  int v20; // eax
  const struct _ITEMID_CHILD *ID; // rax
  int v22; // eax
  __int64 v23; // rcx
  void *v24; // rcx
  struct ICondition ***v25; // rbx
  const char *v26; // r9
  enum tagCONDITION_TYPE v27; // ecx
  __int64 i; // r15
  struct IFilterCondition *v29; // rsi
  __int64 (__fastcall *v30)(struct IFilterCondition *, void **); // rdi
  int v31; // eax
  void *v32; // r8
  int v33; // eax
  int v34; // [rsp+20h] [rbp-50h]
  int v35; // [rsp+20h] [rbp-50h]
  int v36; // [rsp+20h] [rbp-50h]
  void *ppv; // [rsp+30h] [rbp-40h] BYREF
  int v38[2]; // [rsp+38h] [rbp-38h] BYREF
  void *p; // [rsp+40h] [rbp-30h] BYREF
  struct IFilterCondition **pv; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v41[3]; // [rsp+50h] [rbp-20h] BYREF
  char v42; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  LaunchExecuteCommandBase *cItemGrow; // [rsp+A0h] [rbp+30h] BYREF

  cItemGrow = this;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v7 = SHCreateItemFromIDList(a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)v7,
      v34);
  *(_QWORD *)v38 = 0;
  v8 = ppv;
  v9 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)ppv + 24LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v38);
  v10 = v9(v8, 0, &BHID_SFObject, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)v10,
      (int)v38);
  *((_DWORD *)a4 + 8) = 0;
  *((_OWORD *)a4 + 1) = FOLDERTYPEID_DataAccessAPIs;
  if ( !(unsigned int)IsAdvancedQuerySyntaxLocation(*(_QWORD *)v38) )
    *((_DWORD *)a4 + 8) |= 0x20u;
  SearchOptionValue = GetSearchOptionValue(v11);
  ScopeForSearch = GetScopeForSearch(ppv, v13, (unsigned int)(SearchOptionValue != 0) + 128, (char *)a4 + 128);
  if ( ScopeForSearch < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)ScopeForSearch,
      (int)v38);
  SearchFolderName = GetSearchFolderName(&_ImageBase, v15, *((struct IScope **)a4 + 16), 0, (unsigned __int16 **)a4 + 1);
  if ( SearchFolderName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)SearchFolderName,
      v35);
  v18 = SHCreateSingleKindList((const unsigned __int16 *)retaddr, v17, (void **)a4 + 15);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)v18,
      v35);
  if ( !a3 )
    goto LABEL_36;
  v20 = ApplyViewInfoToAUTOLISTINIT(a4, a3, v19);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)v20,
      v35);
  pv = 0;
  LODWORD(cItemGrow) = 0;
  v41[1] = &pv;
  v41[2] = &cItemGrow;
  v42 = 1;
  ID = (const struct _ITEMID_CHILD *)ILFindLastID(a2);
  v22 = SHGetFiltersFromIDList(ID, &pv, (unsigned int *)&cItemGrow);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
      (const char *)(unsigned int)v22,
      v35);
  if ( (_DWORD)cItemGrow )
  {
    v25 = (struct ICondition ***)DPA_Create((int)cItemGrow);
    v41[0] = v25;
    v26 = v25 == 0 ? (const char *)0x8007000ELL : 0LL;
    v27 = (int)retaddr;
    if ( !v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
        v26,
        v35);
    for ( i = 0; (unsigned int)i < (unsigned int)cItemGrow; i = (unsigned int)(i + 1) )
    {
      p = 0;
      v29 = pv[i];
      v30 = *(__int64 (__fastcall **)(struct IFilterCondition *, void **))(*(_QWORD *)v29 + 88LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&p);
      v31 = v30(v29, &p);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
          (const char *)(unsigned int)v31,
          v35);
      v32 = p;
      p = 0;
      if ( DPA_InsertPtr((HDPA)v25, 0x7FFFFFFF, v32) == -1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
          (const char *)0x8007000ELL,
          v35);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&p);
    }
    v33 = SHCombineMultipleConditions(v27, v25[1], *(_DWORD *)v25, (const struct _GUID *)v26, (void **)a4 + 18);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\launchexecutecommand.cpp",
        (const char *)(unsigned int)v33,
        v36);
    CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::~CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>(v41);
    FreeFilterArray(pv, (unsigned int)cItemGrow);
LABEL_36:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    return;
  }
  FreeFilterArray(pv, 0);
  v23 = *(_QWORD *)v38;
  if ( *(_QWORD *)v38 )
  {
    *(_QWORD *)v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
  }
}

```

## disassembly

```asm
0x18005d2ec  mov     [rsp-28h+arg_8], rbx
0x18005d2f1  mov     [rsp-28h+arg_10], rsi
0x18005d2f6  mov     [rsp-28h+cItemGrow], rcx
0x18005d2fb  push    rbp
0x18005d2fc  push    rdi
0x18005d2fd  push    r13
0x18005d2ff  push    r14
0x18005d301  push    r15
0x18005d303  mov     rbp, rsp
0x18005d306  sub     rsp, 70h
0x18005d30a  mov     r14, r9
0x18005d30d  mov     rsi, r8
0x18005d310  mov     r15, rdx
0x18005d313  mov     [rbp+ppv], 0
0x18005d31b  lea     rcx, [rbp+ppv]
0x18005d31f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d324  lea     r8, [rbp+ppv]; ppv
0x18005d328  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18005d32f  mov     rcx, r15; pidl
0x18005d332  call    cs:__imp_SHCreateItemFromIDList
0x18005d338  mov     rcx, [rbp+28h]; this
0x18005d33c  test    eax, eax
0x18005d33e  jns     short loc_18005D355
0x18005d340  mov     r9d, eax; char *
0x18005d343  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d34a  mov     edx, 0C0h; void *
0x18005d34f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d355  mov     qword ptr [rbp+var_38], 0
0x18005d35d  mov     rdi, [rbp+ppv]
0x18005d361  mov     rax, [rdi]
0x18005d364  mov     rbx, [rax+18h]
0x18005d368  lea     rcx, [rbp+var_38]
0x18005d36c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005d371  lea     rax, [rbp+var_38]
0x18005d375  mov     qword ptr [rsp+70h+var_50], rax; int
0x18005d37a  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18005d381  lea     r8, BHID_SFObject
0x18005d388  xor     edx, edx
0x18005d38a  mov     rcx, rdi
0x18005d38d  mov     rax, rbx
0x18005d390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d395  mov     rcx, [rbp+28h]; this
0x18005d399  test    eax, eax
0x18005d39b  jns     short loc_18005D3B2
0x18005d39d  mov     r9d, eax; char *
0x18005d3a0  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d3a7  mov     edx, 0C3h; void *
0x18005d3ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d3b2  mov     dword ptr [r14+20h], 0
0x18005d3ba  movups  xmm0, cs:FOLDERTYPEID_DataAccessAPIs
0x18005d3c1  movdqu  xmmword ptr [r14+10h], xmm0
0x18005d3c7  mov     rcx, qword ptr [rbp+var_38]
0x18005d3cb  call    IsAdvancedQuerySyntaxLocation
0x18005d3d0  test    eax, eax
0x18005d3d2  jnz     short loc_18005D3D9
0x18005d3d4  or      dword ptr [r14+20h], 20h
0x18005d3d9  call    ?GetSearchOptionValue@@YAHK@Z; GetSearchOptionValue(ulong)
0x18005d3de  neg     eax
0x18005d3e0  sbb     r8d, r8d
0x18005d3e3  neg     r8d
0x18005d3e6  sub     r8d, 0FFFFFF80h
0x18005d3ea  lea     rbx, [r14+80h]
0x18005d3f1  mov     r9, rbx
0x18005d3f4  mov     rcx, [rbp+ppv]
0x18005d3f8  call    ?GetScopeForSearch@@YAJPEAUIShellItem@@W4SCOPE_ITEM_DEPTH@@W4SCOPE_ITEM_FLAGS@@PEAPEAUIScope@@@Z; GetScopeForSearch(IShellItem *,SCOPE_ITEM_DEPTH,SCOPE_ITEM_FLAGS,IScope * *)
0x18005d3fd  mov     rcx, [rbp+28h]; this
0x18005d401  test    eax, eax
0x18005d403  jns     short loc_18005D41A
0x18005d405  mov     r9d, eax; char *
0x18005d408  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d40f  mov     edx, 0CDh; void *
0x18005d414  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d41a  lea     rax, [r14+8]
0x18005d41e  mov     qword ptr [rsp+70h+var_50], rax; int
0x18005d423  xor     r9d, r9d; struct IShellItemArray *
0x18005d426  mov     r8, [rbx]; struct IScope *
0x18005d429  lea     rcx, __ImageBase; hInstance
0x18005d430  call    ?GetSearchFolderName@@YAJPEAUHINSTANCE__@@IPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetSearchFolderName(HINSTANCE__ *,uint,IScope *,IShellItemArray *,ushort * *)
0x18005d435  mov     rcx, [rbp+28h]; unsigned __int16 *
0x18005d439  test    eax, eax
0x18005d43b  jns     short loc_18005D452
0x18005d43d  mov     r9d, eax; char *
0x18005d440  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d447  mov     edx, 0CEh; void *
0x18005d44c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d452  lea     r8, [r14+78h]; void **
0x18005d456  call    ?SHCreateSingleKindList@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; SHCreateSingleKindList(ushort const *,_GUID const &,void * *)
0x18005d45b  mov     rcx, [rbp+28h]; this
0x18005d45f  test    eax, eax
0x18005d461  jns     short loc_18005D478
0x18005d463  mov     r9d, eax; char *
0x18005d466  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d46d  mov     edx, 0CFh; void *
0x18005d472  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d478  test    rsi, rsi
0x18005d47b  jz      loc_18005D686
0x18005d481  mov     rdx, rsi; struct IFolderView2 *
0x18005d484  mov     rcx, r14; struct AUTOLISTINIT *
0x18005d487  call    ?ApplyViewInfoToAUTOLISTINIT@@YAJPEAUAUTOLISTINIT@@PEAUIFolderView2@@H@Z; ApplyViewInfoToAUTOLISTINIT(AUTOLISTINIT *,IFolderView2 *,int)
0x18005d48c  mov     rcx, [rbp+28h]; this
0x18005d490  test    eax, eax
0x18005d492  jns     short loc_18005D4A9
0x18005d494  mov     r9d, eax; char *
0x18005d497  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d49e  mov     edx, 0D3h; void *
0x18005d4a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d4a9  mov     [rbp+pv], 0
0x18005d4b1  mov     dword ptr [rbp+cItemGrow], 0
0x18005d4b8  lea     rax, [rbp+pv]
0x18005d4bc  mov     [rbp+var_18], rax
0x18005d4c0  lea     rax, [rbp+cItemGrow]
0x18005d4c4  mov     [rbp+var_10], rax
0x18005d4c8  mov     [rbp+var_8], 1
0x18005d4cc  mov     rcx, r15; pidl
0x18005d4cf  call    cs:__imp_ILFindLastID
0x18005d4d5  mov     rcx, rax; struct _ITEMID_CHILD *
0x18005d4d8  lea     r8, [rbp+cItemGrow]; unsigned int *
0x18005d4dc  lea     rdx, [rbp+pv]; struct IFilterCondition ***
0x18005d4e0  call    ?SHGetFiltersFromIDList@@YAJPEFBU_ITEMID_CHILD@@PEAPEAPEAUIFilterCondition@@PEAI@Z; SHGetFiltersFromIDList(_ITEMID_CHILD const *,IFilterCondition * * *,uint *)
0x18005d4e5  mov     rcx, [rbp+28h]; this
0x18005d4e9  test    eax, eax
0x18005d4eb  jns     short loc_18005D502
0x18005d4ed  mov     r9d, eax; char *
0x18005d4f0  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d4f7  mov     edx, 0DFh; void *
0x18005d4fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d502  mov     ecx, dword ptr [rbp+cItemGrow]; cItemGrow
0x18005d505  test    ecx, ecx
0x18005d507  jnz     short loc_18005D556
0x18005d509  xor     edx, edx; unsigned int
0x18005d50b  mov     rcx, [rbp+pv]; pv
0x18005d50f  call    ?FreeFilterArray@@YAXPEAPEAUIFilterCondition@@I@Z; FreeFilterArray(IFilterCondition * *,uint)
0x18005d514  nop
0x18005d515  mov     rcx, qword ptr [rbp+var_38]
0x18005d519  test    rcx, rcx
0x18005d51c  jz      short loc_18005D533
0x18005d51e  mov     qword ptr [rbp+var_38], 0
0x18005d526  mov     rax, [rcx]
0x18005d529  mov     rax, [rax+10h]
0x18005d52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d532  nop
0x18005d533  mov     rcx, [rbp+ppv]
0x18005d537  test    rcx, rcx
0x18005d53a  jz      short loc_18005D551
0x18005d53c  mov     [rbp+ppv], 0
0x18005d544  mov     rax, [rcx]
0x18005d547  mov     rax, [rax+10h]
0x18005d54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d550  nop
0x18005d551  jmp     loc_18005D699
0x18005d556  call    cs:__imp_DPA_Create
0x18005d55c  mov     rbx, rax
0x18005d55f  mov     [rbp+var_20], rax
0x18005d563  neg     rax
0x18005d566  sbb     r9d, r9d
0x18005d569  not     r9d
0x18005d56c  mov     r13d, 8007000Eh
0x18005d572  and     r9d, r13d; char *
0x18005d575  mov     rcx, [rbp+28h]; this
0x18005d579  jge     short loc_18005D58D
0x18005d57b  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d582  mov     edx, 0E7h; void *
0x18005d587  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d58d  xor     r15d, r15d
0x18005d590  cmp     dword ptr [rbp+cItemGrow], r15d
0x18005d594  jbe     short loc_18005D609
0x18005d596  mov     [rbp+p], 0
0x18005d59e  mov     rax, [rbp+pv]
0x18005d5a2  mov     rsi, [rax+r15*8]
0x18005d5a6  mov     rax, [rsi]
0x18005d5a9  mov     rdi, [rax+58h]
0x18005d5ad  lea     rcx, [rbp+p]
0x18005d5b1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005d5b6  lea     rdx, [rbp+p]
0x18005d5ba  mov     rcx, rsi
0x18005d5bd  mov     rax, rdi
0x18005d5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5c5  mov     rcx, [rbp+28h]; this
0x18005d5c9  test    eax, eax
0x18005d5cb  js      short loc_18005D62C
0x18005d5cd  mov     r8, [rbp+p]; p
0x18005d5d1  mov     [rbp+p], 0
0x18005d5d9  mov     edx, 7FFFFFFFh; i
0x18005d5de  mov     rcx, rbx; hdpa
0x18005d5e1  call    cs:__imp_DPA_InsertPtr
0x18005d5e7  xor     r9d, r9d
0x18005d5ea  cmp     eax, 0FFFFFFFFh
0x18005d5ed  cmovz   r9d, r13d; char *
0x18005d5f1  mov     rcx, [rbp+28h]; this
0x18005d5f5  jz      short loc_18005D61A
0x18005d5f7  lea     rcx, [rbp+p]
0x18005d5fb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005d600  inc     r15d
0x18005d603  cmp     r15d, dword ptr [rbp+cItemGrow]
0x18005d607  jb      short loc_18005D596
0x18005d609  add     r14, 90h
0x18005d610  test    rbx, rbx
0x18005d613  jz      short loc_18005D641
0x18005d615  mov     r8d, [rbx]
0x18005d618  jmp     short loc_18005D644
0x18005d61a  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d621  mov     edx, 0EDh; void *
0x18005d626  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d62c  mov     r9d, eax; char *
0x18005d62f  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d636  mov     edx, 0ECh; void *
0x18005d63b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d641  xor     r8d, r8d; unsigned int
0x18005d644  mov     qword ptr [rsp+70h+var_50], r14; int
0x18005d649  mov     rdx, [rbx+8]; struct ICondition **
0x18005d64d  call    ?SHCombineMultipleConditions@@YAJW4tagCONDITION_TYPE@@PEAPEAUICondition@@IAEBU_GUID@@PEAPEAX@Z; SHCombineMultipleConditions(tagCONDITION_TYPE,ICondition * *,uint,_GUID const &,void * *)
0x18005d652  mov     rcx, [rbp+28h]; this
0x18005d656  test    eax, eax
0x18005d658  jns     short loc_18005D66F
0x18005d65a  mov     r9d, eax; char *
0x18005d65d  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\windows.system.launc"...
0x18005d664  mov     edx, 0F1h; void *
0x18005d669  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d66f  lea     rcx, [rbp+var_20]
0x18005d673  call    ??1?$CDPA_Base@UICondition@@V?$CTContainer_PolicyRelease@UICondition@@@@@@QEAA@XZ; CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::~CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>(void)
0x18005d678  nop
0x18005d679  mov     edx, dword ptr [rbp+cItemGrow]; unsigned int
0x18005d67c  mov     rcx, [rbp+pv]; pv
0x18005d680  call    ?FreeFilterArray@@YAXPEAPEAUIFilterCondition@@I@Z; FreeFilterArray(IFilterCondition * *,uint)
0x18005d685  nop
0x18005d686  lea     rcx, [rbp+var_38]
0x18005d68a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005d68f  nop
0x18005d690  lea     rcx, [rbp+ppv]
0x18005d694  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d699  lea     r11, [rsp+70h+var_s0]
0x18005d69e  mov     rbx, [r11+38h]
0x18005d6a2  mov     rsi, [r11+40h]
0x18005d6a6  mov     rsp, r11
0x18005d6a9  pop     r15
0x18005d6ab  pop     r14
0x18005d6ad  pop     r13
0x18005d6af  pop     rdi
0x18005d6b0  pop     rbp
0x18005d6b1  retn
```
