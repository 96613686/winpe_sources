# CTopViewDescription::_WriteBack(int)

- ea: `0x1805aa5a0`
- end: `0x1805aa82a`
- name: `?_WriteBack@CTopViewDescription@@AEAAJH@Z`
- size: `650`
- prototype: `__int64 __fastcall(CTopViewDescription *__hidden this, int)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1805a9b20`
- `0x1805a9ce0`
- `0x1805a9d40`
- `0x1805a9de0`
- `0x1805a9e30`
- `0x1805a9f20`
- `0x1805a9fc0`
- `0x1805aa010`

## callees

- `0x1801fea9c`
- `0x180354104`
- `0x1803a4cb0`
- `0x1805aa4a0`
- `0x1805aa5a0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1805aa805`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1805aa805`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1805aa5d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1805aa5d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1805aa5e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1805aa5e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1805aa5cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1805aa5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805aa6fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805aa751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805aa78d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805aa6fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805aa751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805aa78d`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1805aa715`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1805aa715`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa61f`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa6f3`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa747`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa783`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa7d4`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa7ec`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa61f`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa6f3`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa747`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa783`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa7d4`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1805aa7ec`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805aa6da`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805aa72e`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805aa76a`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805aa6da`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805aa72e`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1805aa76a`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa637`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa64f`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa667`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa67c`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa694`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa6ac`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa7a5`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa637`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa64f`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa667`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa67c`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa694`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa6ac`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1805aa7a5`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1805aa6c1`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1805aa6c1`

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
0x1805aa5a0  push    rbp
0x1805aa5a2  push    rbx
0x1805aa5a3  push    rsi
0x1805aa5a4  push    rdi
0x1805aa5a5  mov     rbp, rsp
0x1805aa5a8  sub     rsp, 68h
0x1805aa5ac  mov     rax, cs:__security_cookie
0x1805aa5b3  xor     rax, rsp
0x1805aa5b6  mov     [rbp+var_18], rax
0x1805aa5ba  lea     rdi, [rcx+20h]
0x1805aa5be  mov     rbx, rcx
0x1805aa5c1  mov     esi, 1
0x1805aa5c6  test    edx, edx
0x1805aa5c8  jz      short loc_1805AA5DF
0x1805aa5ca  mov     rcx, rdi; SRWLock
0x1805aa5cd  call    cs:__imp_AcquireSRWLockExclusive
0x1805aa5d3  mov     rcx, rdi; SRWLock
0x1805aa5d6  mov     [rbx+6Ch], esi
0x1805aa5d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1805aa5df  mov     rcx, rdi; SRWLock
0x1805aa5e2  call    cs:__imp_AcquireSRWLockShared
0x1805aa5e8  lea     rax, [rbp+propBag]
0x1805aa5ec  mov     [rbp+propBag], 0
0x1805aa5f4  mov     r8d, esi; unsigned int
0x1805aa5f7  mov     [rsp+68h+var_48], rax; void **
0x1805aa5fc  xor     edx, edx; unsigned __int16 *
0x1805aa5fe  mov     rcx, rbx; this
0x1805aa601  call    ?_GetPropertyBag@CTopViewDescription@@AEAAJPEBGKAEBU_GUID@@PEAPEAX@Z; CTopViewDescription::_GetPropertyBag(ushort const *,ulong,_GUID const &,void * *)
0x1805aa606  mov     esi, eax
0x1805aa608  test    eax, eax
0x1805aa60a  js      loc_1805AA802
0x1805aa610  mov     rcx, [rbp+propBag]; propBag
0x1805aa614  lea     r8, [rbx+70h]; value
0x1805aa618  lea     rdx, aName; "Name"
0x1805aa61f  call    cs:__imp_PSPropertyBag_WriteStr
0x1805aa625  mov     r8d, [rbx+278h]; value
0x1805aa62c  lea     rdx, aVersion_0; "Version"
0x1805aa633  mov     rcx, [rbp+propBag]; propBag
0x1805aa637  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805aa63d  mov     r8d, [rbx+484h]; value
0x1805aa644  lea     rdx, aLogicalviewmod; "LogicalViewMode"
0x1805aa64b  mov     rcx, [rbp+propBag]; propBag
0x1805aa64f  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805aa655  mov     r8d, [rbx+488h]; value
0x1805aa65c  lea     rdx, aIconsize; "IconSize"
0x1805aa663  mov     rcx, [rbp+propBag]; propBag
0x1805aa667  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805aa66d  mov     r8d, [rbx+68h]; value
0x1805aa671  lea     rdx, aQuerytype; "QueryType"
0x1805aa678  mov     rcx, [rbp+propBag]; propBag
0x1805aa67c  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805aa682  mov     r8d, [rbx+4E0h]; value
0x1805aa689  lea     rdx, aHidefilenames; "HideFileNames"
0x1805aa690  mov     rcx, [rbp+propBag]; propBag
0x1805aa694  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805aa69a  mov     r8d, [rbx+4DCh]; value
0x1805aa6a1  lea     rdx, aDatecategorize; "DateCategorizerInfo"
0x1805aa6a8  mov     rcx, [rbp+propBag]; propBag
0x1805aa6ac  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805aa6b2  mov     rcx, [rbp+propBag]; propBag
0x1805aa6b6  lea     r8, [rbx+58h]; value
0x1805aa6ba  lea     rdx, aChildviewid; "ChildViewID"
0x1805aa6c1  call    cs:__imp_PSPropertyBag_WriteGUID
0x1805aa6c7  lea     rcx, [rbx+48Ch]; propkey
0x1805aa6ce  mov     [rbp+ppszCanonicalName], 0
0x1805aa6d6  lea     rdx, [rbp+ppszCanonicalName]; ppszCanonicalName
0x1805aa6da  call    cs:__imp_PSGetNameFromPropertyKey
0x1805aa6e0  test    eax, eax
0x1805aa6e2  js      short loc_1805AA703
0x1805aa6e4  mov     r8, [rbp+ppszCanonicalName]; value
0x1805aa6e8  lea     rdx, aGroupby; "GroupBy"
0x1805aa6ef  mov     rcx, [rbp+propBag]; propBag
0x1805aa6f3  call    cs:__imp_PSPropertyBag_WriteStr
0x1805aa6f9  mov     rcx, [rbp+ppszCanonicalName]; pv
0x1805aa6fd  call    cs:__imp_CoTaskMemFree
0x1805aa703  mov     r8d, [rbx+4A0h]; value
0x1805aa70a  lea     rdx, aGroupascending; "GroupAscending"
0x1805aa711  mov     rcx, [rbp+propBag]; propBag
0x1805aa715  call    cs:__imp_PSPropertyBag_WriteBOOL
0x1805aa71b  lea     rcx, [rbx+4C8h]; propkey
0x1805aa722  mov     [rbp+var_28], 0
0x1805aa72a  lea     rdx, [rbp+var_28]; ppszCanonicalName
0x1805aa72e  call    cs:__imp_PSGetNameFromPropertyKey
0x1805aa734  test    eax, eax
0x1805aa736  js      short loc_1805AA757
0x1805aa738  mov     r8, [rbp+var_28]; value
0x1805aa73c  lea     rdx, aStackby; "StackBy"
0x1805aa743  mov     rcx, [rbp+propBag]; propBag
0x1805aa747  call    cs:__imp_PSPropertyBag_WriteStr
0x1805aa74d  mov     rcx, [rbp+var_28]; pv
0x1805aa751  call    cs:__imp_CoTaskMemFree
0x1805aa757  lea     rcx, [rbx+4E4h]; propkey
0x1805aa75e  mov     [rbp+var_20], 0
0x1805aa766  lea     rdx, [rbp+var_20]; ppszCanonicalName
0x1805aa76a  call    cs:__imp_PSGetNameFromPropertyKey
0x1805aa770  test    eax, eax
0x1805aa772  js      short loc_1805AA793
0x1805aa774  mov     r8, [rbp+var_20]; value
0x1805aa778  lea     rdx, aPrimarypropert; "PrimaryProperty"
0x1805aa77f  mov     rcx, [rbp+propBag]; propBag
0x1805aa783  call    cs:__imp_PSPropertyBag_WriteStr
0x1805aa789  mov     rcx, [rbp+var_20]; pv
0x1805aa78d  call    cs:__imp_CoTaskMemFree
0x1805aa793  mov     r8d, [rbx+4F8h]; value
0x1805aa79a  lea     rdx, aPrimarysetting; "PrimarySettings"
0x1805aa7a1  mov     rcx, [rbp+propBag]; propBag
0x1805aa7a5  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1805aa7ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53797701@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701> `wil::Feature<__WilFeatureTraits_Feature_53797701>::GetImpl(void)'::`2'::impl
0x1805aa7b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701>::__private_IsEnabled(void)
0x1805aa7b7  mov     r8, [rbx+4A8h]; value
0x1805aa7be  lea     rdx, aColumnlist5379; "ColumnList_53797701"
0x1805aa7c5  mov     rcx, [rbp+propBag]; propBag
0x1805aa7c9  test    al, al
0x1805aa7cb  jnz     short loc_1805AA7D4
0x1805aa7cd  lea     rdx, aColumnlist; "ColumnList"
0x1805aa7d4  call    cs:__imp_PSPropertyBag_WriteStr
0x1805aa7da  mov     r8, [rbx+4B0h]; value
0x1805aa7e1  lea     rdx, aSortbylist; "SortByList"
0x1805aa7e8  mov     rcx, [rbp+propBag]; propBag
0x1805aa7ec  call    cs:__imp_PSPropertyBag_WriteStr
0x1805aa7f2  mov     rcx, [rbp+propBag]
0x1805aa7f6  mov     rax, [rcx]
0x1805aa7f9  mov     rax, [rax+10h]
0x1805aa7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805aa802  mov     rcx, rdi; SRWLock
0x1805aa805  call    cs:__imp_ReleaseSRWLockShared
0x1805aa80b  mov     rcx, rbx; this
0x1805aa80e  call    ?_UpdateRelatedFolderTypes@CTopViewDescription@@AEAAXXZ; CTopViewDescription::_UpdateRelatedFolderTypes(void)
0x1805aa813  mov     eax, esi
0x1805aa815  mov     rcx, [rbp+var_18]
0x1805aa819  xor     rcx, rsp; StackCookie
0x1805aa81c  call    __security_check_cookie
0x1805aa821  add     rsp, 68h
0x1805aa825  pop     rdi
0x1805aa826  pop     rsi
0x1805aa827  pop     rbx
0x1805aa828  pop     rbp
0x1805aa829  retn
```
