# Windows::System::Internal::UserProfile::CreateConnectedProfile(void)

- ea: `0x18004cf48`
- end: `0x18004d571`
- name: `?CreateConnectedProfile@UserProfile@Internal@System@Windows@@AEAAJXZ`
- size: `1577`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cef78`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180014e7c`
- `0x180014e9c`
- `0x180041fc0`
- `0x180042170`
- `0x18004bed4`
- `0x18004bf04`
- `0x18004bf50`
- `0x18004bf70`
- `0x18004cf48`
- `0x18004d578`
- `0x18004d710`
- `0x18004d734`
- `0x18004da04`
- `0x18004db44`
- `0x18004e4e8`
- `0x18004e58c`
- `0x1800b76d0`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d02e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d02e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d0d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d0d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d17c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d507`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d17c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d507`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004d2a2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004d2a2`

## string_xrefs

- `0x18004d043`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d0ae`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d10c`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d165`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d1ac`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d1f3`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d25f`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d2b4`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d350`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d44f`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::System::Internal::UserProfile::CreateConnectedProfile(HSTRING *this)
{
  HSTRING *v1; // r14
  void (__fastcall *v2)(void *, __int64 *); // rbx
  HRESULT Instance; // eax
  struct IConnectedUser *v4; // rbx
  int v5; // eax
  struct IConnectedUserStore *v6; // rdi
  __int64 (__fastcall *v7)(struct IConnectedUserStore *, _QWORD, PCWSTR, struct _GUID *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v9; // eax
  __int64 (__fastcall *v10)(struct IConnectedUser *, struct IPropertyStore **); // rdi
  int v11; // eax
  Windows::System::Internal::UserProfile *v12; // rcx
  int PropertyAsString; // eax
  Windows::System::Internal::UserProfile *v14; // rcx
  int v15; // eax
  struct _LSA_UNICODE_STRING *v16; // rcx
  bool v17; // di
  NTSTATUS v18; // eax
  const WCHAR *v19; // rbx
  int v20; // r8d
  const char *v21; // r9
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r15
  __int64 (__fastcall *v26)(__int64, PCWSTR, PCWSTR, _BYTE *); // r12
  PCWSTR v27; // rbx
  PCWSTR v28; // rax
  unsigned int v29; // eax
  char v30; // cl
  HSTRING v31; // rbx
  HSTRING v32; // rbx
  __int64 v33; // rdx
  HLOCAL v34; // rcx
  HLOCAL v35; // rcx
  struct IConnectedUserStore *v36; // rcx
  unsigned int v38; // eax
  struct IIdentityProvider **v39; // r9
  const unsigned __int16 *v40; // rdx
  wil *v41; // rcx
  int ppv; // [rsp+20h] [rbp-368h]
  int ppva; // [rsp+20h] [rbp-368h]
  int ppvb; // [rsp+20h] [rbp-368h]
  HSTRING string; // [rsp+40h] [rbp-348h] BYREF
  HSTRING v46; // [rsp+48h] [rbp-340h] BYREF
  struct IConnectedUserStore *v47; // [rsp+50h] [rbp-338h] BYREF
  struct IPropertyStore *v48; // [rsp+58h] [rbp-330h] BYREF
  struct IConnectedUser *v49; // [rsp+60h] [rbp-328h] BYREF
  PSID Sid; // [rsp+68h] [rbp-320h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-318h] BYREF
  __int64 v52; // [rsp+78h] [rbp-310h] BYREF
  __int64 v53; // [rsp+80h] [rbp-308h] BYREF
  HLOCAL v54; // [rsp+88h] [rbp-300h] BYREF
  HLOCAL *v55; // [rsp+90h] [rbp-2F8h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp-2F0h] BYREF
  char v57; // [rsp+A0h] [rbp-2E8h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-2E0h] BYREF
  struct _GUID v59; // [rsp+D8h] [rbp-2B0h] BYREF
  _QWORD v60[3]; // [rsp+E8h] [rbp-2A0h] BYREF
  unsigned __int64 v61; // [rsp+100h] [rbp-288h]
  HLOCAL *p_hMem; // [rsp+108h] [rbp-280h] BYREF
  __int64 v63; // [rsp+110h] [rbp-278h] BYREF
  char v64; // [rsp+118h] [rbp-270h]
  _BYTE v65[528]; // [rsp+130h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v1 = this;
  *(_QWORD *)&v59.Data1 = this;
  v52 = 0;
  v2 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  v2(&Windows::System::Internal::Adapters::g_AdapterCollection, &v52);
  v47 = 0;
  v49 = 0;
  v48 = 0;
  string = 0;
  v46 = 0;
  v61 = 7;
  v60[2] = 0;
  LOWORD(v60[0]) = 0;
  v54 = 0;
  hMem = 0;
  Sid = 0;
  v53 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Instance = CoCreateInstance(
               &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
               0,
               0x17u,
               &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
               (LPVOID *)&v47);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x547,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  try
  {
    Windows::System::Internal::UserProfile::FindConnectedUser((Windows::System::Internal::UserProfile *)v1, v47, &v49);
  }
  catch ( ... )
  {
    v38 = wil::ResultFromCaughtException(v41);
    LOBYTE(v40) = v38 != -2147023728;
    v41 = retaddr;
    if ( v38 != -2147023728 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x551,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)v38,
        ppv);
    v1 = *(HSTRING **)&v59.Data1;
  }
  v4 = v49;
  if ( !v49 )
  {
    v59 = GUID_NULL;
    v5 = Windows::System::Internal::UserProfile::LookupProviderByName(v41, v40, &v59, v39);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x558,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v5,
        ppva);
    v6 = v47;
    v7 = *(__int64 (__fastcall **)(struct IConnectedUserStore *, _QWORD, PCWSTR, struct _GUID *))(*(_QWORD *)v47 + 32LL);
    StringRawBuffer = WindowsGetStringRawBuffer(v1[12], 0);
    ppva = 0;
    v9 = v7(v6, 0, StringRawBuffer, &v59);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x560,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v9,
        0);
    Windows::System::Internal::UserProfile::FindConnectedUser((Windows::System::Internal::UserProfile *)v1, v47, &v49);
    v4 = v49;
  }
  v10 = *(__int64 (__fastcall **)(struct IConnectedUser *, struct IPropertyStore **))(*(_QWORD *)v4 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  v11 = v10(v4, &v48);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x564,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v11,
      ppva);
  WindowsDeleteString(string);
  string = 0;
  PropertyAsString = Windows::System::Internal::UserProfile::GetPropertyAsString(
                       v12,
                       v48,
                       &PKEY_Identity_PrimarySid,
                       &string);
  if ( PropertyAsString < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x565,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)PropertyAsString,
      ppva);
  WindowsDeleteString(v46);
  v46 = 0;
  v15 = Windows::System::Internal::UserProfile::GetPropertyAsString(v14, v48, &PKEY_Identity_UserName, &v46);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x566,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v15,
      ppva);
  v17 = IsWindowsCoreUserModelEnforced();
  if ( v17 )
  {
    v55 = (HLOCAL *)&v53;
    PolicyHandle = 0;
    v57 = 1;
    v18 = LsaOpenPolicy(v16, &ObjectAttributes, 0x801u, &PolicyHandle);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x571,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v18,
        ppva);
    wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v55);
    v19 = WindowsGetStringRawBuffer(string, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &Sid,
      0);
    if ( !ConvertStringSidToSidW(v19, &Sid) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x574,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        v21);
    *(_QWORD *)&v59.Data1 = Sid;
    p_hMem = &hMem;
    v63 = 0;
    v64 = 1;
    v55 = &v54;
    PolicyHandle = 0;
    v57 = 1;
    v22 = LsapLookupSids(v53, 0, v20, (unsigned int)&v59, (__int64)&PolicyHandle, (__int64)&v63);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x57C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v22,
        ppvb);
    wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>(&v55);
    wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>(&p_hMem);
    v23 = std::wstring::wstring(&p_hMem, *((_QWORD *)hMem + 2), (unsigned __int64)*((unsigned __int16 *)hMem + 4) >> 1);
    std::wstring::assign(v60, v23);
    LOBYTE(v24) = 1;
    std::wstring::_Tidy(&p_hMem, v24, 0);
  }
  v25 = v52;
  v26 = *(__int64 (__fastcall **)(__int64, PCWSTR, PCWSTR, _BYTE *))(*(_QWORD *)v52 + 40LL);
  if ( v17 )
  {
    v27 = (PCWSTR)v60;
    if ( v61 >= 8 )
      v27 = (PCWSTR)v60[0];
  }
  else
  {
    v27 = WindowsGetStringRawBuffer(v46, 0);
  }
  v28 = WindowsGetStringRawBuffer(string, 0);
  v29 = v26(v25, v28, v27, v65);
  if ( (int)(v29 + 0x80000000) < 0 || (v30 = 1, v29 == -2147024713) )
    v30 = 0;
  if ( v30 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x586,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v29,
      260);
  v31 = v46;
  v46 = 0;
  WindowsDeleteString(v1[11]);
  v1[11] = v31;
  v32 = string;
  string = 0;
  WindowsDeleteString(v1[15]);
  v1[15] = v32;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v53);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  v34 = hMem;
  hMem = 0;
  if ( v34 )
    LocalFree(v34);
  v35 = v54;
  v54 = 0;
  if ( v35 )
    LocalFree(v35);
  LOBYTE(v33) = 1;
  std::wstring::_Tidy(v60, v33, 0);
  WindowsDeleteString(v46);
  v46 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  v36 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(struct IConnectedUserStore *))(*(_QWORD *)v36 + 16LL))(v36);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  return 0;
}

