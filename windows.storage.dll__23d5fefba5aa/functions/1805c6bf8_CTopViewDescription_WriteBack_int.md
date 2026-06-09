# CTopViewDescription::_WriteBack(int)

- ea: `0x1805c6bf8`
- end: `0x1805c6f19`
- name: `?_WriteBack@CTopViewDescription@@AEAAJH@Z`
- size: `801`
- prototype: `__int64 __fastcall(CTopViewDescription *__hidden this, int)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1805c60d0`
- `0x1805c62c0`
- `0x1805c6320`
- `0x1805c63d0`
- `0x1805c6430`
- `0x1805c6530`
- `0x1805c65e0`
- `0x1805c6640`

## callees

- `0x18027ffd4`
- `0x180367ae4`
- `0x1803b1f60`
- `0x1805c6ae8`
- `0x1805c6bf8`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1805c6eed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1805c6eed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1805c6c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1805c6c37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1805c6c46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1805c6c46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1805c6c25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1805c6c25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c6da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c6e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c6e5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c6da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c6e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c6e5d`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1805c6dc1`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1805c6dc1`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6c89`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6d93`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6dff`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6e4d`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6eb0`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6ece`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6c89`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6d93`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6dff`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6e4d`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6eb0`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805c6ece`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805c6d74`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805c6de0`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805c6e2e`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805c6d74`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805c6de0`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805c6e2e`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6ca7`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6cc5`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6ce3`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6cfe`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6d1c`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6d3a`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6e7b`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6ca7`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6cc5`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6ce3`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6cfe`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6d1c`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6d3a`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805c6e7b`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1805c6d55`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1805c6d55`

## pseudocode

```c
__int64 __fastcall CTopViewDescription::_WriteBack(CTopViewDescription *this, int a2)
{
  RTL_SRWLOCK *v2; // rdi
  const struct _GUID *v4; // r9
  int PropertyBag; // esi
  char IsEnabled; // al
  const WCHAR *v7; // rdx
  IPropertyBag *propBag; // [rsp+30h] [rbp-38h] BYREF
  PWSTR ppszCanonicalName; // [rsp+38h] [rbp-30h] BYREF
  PWSTR v11; // [rsp+40h] [rbp-28h] BYREF
  PWSTR v12; // [rsp+48h] [rbp-20h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 32);
  if ( a2 )
  {
    AcquireSRWLockExclusive(v2);
    *((_DWORD *)this + 27) = 1;
    ReleaseSRWLockExclusive(v2);
  }
  AcquireSRWLockShared(v2);
  propBag = 0;
  PropertyBag = CTopViewDescription::_GetPropertyBag(this, 0, 1u, v4, (void **)&propBag);
  if ( PropertyBag >= 0 )
  {
    PSPropertyBag_WriteStr(propBag, L"Name", (LPCWSTR)this + 56);
    PSPropertyBag_WriteDWORD(propBag, L"Version", *((_DWORD *)this + 158));
    PSPropertyBag_WriteDWORD(propBag, L"LogicalViewMode", *((_DWORD *)this + 289));
    PSPropertyBag_WriteDWORD(propBag, L"IconSize", *((_DWORD *)this + 290));
    PSPropertyBag_WriteDWORD(propBag, L"QueryType", *((_DWORD *)this + 26));
    PSPropertyBag_WriteDWORD(propBag, L"HideFileNames", *((_DWORD *)this + 312));
    PSPropertyBag_WriteDWORD(propBag, L"DateCategorizerInfo", *((_DWORD *)this + 311));
    PSPropertyBag_WriteGUID(propBag, L"ChildViewID", (const GUID *)((char *)this + 88));
    ppszCanonicalName = 0;
    if ( PSGetNameFromPropertyKey((const PROPERTYKEY *const)((char *)this + 1164), &ppszCanonicalName) >= 0 )
    {
      PSPropertyBag_WriteStr(propBag, L"GroupBy", ppszCanonicalName);
      CoTaskMemFree(ppszCanonicalName);
    }
    PSPropertyBag_WriteBOOL(propBag, L"GroupAscending", *((_DWORD *)this + 296));
    v11 = 0;
    if ( PSGetNameFromPropertyKey((const PROPERTYKEY *const)((char *)this + 1224), &v11) >= 0 )
    {
      PSPropertyBag_WriteStr(propBag, L"StackBy", v11);
      CoTaskMemFree(v11);
    }
    v12 = 0;
    if ( PSGetNameFromPropertyKey((const PROPERTYKEY *const)((char *)this + 1252), &v12) >= 0 )
    {
      PSPropertyBag_WriteStr(propBag, L"PrimaryProperty", v12);
      CoTaskMemFree(v12);
    }
    PSPropertyBag_WriteDWORD(propBag, L"PrimarySettings", *((_DWORD *)this + 318));
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53797701>::GetImpl'::`2'::impl);
    v7 = L"ColumnList_53797701";
    if ( !IsEnabled )
      v7 = L"ColumnList";
    PSPropertyBag_WriteStr(propBag, v7, *((LPCWSTR *)this + 149));
    PSPropertyBag_WriteStr(propBag, L"SortByList", *((LPCWSTR *)this + 150));
    ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
  }
  ReleaseSRWLockShared(v2);
  CTopViewDescription::_UpdateRelatedFolderTypes(this);
  return (unsigned int)PropertyBag;
}

