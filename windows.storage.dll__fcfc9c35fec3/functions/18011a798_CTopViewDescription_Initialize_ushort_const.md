# CTopViewDescription::Initialize(ushort const *)

- ea: `0x18011a798`
- end: `0x18011ab0e`
- name: `?Initialize@CTopViewDescription@@QEAAJPEBG@Z`
- size: `886`
- prototype: `__int64 __fastcall(CTopViewDescription *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18011a584`

## callees

- `0x18011a798`
- `0x18027ffd4`
- `0x180302e5c`
- `0x180367ae4`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011aad4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011aad4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011a7d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011a7d4`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18011a871`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18011a871`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18011a987`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18011a987`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a82c`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a945`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a9a9`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a9e9`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a82c`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a945`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a9a9`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18011a9e9`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a855`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a890`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a8af`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a8cb`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a8ea`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a909`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011aa26`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a855`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a890`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a8af`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a8cb`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a8ea`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011a909`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18011aa26`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18011a925`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18011a925`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18011aa6c`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18011aa94`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18011aab3`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18011aa6c`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18011aa94`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18011aab3`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18011a961`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18011a9c7`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18011aa07`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18011a961`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18011a9c7`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18011aa07`

## pseudocode

```c
__int64 __fastcall CTopViewDescription::Initialize(CTopViewDescription *this, const unsigned __int16 *a2)
{
  const struct _GUID *v4; // r9
  HRESULT PropertyBag; // edi
  IPropertyBag *v6; // rcx
  IPropertyBag *v7; // rcx
  char IsEnabled; // al
  IPropertyBag *v9; // rcx
  PWSTR *v10; // r8
  IPropertyBag *propBag; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR value[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR v15[264]; // [rsp+460h] [rbp+360h] BYREF

  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  propBag = 0;
  PropertyBag = CTopViewDescription::_GetPropertyBag(this, a2, 0, v4, (void **)&propBag);
  if ( PropertyBag >= 0 )
  {
    v6 = propBag;
    *((_WORD *)this + 56) = 0;
    PropertyBag = PSPropertyBag_ReadStr(v6, L"Name", (LPWSTR)this + 56, 260);
    if ( PropertyBag < 0 )
    {
LABEL_16:
      ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
      goto LABEL_17;
    }
    PSPropertyBag_ReadDWORD(propBag, L"Version", (DWORD *)this + 158);
    SHLoadIndirectString((PCWSTR)this + 56, (PWSTR)this + 318, 0x104u, 0);
    PSPropertyBag_ReadDWORD(propBag, L"LogicalViewMode", (DWORD *)this + 289);
    PSPropertyBag_ReadDWORD(propBag, L"IconSize", (DWORD *)this + 290);
    PSPropertyBag_ReadDWORD(propBag, L"QueryType", (DWORD *)this + 26);
    PSPropertyBag_ReadDWORD(propBag, L"HideFileNames", (DWORD *)this + 312);
    PSPropertyBag_ReadDWORD(propBag, L"DateCategorizerInfo", (DWORD *)this + 311);
    PSPropertyBag_ReadGUID(propBag, L"ChildViewID", (GUID *)((char *)this + 88));
    if ( PSPropertyBag_ReadStr(propBag, L"GroupBy", value, 260) >= 0 )
      PSGetPropertyKeyFromName(value, (PROPERTYKEY *)((char *)this + 1164));
    v7 = propBag;
    *((_DWORD *)this + 296) = 1;
    PSPropertyBag_ReadBOOL(v7, L"GroupAscending", (BOOL *)this + 296);
    if ( PSPropertyBag_ReadStr(propBag, L"StackBy", pszName, 260) >= 0 )
      PSGetPropertyKeyFromName(pszName, (PROPERTYKEY *)((char *)this + 1224));
    if ( PSPropertyBag_ReadStr(propBag, L"PrimaryProperty", v15, 260) >= 0 )
      PSGetPropertyKeyFromName(v15, (PROPERTYKEY *)((char *)this + 1252));
    PSPropertyBag_ReadDWORD(propBag, L"PrimarySettings", (DWORD *)this + 318);
    if ( CTopViewDescription::_InitializeColumnListWithEncryptionOwners(this, a2, propBag) < 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53797701>::GetImpl'::`2'::impl);
      v9 = propBag;
      if ( !IsEnabled )
      {
        v10 = (PWSTR *)((char *)this + 1192);
        goto LABEL_14;
      }
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"ColumnList_53797701", (PWSTR *)this + 149) < 0 )
      {
        v9 = propBag;
        v10 = (PWSTR *)((char *)this + 1192);
LABEL_14:
        PSPropertyBag_ReadStrAlloc(v9, L"ColumnList", v10);
      }
    }
    PSPropertyBag_ReadStrAlloc(propBag, L"SortByList", (PWSTR *)this + 150);
    goto LABEL_16;
  }