```

## disassembly

```asm
0x18004cf48  push    rbx
0x18004cf4a  push    rsi
0x18004cf4b  push    rdi
0x18004cf4c  push    r12
0x18004cf4e  push    r14
0x18004cf50  push    r15
0x18004cf52  sub     rsp, 358h
0x18004cf59  mov     rax, cs:__security_cookie
0x18004cf60  xor     rax, rsp
0x18004cf63  mov     [rsp+388h+var_48], rax
0x18004cf6b  mov     r14, rcx
0x18004cf6e  mov     qword ptr [rsp+388h+var_2B0.Data1], rcx
0x18004cf76  xor     esi, esi
0x18004cf78  mov     [rsp+388h+var_310], rsi
0x18004cf7d  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004cf84  mov     rbx, [rax+18h]
0x18004cf88  lea     rcx, [rsp+388h+var_310]
0x18004cf8d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cf92  lea     rdx, [rsp+388h+var_310]
0x18004cf97  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004cf9e  mov     rax, rbx
0x18004cfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfa6  mov     [rsp+388h+var_338], rsi
0x18004cfab  mov     [rsp+388h+var_328], rsi
0x18004cfb0  mov     [rsp+388h+var_330], rsi
0x18004cfb5  mov     [rsp+388h+string], rsi
0x18004cfba  mov     [rsp+388h+var_340], rsi
0x18004cfbf  mov     [rsp+388h+var_288], 7
0x18004cfcb  mov     [rsp+388h+var_290], rsi
0x18004cfd3  mov     word ptr [rsp+388h+var_2A0], si
0x18004cfdb  mov     [rsp+388h+var_300], rsi
0x18004cfe3  mov     [rsp+388h+hMem], rsi
0x18004cfe8  mov     [rsp+388h+Sid], rsi
0x18004cfed  mov     [rsp+388h+var_308], rsi
0x18004cff5  xorps   xmm0, xmm0
0x18004cff8  movups  xmmword ptr [rsp+388h+ObjectAttributes.Length], xmm0
0x18004d000  movups  xmmword ptr [rsp+388h+ObjectAttributes.ObjectName], xmm0
0x18004d008  movups  xmmword ptr [rsp+388h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004d010  lea     rax, [rsp+388h+var_338]
0x18004d015  mov     [rsp+388h+ppv], rax; int
0x18004d01a  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x18004d021  xor     edx, edx; pUnkOuter
0x18004d023  lea     r8d, [rsi+17h]; dwClsContext
0x18004d027  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x18004d02e  call    cs:__imp_CoCreateInstance
0x18004d034  mov     rcx, [rsp+388h]; this
0x18004d03c  test    eax, eax
0x18004d03e  jns     short loc_18004D055
0x18004d040  mov     r9d, eax; char *
0x18004d043  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d04a  mov     edx, 547h; void *
0x18004d04f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d055  lea     r8, [rsp+388h+var_328]; struct IConnectedUser **
0x18004d05a  mov     rdx, [rsp+388h+var_338]; struct IConnectedUserStore *
0x18004d05f  mov     rcx, r14; this
0x18004d062  call    ?FindConnectedUser@UserProfile@Internal@System@Windows@@AEAAJPEAUIConnectedUserStore@@PEAPEAUIConnectedUser@@@Z; Windows::System::Internal::UserProfile::FindConnectedUser(IConnectedUserStore *,IConnectedUser * *)
0x18004d067  nop
0x18004d068  jmp     short loc_18004D074
0x18004d06a  xor     esi, esi
0x18004d06c  mov     r14, qword ptr [rsp+388h+var_2B0.Data1]
0x18004d074  mov     rbx, [rsp+388h+var_328]
0x18004d079  test    rbx, rbx
0x18004d07c  jnz     loc_18004D135
0x18004d082  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004d089  movdqu  xmmword ptr [rsp+388h+var_2B0.Data1], xmm0
0x18004d092  lea     r8, [rsp+388h+var_2B0]; struct _GUID *
0x18004d09a  call    ?LookupProviderByName@UserProfile@Internal@System@Windows@@AEAAJPEBGPEAU_GUID@@PEAPEAUIIdentityProvider@@@Z; Windows::System::Internal::UserProfile::LookupProviderByName(ushort const *,_GUID *,IIdentityProvider * *)
0x18004d09f  mov     rcx, [rsp+388h]; this
0x18004d0a7  test    eax, eax
0x18004d0a9  jns     short loc_18004D0C0
0x18004d0ab  mov     r9d, eax; char *
0x18004d0ae  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d0b5  mov     edx, 558h; void *
0x18004d0ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d0c0  mov     rdi, [rsp+388h+var_338]
0x18004d0c5  mov     rax, [rdi]
0x18004d0c8  mov     rbx, [rax+20h]
0x18004d0cc  xor     edx, edx; length
0x18004d0ce  mov     rcx, [r14+60h]; string
0x18004d0d2  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d0d8  mov     [rsp+388h+var_358], esi
0x18004d0dc  mov     [rsp+388h+var_360], rsi
0x18004d0e1  mov     dword ptr [rsp+388h+ppv], esi; int
0x18004d0e5  lea     r9, [rsp+388h+var_2B0]
0x18004d0ed  mov     r8, rax
0x18004d0f0  xor     edx, edx
0x18004d0f2  mov     rcx, rdi
0x18004d0f5  mov     rax, rbx
0x18004d0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0fd  mov     rcx, [rsp+388h]; this
0x18004d105  test    eax, eax
0x18004d107  jns     short loc_18004D11E
0x18004d109  mov     r9d, eax; char *
0x18004d10c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d113  mov     edx, 560h; void *
0x18004d118  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d11e  lea     r8, [rsp+388h+var_328]; struct IConnectedUser **
0x18004d123  mov     rdx, [rsp+388h+var_338]; struct IConnectedUserStore *
0x18004d128  mov     rcx, r14; this
0x18004d12b  call    ?FindConnectedUser@UserProfile@Internal@System@Windows@@AEAAJPEAUIConnectedUserStore@@PEAPEAUIConnectedUser@@@Z; Windows::System::Internal::UserProfile::FindConnectedUser(IConnectedUserStore *,IConnectedUser * *)
0x18004d130  mov     rbx, [rsp+388h+var_328]
0x18004d135  mov     rax, [rbx]
0x18004d138  mov     rdi, [rax+18h]
0x18004d13c  lea     rcx, [rsp+388h+var_330]
0x18004d141  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d146  lea     rdx, [rsp+388h+var_330]
0x18004d14b  mov     rcx, rbx
0x18004d14e  mov     rax, rdi
0x18004d151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d156  mov     rcx, [rsp+388h]; this
0x18004d15e  test    eax, eax
0x18004d160  jns     short loc_18004D177
0x18004d162  mov     r9d, eax; char *
0x18004d165  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d16c  mov     edx, 564h; void *
0x18004d171  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d177  mov     rcx, [rsp+388h+string]; string
0x18004d17c  call    cs:__imp_WindowsDeleteString
0x18004d182  mov     [rsp+388h+string], rsi
0x18004d187  lea     r9, [rsp+388h+string]; HSTRING *
0x18004d18c  lea     r8, PKEY_Identity_PrimarySid; struct _tagpropertykey *
0x18004d193  mov     rdx, [rsp+388h+var_330]; struct IPropertyStore *
0x18004d198  call    ?GetPropertyAsString@UserProfile@Internal@System@Windows@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserProfile::GetPropertyAsString(IPropertyStore *,_tagpropertykey const &,HSTRING__ * *)
0x18004d19d  mov     rcx, [rsp+388h]; this
0x18004d1a5  test    eax, eax
0x18004d1a7  jns     short loc_18004D1BE
0x18004d1a9  mov     r9d, eax; char *
0x18004d1ac  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d1b3  mov     edx, 565h; void *
0x18004d1b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d1be  mov     rcx, [rsp+388h+var_340]; string
0x18004d1c3  call    cs:__imp_WindowsDeleteString
0x18004d1c9  mov     [rsp+388h+var_340], rsi
0x18004d1ce  lea     r9, [rsp+388h+var_340]; HSTRING *
0x18004d1d3  lea     r8, PKEY_Identity_UserName; struct _tagpropertykey *
0x18004d1da  mov     rdx, [rsp+388h+var_330]; struct IPropertyStore *
0x18004d1df  call    ?GetPropertyAsString@UserProfile@Internal@System@Windows@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserProfile::GetPropertyAsString(IPropertyStore *,_tagpropertykey const &,HSTRING__ * *)
0x18004d1e4  mov     rcx, [rsp+388h]; this
0x18004d1ec  test    eax, eax
0x18004d1ee  jns     short loc_18004D205
0x18004d1f0  mov     r9d, eax; char *
0x18004d1f3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d1fa  mov     edx, 566h; void *
0x18004d1ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d205  call    ?IsWindowsCoreUserModelEnforced@@YA_NXZ; IsWindowsCoreUserModelEnforced(void)
0x18004d20a  mov     dil, al
0x18004d20d  test    al, al
0x18004d20f  jz      loc_18004D3BD
0x18004d215  lea     rax, [rsp+388h+var_308]
0x18004d21d  mov     [rsp+388h+var_2F8], rax
0x18004d225  mov     [rsp+388h+PolicyHandle], rsi
0x18004d22d  mov     [rsp+388h+var_2E8], 1
0x18004d235  lea     r9, [rsp+388h+PolicyHandle]; PolicyHandle
0x18004d23d  mov     r8d, 801h; DesiredAccess
0x18004d243  lea     rdx, [rsp+388h+ObjectAttributes]; ObjectAttributes
0x18004d24b  call    LsaOpenPolicy
0x18004d250  mov     rcx, [rsp+388h]; this
0x18004d258  test    eax, eax
0x18004d25a  jns     short loc_18004D271
0x18004d25c  mov     r9d, eax; char *
0x18004d25f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d266  mov     edx, 571h; void *
0x18004d26b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004d271  lea     rcx, [rsp+388h+var_2F8]
0x18004d279  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18004d27e  xor     edx, edx; length
0x18004d280  mov     rcx, [rsp+388h+string]; string
0x18004d285  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d28b  mov     rbx, rax
0x18004d28e  xor     edx, edx
0x18004d290  lea     rcx, [rsp+388h+Sid]
0x18004d295  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004d29a  lea     rdx, [rsp+388h+Sid]; Sid
0x18004d29f  mov     rcx, rbx; StringSid
0x18004d2a2  call    cs:__imp_ConvertStringSidToSidW
0x18004d2a8  mov     rcx, [rsp+388h]; this
0x18004d2b0  test    eax, eax
0x18004d2b2  jnz     short loc_18004D2C6
0x18004d2b4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d2bb  mov     edx, 574h; void *
0x18004d2c0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004d2c6  mov     rax, [rsp+388h+Sid]
0x18004d2cb  mov     qword ptr [rsp+388h+var_2B0.Data1], rax
0x18004d2d3  lea     rax, [rsp+388h+hMem]
0x18004d2d8  mov     [rsp+388h+var_280], rax
0x18004d2e0  mov     [rsp+388h+var_278], rsi
0x18004d2e8  mov     [rsp+388h+var_270], 1
0x18004d2f0  lea     rax, [rsp+388h+var_300]
0x18004d2f8  mov     [rsp+388h+var_2F8], rax
0x18004d300  mov     [rsp+388h+PolicyHandle], rsi
0x18004d308  mov     [rsp+388h+var_2E8], 1
0x18004d310  lea     rax, [rsp+388h+var_278]
0x18004d318  mov     [rsp+388h+var_360], rax
0x18004d31d  lea     rax, [rsp+388h+PolicyHandle]
0x18004d325  mov     [rsp+388h+ppv], rax; int
0x18004d32a  lea     r9, [rsp+388h+var_2B0]
0x18004d332  xor     edx, edx
0x18004d334  mov     rcx, [rsp+388h+var_308]
0x18004d33c  call    LsapLookupSids
0x18004d341  mov     rcx, [rsp+388h]; this
0x18004d349  test    eax, eax
0x18004d34b  jns     short loc_18004D362
0x18004d34d  mov     r9d, eax; char *
0x18004d350  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d357  mov     edx, 57Ch; void *
0x18004d35c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004d362  lea     rcx, [rsp+388h+var_2F8]
0x18004d36a  call    ??1?$out_param_t@V?$unique_ptr@U_LSA_REFERENCED_DOMAIN_LIST@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>(void)
0x18004d36f  nop
0x18004d370  lea     rcx, [rsp+388h+var_280]
0x18004d378  call    ??1?$out_param_t@V?$unique_ptr@U_LSA_REFERENCED_DOMAIN_LIST@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>(void)
0x18004d37d  mov     rdx, [rsp+388h+hMem]
0x18004d382  movzx   r8d, word ptr [rdx+8]
0x18004d387  shr     r8, 1
0x18004d38a  mov     rdx, [rdx+10h]
0x18004d38e  lea     rcx, [rsp+388h+var_280]
0x18004d396  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG_K@Z; std::wstring::wstring(ushort const *,unsigned __int64)
0x18004d39b  mov     rdx, rax
0x18004d39e  lea     rcx, [rsp+388h+var_2A0]
0x18004d3a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18004d3ab  xor     r8d, r8d
0x18004d3ae  mov     dl, 1
0x18004d3b0  lea     rcx, [rsp+388h+var_280]
0x18004d3b8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004d3bd  mov     r15, [rsp+388h+var_310]
0x18004d3c2  mov     rax, [r15]
0x18004d3c5  mov     r12, [rax+28h]
0x18004d3c9  test    dil, dil
0x18004d3cc  jz      short loc_18004D3EA
0x18004d3ce  lea     rbx, [rsp+388h+var_2A0]
0x18004d3d6  cmp     [rsp+388h+var_288], 8
0x18004d3df  cmovnb  rbx, [rsp+388h+var_2A0]
0x18004d3e8  jmp     short loc_18004D3FA
0x18004d3ea  xor     edx, edx; length
0x18004d3ec  mov     rcx, [rsp+388h+var_340]; string
0x18004d3f1  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d3f7  mov     rbx, rax
0x18004d3fa  xor     edx, edx; length
0x18004d3fc  mov     rcx, [rsp+388h+string]; string
0x18004d401  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d407  mov     dword ptr [rsp+388h+ppv], 104h; int
0x18004d40f  lea     r9, [rsp+388h+var_258]
0x18004d417  mov     r8, rbx
0x18004d41a  mov     rdx, rax
0x18004d41d  mov     rcx, r15
0x18004d420  mov     rax, r12
0x18004d423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d428  mov     edx, 80000000h
0x18004d42d  lea     ecx, [rax+rdx]
0x18004d430  test    edx, ecx
0x18004d432  jnz     short loc_18004D43D
0x18004d434  cmp     eax, 800700B7h
0x18004d439  mov     cl, 1
0x18004d43b  jnz     short loc_18004D440
0x18004d43d  mov     cl, sil
0x18004d440  mov     r10, [rsp+388h]
0x18004d448  test    cl, cl
0x18004d44a  jz      short loc_18004D464
0x18004d44c  mov     r9d, eax; char *
0x18004d44f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d456  mov     edx, 586h; void *
0x18004d45b  mov     rcx, r10; this
0x18004d45e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d464  mov     rbx, [rsp+388h+var_340]
0x18004d469  mov     [rsp+388h+var_340], rsi
0x18004d46e  mov     rcx, [r14+58h]; string
0x18004d472  call    cs:__imp_WindowsDeleteString
0x18004d478  mov     [r14+58h], rbx
0x18004d47c  mov     rbx, [rsp+388h+string]
0x18004d481  mov     [rsp+388h+string], rsi
0x18004d486  mov     rcx, [r14+78h]; string
0x18004d48a  call    cs:__imp_WindowsDeleteString
0x18004d490  mov     [r14+78h], rbx
0x18004d494  lea     rcx, [rsp+388h+var_308]
0x18004d49c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004d4a1  nop
0x18004d4a2  lea     rcx, [rsp+388h+Sid]
0x18004d4a7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004d4ac  nop
0x18004d4ad  mov     rcx, [rsp+388h+hMem]; hMem
0x18004d4b2  mov     [rsp+388h+hMem], rsi
0x18004d4b7  test    rcx, rcx
0x18004d4ba  jz      short loc_18004D4C3
0x18004d4bc  call    cs:__imp_LocalFree
0x18004d4c2  nop
0x18004d4c3  mov     rcx, [rsp+388h+var_300]; hMem
0x18004d4cb  mov     [rsp+388h+var_300], rsi
0x18004d4d3  test    rcx, rcx
0x18004d4d6  jz      short loc_18004D4DF
0x18004d4d8  call    cs:__imp_LocalFree
0x18004d4de  nop
0x18004d4df  xor     r8d, r8d
0x18004d4e2  mov     dl, 1
0x18004d4e4  lea     rcx, [rsp+388h+var_2A0]
0x18004d4ec  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004d4f1  nop
0x18004d4f2  mov     rcx, [rsp+388h+var_340]; string
0x18004d4f7  call    cs:__imp_WindowsDeleteString
0x18004d4fd  mov     [rsp+388h+var_340], rsi
0x18004d502  mov     rcx, [rsp+388h+string]; string
  ... truncated ...
```
