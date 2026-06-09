# CSingleIdentity::DeleteCredManLog(void)

- ea: `0x1800d83f0`
- end: `0x1800d8683`
- name: `?DeleteCredManLog@CSingleIdentity@@QEAAXXZ`
- size: `659`
- prototype: `void __fastcall(CSingleIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008bbb0`

## callees

- `0x180006ac0`
- `0x18000ed04`
- `0x180013510`
- `0x18001426c`
- `0x1800151c4`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f968`
- `0x180023d24`
- `0x1800264b0`
- `0x180043344`
- `0x180052340`
- `0x180054910`
- `0x18008d4bc`
- `0x1800d83f0`
- `0x1800ddd80`
- `0x1800ddda4`
- `0x1800dddc0`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d852b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d85c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d852b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d85c5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800d8564`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800d8601`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800d8564`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800d8601`

## string_xrefs

- `0x1800d841a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800d8454`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800d8613`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`

## pseudocode

```c
void __fastcall CSingleIdentity::DeleteCredManLog(CSingleIdentity *this)
{
  int v2; // eax
  int TokenUser; // eax
  unsigned int v4; // r8d
  const char *v5; // r9
  const WCHAR *Buffer; // rax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // eax
  unsigned int v13; // r8d
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 v18; // [rsp+0h] [rbp-78h] BYREF
  PHKEY phkResult; // [rsp+20h] [rbp-58h]
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v22; // [rsp+40h] [rbp-38h] BYREF
  void *v23[2]; // [rsp+48h] [rbp-30h] BYREF
  HKEY *p_hKey; // [rsp+58h] [rbp-20h] BYREF
  HKEY v25; // [rsp+60h] [rbp-18h] BYREF
  char v26; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  char v28; // [rsp+88h] [rbp+10h] BYREF
  __int64 v29; // [rsp+90h] [rbp+18h] BYREF
  HKEY v30; // [rsp+98h] [rbp+20h] BYREF

  v29 = 0;
  v2 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v29, 0);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x753,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        (const char *)(unsigned int)v2,
        (int)phkResult);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v22);
    TokenUser = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v29, &v22);
    if ( TokenUser < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x755,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        (const char *)(unsigned int)TokenUser,
        (int)phkResult);
    (*(void (__fastcall **)(CSingleIdentity *, _BYTE *))(*(_QWORD *)this + 32LL))(this, v21);
    LODWORD(v23[0]) = 0;
    v23[1] = 0;
    if ( !(unsigned int)CAutoRevertToSelf::Revert(v23, 0) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x75C, v4, v5);
    hKey = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v28,
      L".Default\\Software\\Microsoft\\IdentityCRL\\CredManLog");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&v28);
    ATL::CSimpleStringT<unsigned short,0>::Append(&v28, v21);
    p_hKey = &hKey;
    v25 = 0;
    v26 = 1;
    Buffer = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v28);
    v7 = RegOpenKeyExW(HKEY_USERS, Buffer, 0, 2u, &v25);
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x769, v8, (const char *)v7, (unsigned int)phkResult);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    v9 = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v22);
    v10 = RegDeleteKeyW(hKey, v9);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x76D, v11, (const char *)v10, (unsigned int)phkResult);
    v30 = 0;
    p_hKey = &v30;
    v25 = 0;
    v26 = 1;
    v12 = RegOpenKeyExW(HKEY_USERS, L".Default\\Software\\Microsoft\\IdentityCRL\\CredManLog", 0, 2u, &v25);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x776, v13, (const char *)v12, (unsigned int)phkResult);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    v14 = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v21);
    v15 = RegDeleteKeyW(v30, v14);
    if ( v15 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x77B,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        (const char *)v15,
        (unsigned int)phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)v23);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v21);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v22);
    CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v29);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, &v18, v16, v17);
  }
}