```

## disassembly

```asm
0x1805c6bf8  push    rbp
0x1805c6bfa  push    rbx
0x1805c6bfb  push    rsi
0x1805c6bfc  push    rdi
0x1805c6bfd  mov     rbp, rsp
0x1805c6c00  sub     rsp, 68h
0x1805c6c04  mov     rax, cs:__security_cookie
0x1805c6c0b  xor     rax, rsp
0x1805c6c0e  mov     [rbp+var_18], rax
0x1805c6c12  lea     rdi, [rcx+20h]
0x1805c6c16  mov     rbx, rcx
0x1805c6c19  mov     esi, 1
0x1805c6c1e  test    edx, edx
0x1805c6c20  jz      short loc_1805C6C43
0x1805c6c22  mov     rcx, rdi; SRWLock
0x1805c6c25  call    cs:__imp_AcquireSRWLockExclusive
0x1805c6c2c  nop     dword ptr [rax+rax+00h]
0x1805c6c31  mov     rcx, rdi; SRWLock
0x1805c6c34  mov     [rbx+6Ch], esi
0x1805c6c37  call    cs:__imp_ReleaseSRWLockExclusive
0x1805c6c3e  nop     dword ptr [rax+rax+00h]
0x1805c6c43  mov     rcx, rdi; SRWLock
0x1805c6c46  call    cs:__imp_AcquireSRWLockShared
0x1805c6c4d  nop     dword ptr [rax+rax+00h]
0x1805c6c52  lea     rax, [rbp+propBag]
0x1805c6c56  mov     [rbp+propBag], 0
0x1805c6c5e  mov     r8d, esi; unsigned int
0x1805c6c61  mov     [rsp+68h+var_48], rax; void **
0x1805c6c66  xor     edx, edx; unsigned __int16 *
0x1805c6c68  mov     rcx, rbx; this
0x1805c6c6b  call    ?_GetPropertyBag@CTopViewDescription@@AEAAJPEBGKAEBU_GUID@@PEAPEAX@Z; CTopViewDescription::_GetPropertyBag(ushort const *,ulong,_GUID const &,void * *)
0x1805c6c70  mov     esi, eax
0x1805c6c72  test    eax, eax
0x1805c6c74  js      loc_1805C6EEA
0x1805c6c7a  mov     rcx, [rbp+propBag]; propBag
0x1805c6c7e  lea     r8, [rbx+70h]; value
0x1805c6c82  lea     rdx, aName; "Name"
0x1805c6c89  call    cs:__imp_PSPropertyBag_WriteStr
0x1805c6c90  nop     dword ptr [rax+rax+00h]
0x1805c6c95  mov     r8d, [rbx+278h]; value
0x1805c6c9c  lea     rdx, aVersion_0; "Version"
0x1805c6ca3  mov     rcx, [rbp+propBag]; propBag
0x1805c6ca7  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805c6cae  nop     dword ptr [rax+rax+00h]
0x1805c6cb3  mov     r8d, [rbx+484h]; value
0x1805c6cba  lea     rdx, aLogicalviewmod; "LogicalViewMode"
0x1805c6cc1  mov     rcx, [rbp+propBag]; propBag
0x1805c6cc5  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805c6ccc  nop     dword ptr [rax+rax+00h]
0x1805c6cd1  mov     r8d, [rbx+488h]; value
0x1805c6cd8  lea     rdx, aIconsize; "IconSize"
0x1805c6cdf  mov     rcx, [rbp+propBag]; propBag
0x1805c6ce3  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805c6cea  nop     dword ptr [rax+rax+00h]
0x1805c6cef  mov     r8d, [rbx+68h]; value
0x1805c6cf3  lea     rdx, aQuerytype; "QueryType"
0x1805c6cfa  mov     rcx, [rbp+propBag]; propBag
0x1805c6cfe  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805c6d05  nop     dword ptr [rax+rax+00h]
0x1805c6d0a  mov     r8d, [rbx+4E0h]; value
0x1805c6d11  lea     rdx, aHidefilenames; "HideFileNames"
0x1805c6d18  mov     rcx, [rbp+propBag]; propBag
0x1805c6d1c  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805c6d23  nop     dword ptr [rax+rax+00h]
0x1805c6d28  mov     r8d, [rbx+4DCh]; value
0x1805c6d2f  lea     rdx, aDatecategorize; "DateCategorizerInfo"
0x1805c6d36  mov     rcx, [rbp+propBag]; propBag
0x1805c6d3a  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805c6d41  nop     dword ptr [rax+rax+00h]
0x1805c6d46  mov     rcx, [rbp+propBag]; propBag
0x1805c6d4a  lea     r8, [rbx+58h]; value
0x1805c6d4e  lea     rdx, aChildviewid; "ChildViewID"
0x1805c6d55  call    cs:__imp_PSPropertyBag_WriteGUID
0x1805c6d5c  nop     dword ptr [rax+rax+00h]
0x1805c6d61  lea     rcx, [rbx+48Ch]; propkey
0x1805c6d68  mov     [rbp+ppszCanonicalName], 0
0x1805c6d70  lea     rdx, [rbp+ppszCanonicalName]; ppszCanonicalName
0x1805c6d74  call    cs:__imp_PSGetNameFromPropertyKey
0x1805c6d7b  nop     dword ptr [rax+rax+00h]
0x1805c6d80  test    eax, eax
0x1805c6d82  js      short loc_1805C6DAF
0x1805c6d84  mov     r8, [rbp+ppszCanonicalName]; value
0x1805c6d88  lea     rdx, aGroupby; "GroupBy"
0x1805c6d8f  mov     rcx, [rbp+propBag]; propBag
0x1805c6d93  call    cs:__imp_PSPropertyBag_WriteStr
0x1805c6d9a  nop     dword ptr [rax+rax+00h]
0x1805c6d9f  mov     rcx, [rbp+ppszCanonicalName]; pv
0x1805c6da3  call    cs:__imp_CoTaskMemFree
0x1805c6daa  nop     dword ptr [rax+rax+00h]
0x1805c6daf  mov     r8d, [rbx+4A0h]; value
0x1805c6db6  lea     rdx, aGroupascending; "GroupAscending"
0x1805c6dbd  mov     rcx, [rbp+propBag]; propBag
0x1805c6dc1  call    cs:__imp_PSPropertyBag_WriteBOOL
0x1805c6dc8  nop     dword ptr [rax+rax+00h]
0x1805c6dcd  lea     rcx, [rbx+4C8h]; propkey
0x1805c6dd4  mov     [rbp+var_28], 0
0x1805c6ddc  lea     rdx, [rbp+var_28]; ppszCanonicalName
0x1805c6de0  call    cs:__imp_PSGetNameFromPropertyKey
0x1805c6de7  nop     dword ptr [rax+rax+00h]
0x1805c6dec  test    eax, eax
0x1805c6dee  js      short loc_1805C6E1B
0x1805c6df0  mov     r8, [rbp+var_28]; value
0x1805c6df4  lea     rdx, aStackby; "StackBy"
0x1805c6dfb  mov     rcx, [rbp+propBag]; propBag
0x1805c6dff  call    cs:__imp_PSPropertyBag_WriteStr
0x1805c6e06  nop     dword ptr [rax+rax+00h]
0x1805c6e0b  mov     rcx, [rbp+var_28]; pv
0x1805c6e0f  call    cs:__imp_CoTaskMemFree
0x1805c6e16  nop     dword ptr [rax+rax+00h]
0x1805c6e1b  lea     rcx, [rbx+4E4h]; propkey
0x1805c6e22  mov     [rbp+var_20], 0
0x1805c6e2a  lea     rdx, [rbp+var_20]; ppszCanonicalName
0x1805c6e2e  call    cs:__imp_PSGetNameFromPropertyKey
0x1805c6e35  nop     dword ptr [rax+rax+00h]
0x1805c6e3a  test    eax, eax
0x1805c6e3c  js      short loc_1805C6E69
0x1805c6e3e  mov     r8, [rbp+var_20]; value
0x1805c6e42  lea     rdx, aPrimarypropert; "PrimaryProperty"
0x1805c6e49  mov     rcx, [rbp+propBag]; propBag
0x1805c6e4d  call    cs:__imp_PSPropertyBag_WriteStr
0x1805c6e54  nop     dword ptr [rax+rax+00h]
0x1805c6e59  mov     rcx, [rbp+var_20]; pv
0x1805c6e5d  call    cs:__imp_CoTaskMemFree
0x1805c6e64  nop     dword ptr [rax+rax+00h]
0x1805c6e69  mov     r8d, [rbx+4F8h]; value
0x1805c6e70  lea     rdx, aPrimarysetting; "PrimarySettings"
0x1805c6e77  mov     rcx, [rbp+propBag]; propBag
0x1805c6e7b  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805c6e82  nop     dword ptr [rax+rax+00h]
0x1805c6e87  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53797701@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701> `wil::Feature<__WilFeatureTraits_Feature_53797701>::GetImpl(void)'::`2'::impl
0x1805c6e8e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701>::__private_IsEnabled(void)
0x1805c6e93  mov     r8, [rbx+4A8h]; value
0x1805c6e9a  lea     rdx, aColumnlist5379; "ColumnList_53797701"
0x1805c6ea1  mov     rcx, [rbp+propBag]; propBag
0x1805c6ea5  test    al, al
0x1805c6ea7  jnz     short loc_1805C6EB0
0x1805c6ea9  lea     rdx, aColumnlist; "ColumnList"
0x1805c6eb0  call    cs:__imp_PSPropertyBag_WriteStr
0x1805c6eb7  nop     dword ptr [rax+rax+00h]
0x1805c6ebc  mov     r8, [rbx+4B0h]; value
0x1805c6ec3  lea     rdx, aSortbylist; "SortByList"
0x1805c6eca  mov     rcx, [rbp+propBag]; propBag
0x1805c6ece  call    cs:__imp_PSPropertyBag_WriteStr
0x1805c6ed5  nop     dword ptr [rax+rax+00h]
0x1805c6eda  mov     rcx, [rbp+propBag]
0x1805c6ede  mov     rax, [rcx]
0x1805c6ee1  mov     rax, [rax+10h]
0x1805c6ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805c6eea  mov     rcx, rdi; SRWLock
0x1805c6eed  call    cs:__imp_ReleaseSRWLockShared
0x1805c6ef4  nop     dword ptr [rax+rax+00h]
0x1805c6ef9  mov     rcx, rbx; this
0x1805c6efc  call    ?_UpdateRelatedFolderTypes@CTopViewDescription@@AEAAXXZ; CTopViewDescription::_UpdateRelatedFolderTypes(void)
0x1805c6f01  mov     eax, esi
0x1805c6f03  mov     rcx, [rbp+var_18]
0x1805c6f07  xor     rcx, rsp; StackCookie
0x1805c6f0a  call    __security_check_cookie
0x1805c6f0f  add     rsp, 68h
0x1805c6f13  pop     rdi
0x1805c6f14  pop     rsi
0x1805c6f15  pop     rbx
0x1805c6f16  pop     rbp
0x1805c6f17  retn
```
