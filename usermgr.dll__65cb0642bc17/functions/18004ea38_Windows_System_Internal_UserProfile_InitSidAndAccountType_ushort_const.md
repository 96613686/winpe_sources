# Windows::System::Internal::UserProfile::InitSidAndAccountType(ushort const *)

- ea: `0x18004ea38`
- end: `0x18004eeeb`
- name: `?InitSidAndAccountType@UserProfile@Internal@System@Windows@@AEAAJPEBG@Z`
- size: `1203`
- prototype: `int(Windows::System::Internal::UserProfile *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ce190`
- `0x1800cef78`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180014e7c`
- `0x1800154b0`
- `0x180015540`
- `0x1800181f0`
- `0x180018b60`
- `0x18003322c`
- `0x180041fc0`
- `0x18004bed4`
- `0x18004bf50`
- `0x18004d710`
- `0x18004e4e8`
- `0x18004e508`
- `0x18004e58c`
- `0x18004ea38`
- `0x1800da968`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18004eb53`
- `msvcrt!_wcsnicmp` at `0x18004eb53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ecd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ecd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004ec66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004ecaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004ec66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004ecaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ec4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ec91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ee34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ee44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ec4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ec91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ee34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ee44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004ead3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004ead3`
- `ntdll!RtlInitUnicodeString` at `0x18004ece4`
- `ntdll!RtlInitUnicodeString` at `0x18004ece4`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18004ea9f`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18004eb13`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18004ea9f`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18004eb13`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18004ed57`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18004ed57`

## string_xrefs