LABEL_17:
  ReleaseSRWLockExclusive((PSRWLOCK)this + 4);
  return (unsigned int)PropertyBag;
}

```

## disassembly

```asm
0x18011a798  mov     [rsp-8+arg_10], rbx
0x18011a79d  mov     [rsp-8+arg_18], rsi
0x18011a7a2  push    rbp
0x18011a7a3  push    rdi
0x18011a7a4  push    r12
0x18011a7a6  push    r14
0x18011a7a8  push    r15
0x18011a7aa  lea     rbp, [rsp-580h]
0x18011a7b2  sub     rsp, 680h
0x18011a7b9  mov     rax, cs:__security_cookie
0x18011a7c0  xor     rax, rsp
0x18011a7c3  mov     [rbp+5A0h+var_30], rax
0x18011a7ca  mov     rbx, rcx
0x18011a7cd  mov     r15, rdx
0x18011a7d0  add     rcx, 20h ; ' '; SRWLock
0x18011a7d4  call    cs:__imp_AcquireSRWLockExclusive
0x18011a7db  nop     dword ptr [rax+rax+00h]
0x18011a7e0  lea     rax, [rsp+6A0h+propBag]
0x18011a7e5  mov     [rsp+6A0h+propBag], 0
0x18011a7ee  xor     r8d, r8d; unsigned int
0x18011a7f1  mov     [rsp+6A0h+var_680], rax; void **
0x18011a7f6  mov     rdx, r15; unsigned __int16 *
0x18011a7f9  mov     rcx, rbx; this
0x18011a7fc  call    ?_GetPropertyBag@CTopViewDescription@@AEAAJPEBGKAEBU_GUID@@PEAPEAX@Z; CTopViewDescription::_GetPropertyBag(ushort const *,ulong,_GUID const &,void * *)
0x18011a801  mov     edi, eax
0x18011a803  test    eax, eax
0x18011a805  js      loc_18011AAD0
0x18011a80b  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a810  lea     rsi, [rbx+70h]
0x18011a814  xor     eax, eax
0x18011a816  lea     rdx, aName; "Name"
0x18011a81d  mov     r12d, 104h
0x18011a823  mov     [rsi], ax
0x18011a826  mov     r9d, r12d; characterCount
0x18011a829  mov     r8, rsi; value
0x18011a82c  call    cs:__imp_PSPropertyBag_ReadStr
0x18011a833  nop     dword ptr [rax+rax+00h]
0x18011a838  mov     edi, eax
0x18011a83a  test    eax, eax
0x18011a83c  js      loc_18011AABF
0x18011a842  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a847  lea     r8, [rbx+278h]; value
0x18011a84e  lea     rdx, aVersion_0; "Version"
0x18011a855  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18011a85c  nop     dword ptr [rax+rax+00h]
0x18011a861  lea     rdx, [rbx+27Ch]; pszOutBuf
0x18011a868  xor     r9d, r9d; ppvReserved
0x18011a86b  mov     r8d, r12d; cchOutBuf
0x18011a86e  mov     rcx, rsi; pszSource
0x18011a871  call    cs:__imp_SHLoadIndirectString
0x18011a878  nop     dword ptr [rax+rax+00h]
0x18011a87d  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a882  lea     r8, [rbx+484h]; value
0x18011a889  lea     rdx, aLogicalviewmod; "LogicalViewMode"
0x18011a890  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18011a897  nop     dword ptr [rax+rax+00h]
0x18011a89c  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a8a1  lea     r8, [rbx+488h]; value
0x18011a8a8  lea     rdx, aIconsize; "IconSize"
0x18011a8af  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18011a8b6  nop     dword ptr [rax+rax+00h]
0x18011a8bb  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a8c0  lea     r8, [rbx+68h]; value
0x18011a8c4  lea     rdx, aQuerytype; "QueryType"
0x18011a8cb  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18011a8d2  nop     dword ptr [rax+rax+00h]
0x18011a8d7  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a8dc  lea     r8, [rbx+4E0h]; value
0x18011a8e3  lea     rdx, aHidefilenames; "HideFileNames"
0x18011a8ea  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18011a8f1  nop     dword ptr [rax+rax+00h]
0x18011a8f6  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a8fb  lea     r8, [rbx+4DCh]; value
0x18011a902  lea     rdx, aDatecategorize; "DateCategorizerInfo"
0x18011a909  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18011a910  nop     dword ptr [rax+rax+00h]
0x18011a915  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a91a  lea     r8, [rbx+58h]; value
0x18011a91e  lea     rdx, aChildviewid; "ChildViewID"
0x18011a925  call    cs:__imp_PSPropertyBag_ReadGUID
0x18011a92c  nop     dword ptr [rax+rax+00h]
0x18011a931  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a936  lea     r8, [rsp+6A0h+value]; value
0x18011a93b  mov     r9d, r12d; characterCount
0x18011a93e  lea     rdx, aGroupby; "GroupBy"
0x18011a945  call    cs:__imp_PSPropertyBag_ReadStr
0x18011a94c  nop     dword ptr [rax+rax+00h]
0x18011a951  test    eax, eax
0x18011a953  js      short loc_18011A96D
0x18011a955  lea     rdx, [rbx+48Ch]; ppropkey
0x18011a95c  lea     rcx, [rsp+6A0h+value]; pszName
0x18011a961  call    cs:__imp_PSGetPropertyKeyFromName
0x18011a968  nop     dword ptr [rax+rax+00h]
0x18011a96d  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a972  lea     r8, [rbx+4A0h]; value
0x18011a979  lea     rdx, aGroupascending; "GroupAscending"
0x18011a980  mov     dword ptr [r8], 1
0x18011a987  call    cs:__imp_PSPropertyBag_ReadBOOL
0x18011a98e  nop     dword ptr [rax+rax+00h]
0x18011a993  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a998  lea     r8, [rbp+5A0h+pszName]; value
0x18011a99f  mov     r9d, r12d; characterCount
0x18011a9a2  lea     rdx, aStackby; "StackBy"
0x18011a9a9  call    cs:__imp_PSPropertyBag_ReadStr
0x18011a9b0  nop     dword ptr [rax+rax+00h]
0x18011a9b5  test    eax, eax
0x18011a9b7  js      short loc_18011A9D3
0x18011a9b9  lea     rdx, [rbx+4C8h]; ppropkey
0x18011a9c0  lea     rcx, [rbp+5A0h+pszName]; pszName
0x18011a9c7  call    cs:__imp_PSGetPropertyKeyFromName
0x18011a9ce  nop     dword ptr [rax+rax+00h]
0x18011a9d3  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011a9d8  lea     r8, [rbp+5A0h+var_240]; value
0x18011a9df  mov     r9d, r12d; characterCount
0x18011a9e2  lea     rdx, aPrimarypropert; "PrimaryProperty"
0x18011a9e9  call    cs:__imp_PSPropertyBag_ReadStr
0x18011a9f0  nop     dword ptr [rax+rax+00h]
0x18011a9f5  test    eax, eax
0x18011a9f7  js      short loc_18011AA13
0x18011a9f9  lea     rdx, [rbx+4E4h]; ppropkey
0x18011aa00  lea     rcx, [rbp+5A0h+var_240]; pszName
0x18011aa07  call    cs:__imp_PSGetPropertyKeyFromName
0x18011aa0e  nop     dword ptr [rax+rax+00h]
0x18011aa13  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011aa18  lea     r8, [rbx+4F8h]; value
0x18011aa1f  lea     rdx, aPrimarysetting; "PrimarySettings"
0x18011aa26  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18011aa2d  nop     dword ptr [rax+rax+00h]
0x18011aa32  mov     r8, [rsp+6A0h+propBag]; struct IPropertyBag *
0x18011aa37  mov     rdx, r15; unsigned __int16 *
0x18011aa3a  mov     rcx, rbx; this
0x18011aa3d  call    ?_InitializeColumnListWithEncryptionOwners@CTopViewDescription@@AEAAJPEBGPEAUIPropertyBag@@@Z; CTopViewDescription::_InitializeColumnListWithEncryptionOwners(ushort const *,IPropertyBag *)
0x18011aa42  test    eax, eax
0x18011aa44  jns     short loc_18011AAA0
0x18011aa46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53797701@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701> `wil::Feature<__WilFeatureTraits_Feature_53797701>::GetImpl(void)'::`2'::impl
0x18011aa4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701>::__private_IsEnabled(void)
0x18011aa52  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011aa57  test    al, al
0x18011aa59  jz      short loc_18011AA86
0x18011aa5b  lea     rsi, [rbx+4A8h]
0x18011aa62  mov     r8, rsi; value
0x18011aa65  lea     rdx, aColumnlist5379; "ColumnList_53797701"
0x18011aa6c  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x18011aa73  nop     dword ptr [rax+rax+00h]
0x18011aa78  test    eax, eax
0x18011aa7a  jns     short loc_18011AAA0
0x18011aa7c  mov     rcx, [rsp+6A0h+propBag]
0x18011aa81  mov     r8, rsi
0x18011aa84  jmp     short loc_18011AA8D
0x18011aa86  lea     r8, [rbx+4A8h]; value
0x18011aa8d  lea     rdx, aColumnlist; "ColumnList"
0x18011aa94  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x18011aa9b  nop     dword ptr [rax+rax+00h]
0x18011aaa0  mov     rcx, [rsp+6A0h+propBag]; propBag
0x18011aaa5  lea     r8, [rbx+4B0h]; value
0x18011aaac  lea     rdx, aSortbylist; "SortByList"
0x18011aab3  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x18011aaba  nop     dword ptr [rax+rax+00h]
0x18011aabf  mov     rcx, [rsp+6A0h+propBag]
0x18011aac4  mov     rax, [rcx]
0x18011aac7  mov     rax, [rax+10h]
0x18011aacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011aad0  lea     rcx, [rbx+20h]; SRWLock
0x18011aad4  call    cs:__imp_ReleaseSRWLockExclusive
0x18011aadb  nop     dword ptr [rax+rax+00h]
0x18011aae0  mov     eax, edi
0x18011aae2  mov     rcx, [rbp+5A0h+var_30]
0x18011aae9  xor     rcx, rsp; StackCookie
0x18011aaec  call    __security_check_cookie
0x18011aaf1  lea     r11, [rsp+6A0h+var_20]
0x18011aaf9  mov     rbx, [r11+40h]
0x18011aafd  mov     rsi, [r11+48h]
0x18011ab01  mov     rsp, r11
0x18011ab04  pop     r15
0x18011ab06  pop     r14
0x18011ab08  pop     r12
0x18011ab0a  pop     rdi
0x18011ab0b  pop     rbp
0x18011ab0c  retn
```