```

## disassembly

```asm
0x1800d83f0  mov     rax, rsp
0x1800d83f3  push    rbx
0x1800d83f4  sub     rsp, 70h
0x1800d83f8  mov     rbx, rcx
0x1800d83fb  mov     qword ptr [rax+18h], 0
0x1800d8403  xor     edx, edx; struct ATL::CAccessToken *
0x1800d8405  lea     rcx, [rax+18h]; this
0x1800d8409  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x1800d840e  mov     rcx, [rsp+78h]; this
0x1800d8413  test    eax, eax
0x1800d8415  jns     short loc_1800D842B
0x1800d8417  mov     r9d, eax; char *
0x1800d841a  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800d8421  mov     edx, 753h; void *
0x1800d8426  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d842b  lea     rcx, [rsp+78h+var_38]
0x1800d8430  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d8435  nop
0x1800d8436  lea     rdx, [rsp+78h+var_38]
0x1800d843b  lea     rcx, [rsp+78h+arg_10]; this
0x1800d8443  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800d8448  mov     rcx, [rsp+78h]; this
0x1800d844d  test    eax, eax
0x1800d844f  jns     short loc_1800D8465
0x1800d8451  mov     r9d, eax; char *
0x1800d8454  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800d845b  mov     edx, 755h; void *
0x1800d8460  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d8465  mov     rax, [rbx]
0x1800d8468  lea     rdx, [rsp+78h+var_40]
0x1800d846d  mov     rcx, rbx
0x1800d8470  mov     rax, [rax+20h]
0x1800d8474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8479  nop
0x1800d847a  mov     [rsp+78h+var_30], 0
0x1800d8482  mov     [rsp+78h+var_28], 0
0x1800d848b  xor     edx, edx; int
0x1800d848d  lea     rcx, [rsp+78h+var_30]; this
0x1800d8492  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x1800d8497  mov     rcx, [rsp+78h]; this
0x1800d849c  test    eax, eax
0x1800d849e  jnz     short loc_1800D84AA
0x1800d84a0  mov     edx, 75Ch; void *
0x1800d84a5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800d84aa  mov     [rsp+78h+hKey], 0
0x1800d84b3  lea     rdx, aDefaultSoftwar_1; ".Default\\Software\\Microsoft\\Identity"...
0x1800d84ba  lea     rcx, [rsp+78h+arg_8]
0x1800d84c2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800d84c7  nop
0x1800d84c8  lea     rcx, [rsp+78h+arg_8]
0x1800d84d0  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x1800d84d5  lea     rdx, [rsp+78h+var_40]
0x1800d84da  lea     rcx, [rsp+78h+arg_8]
0x1800d84e2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x1800d84e7  lea     rax, [rsp+78h+hKey]
0x1800d84ec  mov     [rsp+78h+var_20], rax
0x1800d84f1  mov     [rsp+78h+var_18], 0
0x1800d84fa  mov     [rsp+78h+var_10], 1
0x1800d84ff  lea     rcx, [rsp+78h+arg_8]
0x1800d8507  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800d850c  lea     rcx, [rsp+78h+var_18]
0x1800d8511  mov     [rsp+78h+phkResult], rcx; unsigned int
0x1800d8516  mov     ebx, 2
0x1800d851b  mov     r9d, ebx; samDesired
0x1800d851e  xor     r8d, r8d; ulOptions
0x1800d8521  mov     rdx, rax; lpSubKey
0x1800d8524  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800d852b  call    cs:__imp_RegOpenKeyExW
0x1800d8531  mov     rcx, [rsp+78h]; this
0x1800d8536  test    eax, eax
0x1800d8538  jz      short loc_1800D8548
0x1800d853a  mov     r9d, eax; char *
0x1800d853d  mov     edx, 769h; void *
0x1800d8542  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800d8548  lea     rcx, [rsp+78h+var_20]
0x1800d854d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d8552  lea     rcx, [rsp+78h+var_38]
0x1800d8557  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800d855c  mov     rdx, rax; lpSubKey
0x1800d855f  mov     rcx, [rsp+78h+hKey]; hKey
0x1800d8564  call    cs:__imp_RegDeleteKeyW
0x1800d856a  mov     rcx, [rsp+78h]; this
0x1800d856f  test    eax, eax
0x1800d8571  jz      short loc_1800D8580
0x1800d8573  mov     r9d, eax; char *
0x1800d8576  mov     edx, 76Dh; void *
0x1800d857b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800d8580  mov     [rsp+78h+arg_18], 0
0x1800d858c  lea     rax, [rsp+78h+arg_18]
0x1800d8594  mov     [rsp+78h+var_20], rax
0x1800d8599  mov     [rsp+78h+var_18], 0
0x1800d85a2  mov     [rsp+78h+var_10], 1
0x1800d85a7  lea     rax, [rsp+78h+var_18]
0x1800d85ac  mov     [rsp+78h+phkResult], rax; unsigned int
0x1800d85b1  mov     r9d, ebx; samDesired
0x1800d85b4  xor     r8d, r8d; ulOptions
0x1800d85b7  lea     rdx, aDefaultSoftwar_1; ".Default\\Software\\Microsoft\\Identity"...
0x1800d85be  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800d85c5  call    cs:__imp_RegOpenKeyExW
0x1800d85cb  mov     rcx, [rsp+78h]; this
0x1800d85d0  test    eax, eax
0x1800d85d2  jz      short loc_1800D85E2
0x1800d85d4  mov     r9d, eax; char *
0x1800d85d7  mov     edx, 776h; void *
0x1800d85dc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800d85e2  lea     rcx, [rsp+78h+var_20]
0x1800d85e7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d85ec  lea     rcx, [rsp+78h+var_40]
0x1800d85f1  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800d85f6  mov     rdx, rax; lpSubKey
0x1800d85f9  mov     rcx, [rsp+78h+arg_18]; hKey
0x1800d8601  call    cs:__imp_RegDeleteKeyW
0x1800d8607  mov     rcx, [rsp+78h]; this
0x1800d860c  test    eax, eax
0x1800d860e  jz      short loc_1800D8625
0x1800d8610  mov     r9d, eax; char *
0x1800d8613  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800d861a  mov     edx, 77Bh; void *
0x1800d861f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800d8624  nop
0x1800d8625  lea     rcx, [rsp+78h+arg_18]
0x1800d862d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d8632  nop
0x1800d8633  lea     rcx, [rsp+78h+arg_8]
0x1800d863b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d8640  nop
0x1800d8641  lea     rcx, [rsp+78h+hKey]
0x1800d8646  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d864b  nop
0x1800d864c  lea     rcx, [rsp+78h+var_30]; this
0x1800d8651  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x1800d8656  nop
0x1800d8657  lea     rcx, [rsp+78h+var_40]
0x1800d865c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d8661  nop
0x1800d8662  lea     rcx, [rsp+78h+var_38]
0x1800d8667  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d866c  nop
0x1800d866d  lea     rcx, [rsp+78h+arg_10]; this
0x1800d8675  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x1800d867a  nop
0x1800d867b  jmp     short $+2
0x1800d867d  add     rsp, 70h
0x1800d8681  pop     rbx
0x1800d8682  retn
```