- `0x18004eab8`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004eaf2`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004eb27`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004ec21`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004ec7a`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004ecbe`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004ed6b`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004edc5`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004ee02`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004eed9`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::System::Internal::UserProfile::InitSidAndAccountType(
        Windows::System::Internal::UserProfile *this,
        const unsigned __int16 *a2)
{
  unsigned int IdentityProviderInfoByGUID; // eax
  const WCHAR **v5; // rax
  const WCHAR **v6; // rsi
  unsigned int v7; // eax
  const wchar_t *v8; // rdx
  size_t v9; // r8
  char v10; // di
  void (__fastcall *v11)(void *, __int64 *); // rbx
  PLSA_UNICODE_STRING v12; // rcx
  NTSTATUS v13; // eax
  const WCHAR *StringRawBuffer; // rdx
  HRESULT v15; // eax
  HRESULT v16; // eax
  ULONG v17; // edx
  ULONG v18; // r8d
  NTSTATUS v19; // ebx
  int v20; // eax
  __int64 v21; // rdi
  unsigned int (__fastcall *v22)(__int64, _QWORD, const WCHAR **); // rbx
  const char *v23; // r9
  const WCHAR *v24; // rax
  int v25; // eax
  HLOCAL v26; // rcx
  HLOCAL v27; // rcx
  unsigned int ReferencedDomains; // [rsp+20h] [rbp-E0h]
  int ReferencedDomainsa; // [rsp+20h] [rbp-E0h]
  SIZE_T uBytes; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  LSA_HANDLE v38; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v39; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR *v40; // [rsp+78h] [rbp-88h] BYREF
  LSA_HANDLE *v41; // [rsp+80h] [rbp-80h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp-78h] BYREF
  char v43; // [rsp+90h] [rbp-70h]
  const WCHAR **v44; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL *p_hMem; // [rsp+B0h] [rbp-50h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+B8h] [rbp-48h] BYREF
  char v48; // [rsp+C0h] [rbp-40h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING string2; // [rsp+110h] [rbp+10h]
  HSTRING_HEADER v52; // [rsp+118h] [rbp+18h] BYREF
  HSTRING string1; // [rsp+130h] [rbp+30h]
  HSTRING_HEADER v54; // [rsp+138h] [rbp+38h] BYREF
  HSTRING v55; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v40 = a2;
  *((_BYTE *)this + 80) = 0;
  LODWORD(uBytes) = 0;
  v36 = 0;
  v44 = 0;
  v39 = 0;
  hMem = 0;
  v34 = 0;
  IdentityProviderInfoByGUID = GetIdentityProviderInfoByGUID(qword_18010BA68, 0, &uBytes);
  if ( IdentityProviderInfoByGUID != 122 && IdentityProviderInfoByGUID )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)IdentityProviderInfoByGUID,
      ReferencedDomains);
  v5 = (const WCHAR **)LocalAlloc(0x40u, (unsigned int)uBytes);
  v6 = v5;
  v44 = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A7,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)0x8007000ELL,
      ReferencedDomains);
  v7 = GetIdentityProviderInfoByGUID(qword_18010BA68, v5, &uBytes);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4A9,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v7,
      ReferencedDomains);
  v8 = v6[1];
  if ( !v8 )
    goto LABEL_12;
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  v10 = 1;
  if ( _wcsnicmp(a2, v8, v9) )
LABEL_12:
    v10 = 0;
  v37 = 0;
  v11 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v11(&Windows::System::Internal::Adapters::g_AdapterCollection, &v37);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v54, &v40);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v52, v6 + 1);
  string2 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"\\", 2u, 1u);
  string = 0;
  newString = 0;
  DestinationString = 0;
  v38 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v41 = &v38;
  PolicyHandle = 0;
  v43 = 1;
  v13 = LsaOpenPolicy(v12, &ObjectAttributes, 0x801u, &PolicyHandle);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4C1,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v13,
      ReferencedDomains);
  wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v41);
  if ( v10 )
  {
    StringRawBuffer = a2;
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    v15 = WindowsConcatString(string1, string2, &string);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v15,
        ReferencedDomains);
    WindowsDeleteString(newString);
    newString = 0;
    v16 = WindowsConcatString(string, v55, &newString);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4CA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v16,
        ReferencedDomains);
    StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
  }
  RtlInitUnicodeString(&DestinationString, StringRawBuffer);
  p_hMem = &hMem;
  Sids = 0;
  v48 = 1;
  v41 = &v39;
  PolicyHandle = 0;
  v43 = 1;
  v19 = LsaLookupNames2(
          v38,
          v17,
          v18,
          (PLSA_UNICODE_STRING)&DestinationString,
          (PLSA_REFERENCED_DOMAIN_LIST *)&PolicyHandle,
          &Sids);
  wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>(&v41);
  wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>(&p_hMem);
  if ( v19 < 0 )
  {
    if ( v19 != -1073741709 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x4E6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v19,
        ReferencedDomainsa);
    *((_BYTE *)this + 80) = 0;
  }
  else
  {
    v20 = LsaLookupUserAccountType(*((_QWORD *)hMem + 1), &v34);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x4DA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v20,
        ReferencedDomainsa);
    *((_BYTE *)this + 80) = v34 == 5;
    v21 = v37;
    v22 = *(unsigned int (__fastcall **)(__int64, _QWORD, const WCHAR **))(*(_QWORD *)v37 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v36,
      0);
    if ( !v22(v21, *((_QWORD *)hMem + 1), &v36) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x4DD,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        v23);
    v24 = v36;
    v36 = 0;
    v40 = v24;
    v25 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((HSTRING *)this + 15);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DE,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v25,
        ReferencedDomainsa);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(string);
  string = 0;
  string2 = 0;
  string1 = 0;
  v55 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v26 = hMem;
  hMem = 0;
  if ( v26 )
    LocalFree(v26);
  v27 = v39;
  v39 = 0;
  if ( v27 )
    LocalFree(v27);
  LocalFree(v6);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v36);
  return 0;
}

```

## disassembly

```asm
0x18004ea38  mov     [rsp-8+arg_10], rbx
0x18004ea3d  push    rbp
0x18004ea3e  push    rsi
0x18004ea3f  push    rdi
0x18004ea40  push    r12
0x18004ea42  push    r13
0x18004ea44  push    r14
0x18004ea46  push    r15
0x18004ea48  lea     rbp, [rsp-60h]
0x18004ea4d  sub     rsp, 160h
0x18004ea54  mov     rax, cs:__security_cookie
0x18004ea5b  xor     rax, rsp
0x18004ea5e  mov     [rbp+90h+var_38], rax
0x18004ea62  mov     r15, rdx
0x18004ea65  mov     r14, rcx
0x18004ea68  mov     [rsp+190h+var_118], rdx
0x18004ea6d  xor     r13d, r13d
0x18004ea70  mov     [rcx+50h], r13b
0x18004ea74  mov     dword ptr [rsp+190h+uBytes], r13d
0x18004ea79  mov     [rsp+190h+var_138], r13
0x18004ea7e  mov     [rbp+90h+var_F8], r13
0x18004ea82  mov     [rsp+190h+var_120], r13
0x18004ea87  mov     [rsp+190h+hMem], r13
0x18004ea8c  mov     [rsp+190h+var_148], r13d
0x18004ea91  lea     r8, [rsp+190h+uBytes]
0x18004ea96  xor     edx, edx
0x18004ea98  lea     rcx, qword_18010BA68
0x18004ea9f  call    cs:__imp_GetIdentityProviderInfoByGUID
0x18004eaa5  cmp     eax, 7Ah ; 'z'
0x18004eaa8  jz      short loc_18004EACA
0x18004eaaa  mov     rcx, [rbp+98h]; this
0x18004eab1  test    eax, eax
0x18004eab3  jz      short loc_18004EACA
0x18004eab5  mov     r9d, eax; char *
0x18004eab8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004eabf  mov     edx, 4A3h; void *
0x18004eac4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004eaca  mov     edx, dword ptr [rsp+190h+uBytes]; uBytes
0x18004eace  mov     ecx, 40h ; '@'; uFlags
0x18004ead3  call    cs:__imp_LocalAlloc
0x18004ead9  mov     rsi, rax
0x18004eadc  mov     [rbp+90h+var_F8], rax
0x18004eae0  mov     rcx, [rbp+98h]; this
0x18004eae7  test    rax, rax
0x18004eaea  jnz     short loc_18004EB04
0x18004eaec  mov     r9d, 8007000Eh; char *
0x18004eaf2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004eaf9  mov     edx, 4A7h; void *
0x18004eafe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb04  lea     r8, [rsp+190h+uBytes]
0x18004eb09  mov     rdx, rsi
0x18004eb0c  lea     rcx, qword_18010BA68
0x18004eb13  call    cs:__imp_GetIdentityProviderInfoByGUID
0x18004eb19  mov     rcx, [rbp+98h]; this
0x18004eb20  test    eax, eax
0x18004eb22  jz      short loc_18004EB39
0x18004eb24  mov     r9d, eax; char *
0x18004eb27  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004eb2e  mov     edx, 4A9h; void *
0x18004eb33  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004eb39  mov     rdx, [rsi+8]; String2
0x18004eb3d  test    rdx, rdx
0x18004eb40  jz      short loc_18004EB60
0x18004eb42  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004eb46  inc     r8; MaxCount
0x18004eb49  cmp     [rdx+r8*2], r13w
0x18004eb4e  jnz     short loc_18004EB46
0x18004eb50  mov     rcx, r15; String1
0x18004eb53  call    cs:__imp__wcsnicmp
0x18004eb59  test    eax, eax
0x18004eb5b  mov     dil, 1
0x18004eb5e  jz      short loc_18004EB63
0x18004eb60  mov     dil, r13b
0x18004eb63  mov     [rsp+190h+var_130], r13
0x18004eb68  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004eb6f  mov     rbx, [rax+38h]
0x18004eb73  lea     rcx, [rsp+190h+var_130]
0x18004eb78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004eb7d  lea     rdx, [rsp+190h+var_130]
0x18004eb82  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004eb89  mov     rax, rbx
0x18004eb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb91  lea     rdx, [rsp+190h+var_118]
0x18004eb96  lea     rcx, [rbp+90h+var_58]
0x18004eb9a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004eb9f  nop
0x18004eba0  lea     rdx, [rsi+8]
0x18004eba4  lea     rcx, [rbp+90h+var_78]
0x18004eba8  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004ebad  nop
0x18004ebae  mov     [rbp+90h+string2], r13
0x18004ebb2  mov     r9d, 1; unsigned int
0x18004ebb8  lea     r8d, [r9+1]; unsigned int
0x18004ebbc  lea     rdx, SubStr; "\\"
0x18004ebc3  lea     rcx, [rbp+90h+hstringHeader]; hstringHeader
0x18004ebc7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004ebcc  nop
0x18004ebcd  mov     [rsp+190h+string], r13
0x18004ebd2  mov     [rsp+190h+newString], r13
0x18004ebd7  xorps   xmm0, xmm0
0x18004ebda  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18004ebde  mov     [rsp+190h+var_128], r13
0x18004ebe3  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x18004ebe7  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x18004ebeb  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004ebef  lea     rax, [rsp+190h+var_128]
0x18004ebf4  mov     [rbp+90h+var_110], rax
0x18004ebf8  mov     [rbp+90h+PolicyHandle], r13
0x18004ebfc  mov     [rbp+90h+var_100], 1
0x18004ec00  lea     r9, [rbp+90h+PolicyHandle]; PolicyHandle
0x18004ec04  mov     r8d, 801h; DesiredAccess
0x18004ec0a  lea     rdx, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18004ec0e  call    LsaOpenPolicy
0x18004ec13  mov     rcx, [rbp+98h]; this
0x18004ec1a  test    eax, eax
0x18004ec1c  jns     short loc_18004EC33
0x18004ec1e  mov     r9d, eax; char *
0x18004ec21  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ec28  mov     edx, 4C1h; void *
0x18004ec2d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004ec33  lea     rcx, [rbp+90h+var_110]
0x18004ec37  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18004ec3c  test    dil, dil
0x18004ec3f  jz      short loc_18004EC49
0x18004ec41  mov     rdx, r15
0x18004ec44  jmp     loc_18004ECE0
0x18004ec49  mov     rcx, [rsp+190h+string]; string
0x18004ec4e  call    cs:__imp_WindowsDeleteString
0x18004ec54  mov     [rsp+190h+string], r13
0x18004ec59  lea     r8, [rsp+190h+string]; newString
0x18004ec5e  mov     rdx, [rbp+90h+string2]; string2
0x18004ec62  mov     rcx, [rbp+90h+string1]; string1
0x18004ec66  call    cs:__imp_WindowsConcatString
0x18004ec6c  mov     rcx, [rbp+98h]; this
0x18004ec73  test    eax, eax
0x18004ec75  jns     short loc_18004EC8C
0x18004ec77  mov     r9d, eax; char *
0x18004ec7a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ec81  mov     edx, 4C9h; void *
0x18004ec86  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ec8c  mov     rcx, [rsp+190h+newString]; string
0x18004ec91  call    cs:__imp_WindowsDeleteString
0x18004ec97  mov     [rsp+190h+newString], r13
0x18004ec9c  lea     r8, [rsp+190h+newString]; newString
0x18004eca1  mov     rdx, [rbp+90h+var_40]; string2
0x18004eca5  mov     rcx, [rsp+190h+string]; string1
0x18004ecaa  call    cs:__imp_WindowsConcatString
0x18004ecb0  mov     rcx, [rbp+98h]; this
0x18004ecb7  test    eax, eax
0x18004ecb9  jns     short loc_18004ECD0
0x18004ecbb  mov     r9d, eax; char *
0x18004ecbe  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ecc5  mov     edx, 4CAh; void *
0x18004ecca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ecd0  xor     edx, edx; length
0x18004ecd2  mov     rcx, [rsp+190h+newString]; string
0x18004ecd7  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ecdd  mov     rdx, rax; SourceString
0x18004ece0  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x18004ece4  call    cs:__imp_RtlInitUnicodeString
0x18004ecea  lea     rax, [rsp+190h+hMem]
0x18004ecef  mov     [rbp+90h+var_E0], rax
0x18004ecf3  mov     [rbp+90h+var_D8], r13
0x18004ecf7  mov     [rbp+90h+var_D0], 1
0x18004ecfb  lea     rax, [rsp+190h+var_120]
0x18004ed00  mov     [rbp+90h+var_110], rax
0x18004ed04  mov     [rbp+90h+PolicyHandle], r13
0x18004ed08  mov     [rbp+90h+var_100], 1
0x18004ed0c  lea     rax, [rbp+90h+var_D8]
0x18004ed10  mov     [rsp+190h+Sids], rax; Sids
0x18004ed15  lea     rax, [rbp+90h+PolicyHandle]
0x18004ed19  mov     [rsp+190h+ReferencedDomains], rax; int
0x18004ed1e  lea     r9, [rbp+90h+DestinationString]; Names
0x18004ed22  mov     rcx, [rsp+190h+var_128]; PolicyHandle
0x18004ed27  call    LsaLookupNames2
0x18004ed2c  mov     ebx, eax
0x18004ed2e  lea     rcx, [rbp+90h+var_110]
0x18004ed32  call    ??1?$out_param_t@V?$unique_ptr@U_LSA_REFERENCED_DOMAIN_LIST@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>(void)
0x18004ed37  nop
0x18004ed38  lea     rcx, [rbp+90h+var_E0]
0x18004ed3c  call    ??1?$out_param_t@V?$unique_ptr@U_LSA_REFERENCED_DOMAIN_LIST@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&LsaFreeMemory(void *)>>>(void)
0x18004ed41  test    ebx, ebx
0x18004ed43  js      loc_18004EE14
0x18004ed49  lea     rdx, [rsp+190h+var_148]
0x18004ed4e  mov     rcx, [rsp+190h+hMem]
0x18004ed53  mov     rcx, [rcx+8]
0x18004ed57  call    cs:__imp_LsaLookupUserAccountType
0x18004ed5d  mov     rcx, [rbp+98h]; this
0x18004ed64  test    eax, eax
0x18004ed66  jns     short loc_18004ED7D
0x18004ed68  mov     r9d, eax; char *
0x18004ed6b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ed72  mov     edx, 4DAh; void *
0x18004ed77  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004ed7d  cmp     [rsp+190h+var_148], 5
0x18004ed82  setz    al
0x18004ed85  mov     [r14+50h], al
0x18004ed89  mov     rdi, [rsp+190h+var_130]
0x18004ed8e  mov     rax, [rdi]
0x18004ed91  mov     rbx, [rax+20h]
0x18004ed95  xor     edx, edx
0x18004ed97  lea     rcx, [rsp+190h+var_138]
0x18004ed9c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004eda1  lea     r8, [rsp+190h+var_138]
0x18004eda6  mov     rdx, [rsp+190h+hMem]
0x18004edab  mov     rdx, [rdx+8]
0x18004edaf  mov     rcx, rdi
0x18004edb2  mov     rax, rbx
0x18004edb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edba  mov     rcx, [rbp+98h]; this
0x18004edc1  test    eax, eax
0x18004edc3  jnz     short loc_18004EDD7
0x18004edc5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004edcc  mov     edx, 4DDh; void *
0x18004edd1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004edd7  mov     rax, [rsp+190h+var_138]
0x18004eddc  mov     [rsp+190h+var_138], r13
0x18004ede1  mov     [rsp+190h+var_118], rax
0x18004ede6  lea     rcx, [r14+78h]; string
0x18004edea  lea     rdx, [rsp+190h+var_118]
0x18004edef  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004edf4  mov     rcx, [rbp+98h]; this
0x18004edfb  test    eax, eax
0x18004edfd  jns     short loc_18004EE24
0x18004edff  mov     r9d, eax; char *
0x18004ee02  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ee09  mov     edx, 4DEh; void *
0x18004ee0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ee14  cmp     ebx, 0C0000073h
0x18004ee1a  jnz     loc_18004EECF
0x18004ee20  mov     [r14+50h], r13b
0x18004ee24  lea     rcx, [rsp+190h+var_128]
0x18004ee29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004ee2e  nop
0x18004ee2f  mov     rcx, [rsp+190h+newString]; string
0x18004ee34  call    cs:__imp_WindowsDeleteString
0x18004ee3a  mov     [rsp+190h+newString], r13
0x18004ee3f  mov     rcx, [rsp+190h+string]; string
0x18004ee44  call    cs:__imp_WindowsDeleteString
0x18004ee4a  mov     [rsp+190h+string], r13
0x18004ee4f  mov     [rbp+90h+string2], r13
0x18004ee53  mov     [rbp+90h+string1], r13
0x18004ee57  mov     [rbp+90h+var_40], r13
0x18004ee5b  lea     rcx, [rsp+190h+var_130]
0x18004ee60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ee65  nop
0x18004ee66  mov     rcx, [rsp+190h+hMem]; hMem
0x18004ee6b  mov     [rsp+190h+hMem], r13
0x18004ee70  test    rcx, rcx
0x18004ee73  jz      short loc_18004EE7C
0x18004ee75  call    cs:__imp_LocalFree
0x18004ee7b  nop
0x18004ee7c  mov     rcx, [rsp+190h+var_120]; hMem
0x18004ee81  mov     [rsp+190h+var_120], r13
0x18004ee86  test    rcx, rcx
0x18004ee89  jz      short loc_18004EE92
0x18004ee8b  call    cs:__imp_LocalFree
0x18004ee91  nop
0x18004ee92  mov     rcx, rsi; hMem
0x18004ee95  call    cs:__imp_LocalFree
0x18004ee9b  nop
0x18004ee9c  lea     rcx, [rsp+190h+var_138]
0x18004eea1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004eea6  xor     eax, eax
0x18004eea8  mov     rcx, [rbp+90h+var_38]
0x18004eeac  xor     rcx, rsp; StackCookie
0x18004eeaf  call    __security_check_cookie
0x18004eeb4  mov     rbx, [rsp+190h+arg_10]
0x18004eebc  add     rsp, 160h
0x18004eec3  pop     r15
0x18004eec5  pop     r14
0x18004eec7  pop     r13
0x18004eec9  pop     r12
0x18004eecb  pop     rdi
0x18004eecc  pop     rsi
0x18004eecd  pop     rbp
0x18004eece  retn
0x18004eecf  mov     rcx, [rbp+98h]; this
0x18004eed6  mov     r9d, ebx; char *
0x18004eed9  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004eee0  mov     edx, 4E6h; void *
0x18004eee5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
