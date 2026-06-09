# PrepareUWPActivation(ushort *,void *,ushort * *,ushort * *,int *)

- ea: `0x18006bbe4`
- end: `0x18006c485`
- name: `?PrepareUWPActivation@@YAJPEAGPEAXPEAPEAG2PEAH@Z`
- size: `2209`
- prototype: `__int64 __fastcall(unsigned __int16 *, PSID Sid, HLOCAL *, HLOCAL *, int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004cd64`
- `0x1800507c0`

## callees

- `0x18000b310`
- `0x18000bbe8`
- `0x18001ec28`
- `0x180024cc4`
- `0x18002ba28`
- `0x18002f058`
- `0x1800320b0`
- `0x1800320d4`
- `0x18006b5a4`
- `0x18006bbe4`
- `0x18006c48c`
- `0x18006c588`
- `0x18006c5c0`
- `0x18006ca54`
- `0x18007ea58`
- `0x18008eefc`
- `0x1800b27e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18006c2e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18006c362`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18006c2e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18006c362`
- `ntdll!wcsstr` at `0x18006c37d`
- `ntdll!wcsstr` at `0x18006c392`
- `ntdll!wcsstr` at `0x18006c37d`
- `ntdll!wcsstr` at `0x18006c392`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006bdb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006bffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006bdb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006bffa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006bcb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006be61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006bcb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006be61`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006bc5b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006bc5b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bcf1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bd7a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bfb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bfc9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006c470`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bcf1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bd7a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bfb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006bfc9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006c470`

## string_xrefs

- `0x18006bddb`: `path:%ls`
- `0x18006be85`: `path:%ls`
- `0x18006bdd4`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18006be91`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18006bd11`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006bd5c`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006bd89`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006bebd`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006bfdf`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c036`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c0a1`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c11a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c18e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c206`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c226`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c2a7`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006c42c`: `onecore\com\combase\rpcss\olescm\launch.cxx`

## pseudocode

```c
__int64 __fastcall PrepareUWPActivation(unsigned __int16 *a1, PSID Sid, HLOCAL *a3, HLOCAL *a4, int *a5)
{
  int v8; // esi
  int v9; // eax
  unsigned int LastError; // ebx
  const char *v11; // r9
  int v12; // eax
  LSTATUS v13; // eax
  void *v14; // rdx
  void *v16; // rdx
  int StringValue; // eax
  LSTATUS v18; // eax
  signed int v19; // edi
  void *v20; // rdx
  HLOCAL v21; // rbx
  HKEY v22; // rax
  char *v23; // r14
  wchar_t *v24; // rbx
  void *v25; // rdx
  void *v26; // rdx
  void *v27; // rdx
  signed int v28; // eax
  int v29; // eax
  int v30; // eax
  unsigned int v31; // esi
  __int64 v32; // rdx
  unsigned __int16 *i; // rsi
  int v34; // r14d
  __int64 v35; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResultd; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL v43; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v48; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t SubStr[264]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  *a3 = 0;
  *a4 = 0;
  hObject = (HANDLE)-1LL;
  *a5 = 0;
  v8 = (int)a1;
  v9 = wil::impersonate_token_nothrow(a1, &hObject);
  LastError = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x394,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)v9,
      phkResult);
LABEL_15:
    if ( hObject != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(hObject, v16);
    return LastError;
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x398,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                  v11);
LABEL_19:
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_15;
  }
  v12 = StringCchPrintfW(
          SubKey,
          0x104u,
          L"%s\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PackagedAppXDebug\\%s",
          StringSid);
  LastError = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x399,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)v12,
      v8);
    goto LABEL_19;
  }
  hKey = 0;
  v13 = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20019u, &hKey);
  LastError = v13;
  if ( v13 > 0 )
    LastError = (unsigned __int16)v13 | 0x80070000;
  if ( LastError == -2147024894 )
  {
LABEL_7:
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
LABEL_11:
    if ( hObject != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(hObject, v14);
    return 0;
  }
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x10E,
    (unsigned int)"onecore\\com\\combase\\inc\\RegistryKey.hpp",
    (const char *)LastError,
    (__int64)"path:%ls",
    (const char *)SubKey);
  if ( (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)LastError,
      phkResulta);
    goto LABEL_50;
  }
  hMem = 0;
  v43 = 0;
  LOBYTE(v41) = 0;
  StringValue = RegistryKey::ReadStringValueWorker<0,unsigned short *>(
                  (RegistryKey *)&hKey,
                  (char *)&Class,
                  2u,
                  (__int64)&v41);
  LastError = StringValue;
  if ( StringValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A9,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)StringValue,
      phkResultb);
    goto LABEL_49;
  }
  v47 = 0;
  v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Ole\\Debug", 0, 0x20019u, &v47);
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  if ( v19 == -2147024894 )
    goto LABEL_34;
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x10E,
    (unsigned int)"onecore\\com\\combase\\inc\\RegistryKey.hpp",
    (const char *)(unsigned int)v19,
    (__int64)"path:%ls",
    (const char *)L"SOFTWARE\\Microsoft\\Ole\\Debug");
  if ( v19 < 0 )
  {
LABEL_28:
    if ( v19 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3DD,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)v19,
        phkResultc);
LABEL_30:
      RegistryKey::Close((RegistryKey *)&v47);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
      RegistryKey::Close((RegistryKey *)&hKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      if ( hObject != (HANDLE)-1LL )
        wil::details::RevertImpersonateToken(hObject, v20);
      return (unsigned int)v19;
    }
LABEL_34:
    v21 = hMem;
    if ( hMem )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v50);
      LocalFree(v21);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v50);
    }
    hMem = 0;
    LOBYTE(v41) = 0;
    LastError = RegistryKey::ReadStringValueWorker<0,unsigned short *>(
                  (RegistryKey *)&hKey,
                  (char *)L"DebuggerEnvironment",
                  0x20u,
                  (__int64)&v41);
    if ( (int)(LastError + 0x80000000) < 0 || LastError == -2147024894 )
    {
      *a4 = hMem;
      *a3 = v43;
      v22 = v47;
      hMem = 0;
      v43 = 0;
      *a5 = 1;
      if ( v22 )
      {
        RegCloseKey(v47);
        v47 = 0;
      }
      if ( hMem )
        LocalFree(hMem);
      if ( v43 )
        LocalFree(v43);
      goto LABEL_7;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)LastError,
      phkResultd);
    goto LABEL_48;
  }
  v48 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v48,
    0);
  LOBYTE(v41) = 0;
  v28 = RegistryKey::ReadStringValueWorker<0,unsigned short *>(
          (RegistryKey *)&v47,
          (char *)L"NonNativeDebuggerExclusionList",
          0x20u,
          (__int64)&v41);
  String = 0;
  v19 = v28;
  v29 = StringCchLengthW((const unsigned __int16 *)v43, 0x7FFFFFFFu, (unsigned __int64 *)&String);
  LastError = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C4,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)v29,
      phkResultc);
    goto LABEL_47;
  }
  v23 = (char *)String + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &String,
    v43,
    (char *)String + 1);
  v24 = String;
  if ( !String )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C6,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)0x8007000ELL,
      phkResultc);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
LABEL_47:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
LABEL_48:
    RegistryKey::Close((RegistryKey *)&v47);
LABEL_49:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
LABEL_50:
    RegistryKey::Close((RegistryKey *)&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_15;
  }
  v30 = StringCchCopyW(String, (unsigned __int64)v23, (const unsigned __int16 *)v43);
  v31 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C7,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)v30,
      phkResultc);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
    RegistryKey::Close((RegistryKey *)&v47);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
    RegistryKey::Close((RegistryKey *)&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    if ( hObject != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(hObject, v27);
    return v31;
  }
  if ( !_wcslwr_s(v24, (size_t)v23) )
  {
    if ( v19 >= 0 )
    {
      for ( i = v48; ; i += v50 + 1 )
      {
        if ( !*i )
          goto LABEL_33;
        v50 = 0;
        v34 = StringCchLengthW(i, 0x7FFFFFFFu, &v50);
        if ( v34 < 0 )
          break;
        v34 = StringCchPrintfW(SubStr, 0x104u, L"%s", i);
        if ( v34 < 0 )
        {
          v35 = 977;
LABEL_54:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v35,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)v34,
            phkResultc);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
          RegistryKey::Close((RegistryKey *)&v47);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
          RegistryKey::Close((RegistryKey *)&hKey);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          if ( hObject != (HANDLE)-1LL )
            wil::details::RevertImpersonateToken(hObject, v26);
          return (unsigned int)v34;
        }
        if ( _wcslwr_s(SubStr, 0x104u) )
        {
          v32 = 978;
          goto LABEL_51;
        }
        if ( wcsstr(v24, SubStr) && !wcsstr(v24, L"\\x64\\") )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
          RegistryKey::Close((RegistryKey *)&v47);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
          RegistryKey::Close((RegistryKey *)&hKey);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          goto LABEL_11;
        }
      }
      v35 = 975;
      goto LABEL_54;
    }
    if ( v19 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3DB,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)v19,
        phkResultc);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
      goto LABEL_30;
    }
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
    if ( v19 >= 0 )
      goto LABEL_34;
    goto LABEL_28;
  }
  v32 = 968;
LABEL_51:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v32,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
    (const char *)0x8000FFFFLL,
    phkResultc);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
  RegistryKey::Close((RegistryKey *)&v47);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
  RegistryKey::Close((RegistryKey *)&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  if ( hObject != (HANDLE)-1LL )
    wil::details::RevertImpersonateToken(hObject, v25);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18006bbe4  push    rbp
0x18006bbe6  push    rbx
0x18006bbe7  push    rsi
0x18006bbe8  push    rdi
0x18006bbe9  push    r12
0x18006bbeb  push    r13
0x18006bbed  push    r14
0x18006bbef  push    r15
0x18006bbf1  lea     rbp, [rsp-3B8h]
0x18006bbf9  sub     rsp, 4B8h
0x18006bc00  mov     rax, cs:__security_cookie
0x18006bc07  xor     rax, rsp
0x18006bc0a  mov     [rbp+3F0h+var_50], rax
0x18006bc11  mov     r13, [rbp+3F0h+arg_20]
0x18006bc18  xor     r14d, r14d
0x18006bc1b  mov     [r8], r14
0x18006bc1e  mov     rdi, rdx
0x18006bc21  mov     [r9], r14
0x18006bc24  lea     rdx, [rsp+4F0h+hObject]
0x18006bc29  mov     r12, r9
0x18006bc2c  mov     [rsp+4F0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18006bc35  mov     [r13+0], r14d
0x18006bc39  mov     r15, r8
0x18006bc3c  mov     rsi, rcx
0x18006bc3f  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18006bc44  mov     ebx, eax
0x18006bc46  test    eax, eax
0x18006bc48  js      loc_18006BD0A
0x18006bc4e  lea     rdx, [rsp+4F0h+StringSid]; StringSid
0x18006bc53  mov     [rsp+4F0h+StringSid], r14
0x18006bc58  mov     rcx, rdi; Sid
0x18006bc5b  call    cs:__imp_ConvertSidToStringSidW
0x18006bc61  test    eax, eax
0x18006bc63  jz      loc_18006BD82
0x18006bc69  mov     r9, [rsp+4F0h+StringSid]
0x18006bc6e  lea     r8, aSSoftwareMicro; "%s\\SOFTWARE\\Microsoft\\Windows\\Curre"...
0x18006bc75  mov     edx, 104h; unsigned __int64
0x18006bc7a  mov     [rsp+4F0h+phkResult], rsi; int
0x18006bc7f  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x18006bc83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006bc88  mov     ebx, eax
0x18006bc8a  test    eax, eax
0x18006bc8c  js      loc_18006BD55
0x18006bc92  lea     rax, [rsp+4F0h+hKey]
0x18006bc97  mov     [rsp+4F0h+hKey], r14
0x18006bc9c  mov     edi, 20019h
0x18006bca1  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18006bca6  mov     r9d, edi; samDesired
0x18006bca9  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x18006bcad  xor     r8d, r8d; ulOptions
0x18006bcb0  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18006bcb7  call    cs:__imp_RegOpenKeyExW
0x18006bcbd  mov     ebx, eax
0x18006bcbf  test    eax, eax
0x18006bcc1  jle     short loc_18006BCCC
0x18006bcc3  movzx   ebx, ax
0x18006bcc6  or      ebx, 80070000h
0x18006bccc  mov     esi, 80070002h
0x18006bcd1  cmp     ebx, esi
0x18006bcd3  jnz     loc_18006BDC4
0x18006bcd9  mov     rax, [rsp+4F0h+hKey]
0x18006bcde  test    rax, rax
0x18006bce1  jnz     loc_18006BDAF
0x18006bce7  mov     rcx, [rsp+4F0h+StringSid]; hMem
0x18006bcec  test    rcx, rcx
0x18006bcef  jz      short loc_18006BCF7
0x18006bcf1  call    cs:__imp_LocalFree
0x18006bcf7  mov     rcx, [rsp+4F0h+hObject]; hObject
0x18006bcfc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006bd00  jnz     loc_18006BDA5
0x18006bd06  xor     eax, eax
0x18006bd08  jmp     short loc_18006BD32
0x18006bd0a  mov     rcx, [rbp+3F8h]; this
0x18006bd11  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006bd18  mov     r9d, ebx; char *
0x18006bd1b  mov     edx, 394h; void *
0x18006bd20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bd25  mov     rcx, [rsp+4F0h+hObject]; hObject
0x18006bd2a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006bd2e  jnz     short loc_18006BD9E
0x18006bd30  mov     eax, ebx
0x18006bd32  mov     rcx, [rbp+3F0h+var_50]
0x18006bd39  xor     rcx, rsp; StackCookie
0x18006bd3c  call    __security_check_cookie
0x18006bd41  add     rsp, 4B8h
0x18006bd48  pop     r15
0x18006bd4a  pop     r14
0x18006bd4c  pop     r13
0x18006bd4e  pop     r12
0x18006bd50  pop     rdi
0x18006bd51  pop     rsi
0x18006bd52  pop     rbx
0x18006bd53  pop     rbp
0x18006bd54  retn
0x18006bd55  mov     rcx, [rbp+3F8h]; this
0x18006bd5c  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006bd63  mov     r9d, ebx; char *
0x18006bd66  mov     edx, 399h; void *
0x18006bd6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bd70  mov     rcx, [rsp+4F0h+StringSid]; hMem
0x18006bd75  test    rcx, rcx
0x18006bd78  jz      short loc_18006BD25
0x18006bd7a  call    cs:__imp_LocalFree
0x18006bd80  jmp     short loc_18006BD25
0x18006bd82  mov     rcx, [rbp+3F8h]; this
0x18006bd89  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006bd90  mov     edx, 398h; void *
0x18006bd95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006bd9a  mov     ebx, eax
0x18006bd9c  jmp     short loc_18006BD70
0x18006bd9e  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18006bda3  jmp     short loc_18006BD30
0x18006bda5  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18006bdaa  jmp     loc_18006BD06
0x18006bdaf  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18006bdb4  call    cs:__imp_RegCloseKey
0x18006bdba  mov     [rsp+4F0h+hKey], r14
0x18006bdbf  jmp     loc_18006BCE7
0x18006bdc4  mov     rcx, [rbp+3F8h]; this
0x18006bdcb  lea     rax, [rbp+3F0h+SubKey]
0x18006bdcf  mov     [rsp+4F0h+var_4C8], rax; char *
0x18006bdd4  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18006bddb  lea     rax, aPathLs; "path:%ls"
0x18006bde2  mov     r9d, ebx; char *
0x18006bde5  mov     edx, 10Eh; void *
0x18006bdea  mov     [rsp+4F0h+phkResult], rax; int
0x18006bdef  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006bdf4  test    ebx, ebx
0x18006bdf6  js      loc_18006C1FF
0x18006bdfc  lea     rax, [rsp+4F0h+var_4C0]
0x18006be01  mov     [rsp+4F0h+hMem], r14
0x18006be06  lea     r9, [rsp+4F0h+var_4B0]
0x18006be0b  mov     [rsp+4F0h+phkResult], rax; int
0x18006be10  mov     r8d, 2
0x18006be16  mov     [rsp+4F0h+var_4B0], r14
0x18006be1b  lea     rdx, Class
0x18006be22  mov     byte ptr [rsp+4F0h+var_4C0], r14b
0x18006be27  lea     rcx, [rsp+4F0h+hKey]
0x18006be2c  call    ??$ReadStringValueWorker@$0A@PEAG@RegistryKey@@AEBAJPEBGKPEAPEAGPEA_N@Z; RegistryKey::ReadStringValueWorker<0,ushort *>(ushort const *,ulong,ushort * *,bool *)
0x18006be31  mov     ebx, eax
0x18006be33  test    eax, eax
0x18006be35  js      loc_18006C21F
0x18006be3b  lea     rax, [rsp+4F0h+var_490]
0x18006be40  mov     [rsp+4F0h+var_490], r14
0x18006be45  lea     rbx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Ole\\Debug"
0x18006be4c  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18006be51  mov     rdx, rbx; lpSubKey
0x18006be54  mov     r9d, edi; samDesired
0x18006be57  xor     r8d, r8d; ulOptions
0x18006be5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006be61  call    cs:__imp_RegOpenKeyExW
0x18006be67  mov     edi, eax
0x18006be69  test    eax, eax
0x18006be6b  jle     short loc_18006BE76
0x18006be6d  movzx   edi, ax
0x18006be70  or      edi, 80070000h
0x18006be76  cmp     edi, esi
0x18006be78  jz      loc_18006BF32
0x18006be7e  mov     rcx, [rbp+3F8h]; this
0x18006be85  lea     rax, aPathLs; "path:%ls"
0x18006be8c  mov     [rsp+4F0h+var_4C8], rbx; char *
0x18006be91  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18006be98  mov     r9d, edi; char *
0x18006be9b  mov     [rsp+4F0h+phkResult], rax; int
0x18006bea0  mov     edx, 10Eh; void *
0x18006bea5  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006beaa  test    edi, edi
0x18006beac  jns     loc_18006C23F
0x18006beb2  cmp     edi, esi
0x18006beb4  jz      short loc_18006BF32
0x18006beb6  mov     rcx, [rbp+3F8h]; this
0x18006bebd  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006bec4  mov     r9d, edi; char *
0x18006bec7  mov     edx, 3DDh; void *
0x18006becc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bed1  lea     rcx, [rsp+4F0h+var_490]; this
0x18006bed6  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18006bedb  lea     rcx, [rsp+4F0h+hMem]
0x18006bee0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006bee5  lea     rcx, [rsp+4F0h+var_4B0]
0x18006beea  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006beef  lea     rcx, [rsp+4F0h+hKey]; this
0x18006bef4  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18006bef9  lea     rcx, [rsp+4F0h+StringSid]
0x18006befe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006bf03  mov     rcx, [rsp+4F0h+hObject]; hObject
0x18006bf08  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006bf0c  jz      short loc_18006BF13
0x18006bf0e  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18006bf13  mov     eax, edi
0x18006bf15  jmp     loc_18006BD32
0x18006bf1a  lea     rcx, [rsp+4F0h+String]
0x18006bf1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006bf24  lea     rcx, [rsp+4F0h+var_488]
0x18006bf29  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006bf2e  test    edi, edi
0x18006bf30  js      short loc_18006BEB2
0x18006bf32  mov     rbx, [rsp+4F0h+hMem]
0x18006bf37  test    rbx, rbx
0x18006bf3a  jnz     loc_18006C463
0x18006bf40  lea     rax, [rsp+4F0h+var_4C0]
0x18006bf45  mov     [rsp+4F0h+hMem], r14
0x18006bf4a  lea     r9, [rsp+4F0h+hMem]
0x18006bf4f  mov     [rsp+4F0h+phkResult], rax; int
0x18006bf54  mov     r8d, 20h ; ' '
0x18006bf5a  mov     byte ptr [rsp+4F0h+var_4C0], r14b
0x18006bf5f  lea     rdx, aDebuggerenviro; "DebuggerEnvironment"
0x18006bf66  lea     rcx, [rsp+4F0h+hKey]
0x18006bf6b  call    ??$ReadStringValueWorker@$0A@PEAG@RegistryKey@@AEBAJPEBGKPEAPEAGPEA_N@Z; RegistryKey::ReadStringValueWorker<0,ushort *>(ushort const *,ulong,ushort * *,bool *)
0x18006bf70  mov     ebx, eax
0x18006bf72  mov     eax, 80000000h
0x18006bf77  lea     ecx, [rbx+rax]
0x18006bf7a  test    eax, ecx
0x18006bf7c  jz      short loc_18006BFD4
0x18006bf7e  mov     rax, [rsp+4F0h+hMem]
0x18006bf83  mov     [r12], rax
0x18006bf87  mov     rax, [rsp+4F0h+var_4B0]
0x18006bf8c  mov     [r15], rax
0x18006bf8f  mov     rax, [rsp+4F0h+var_490]
0x18006bf94  mov     [rsp+4F0h+hMem], r14
0x18006bf99  mov     [rsp+4F0h+var_4B0], r14
0x18006bf9e  mov     dword ptr [r13+0], 1
0x18006bfa6  test    rax, rax
0x18006bfa9  jnz     short loc_18006BFF5
0x18006bfab  mov     rcx, [rsp+4F0h+hMem]; hMem
0x18006bfb0  test    rcx, rcx
0x18006bfb3  jz      short loc_18006BFBB
0x18006bfb5  call    cs:__imp_LocalFree
0x18006bfbb  mov     rcx, [rsp+4F0h+var_4B0]; hMem
0x18006bfc0  test    rcx, rcx
0x18006bfc3  jz      loc_18006BCD9
0x18006bfc9  call    cs:__imp_LocalFree
0x18006bfcf  jmp     loc_18006BCD9
0x18006bfd4  cmp     ebx, esi
0x18006bfd6  jz      short loc_18006BF7E
0x18006bfd8  mov     rcx, [rbp+3F8h]; this
0x18006bfdf  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006bfe6  mov     r9d, ebx; char *
0x18006bfe9  mov     edx, 3E1h; void *
0x18006bfee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bff3  jmp     short loc_18006C063
0x18006bff5  mov     rcx, [rsp+4F0h+var_490]; hKey
0x18006bffa  call    cs:__imp_RegCloseKey
0x18006c000  mov     [rsp+4F0h+var_490], r14
0x18006c005  jmp     short loc_18006BFAB
0x18006c007  mov     r14, [rsp+4F0h+String]
0x18006c00c  lea     rcx, [rsp+4F0h+String]
0x18006c011  mov     rdx, [rsp+4F0h+var_4B0]
0x18006c016  inc     r14
0x18006c019  mov     r8, r14
0x18006c01c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18006c021  mov     rbx, [rsp+4F0h+String]
0x18006c026  test    rbx, rbx
0x18006c029  jnz     loc_18006C2C0
0x18006c02f  mov     rcx, [rbp+3F8h]; this
0x18006c036  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006c03d  mov     ebx, 8007000Eh
0x18006c042  mov     edx, 3C6h; void *
0x18006c047  mov     r9d, ebx; char *
0x18006c04a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c04f  lea     rcx, [rsp+4F0h+String]
0x18006c054  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c059  lea     rcx, [rsp+4F0h+var_488]
0x18006c05e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c063  lea     rcx, [rsp+4F0h+var_490]; this
0x18006c068  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18006c06d  lea     rcx, [rsp+4F0h+hMem]
0x18006c072  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c077  lea     rcx, [rsp+4F0h+var_4B0]
0x18006c07c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c081  lea     rcx, [rsp+4F0h+hKey]; this
0x18006c086  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18006c08b  lea     rcx, [rsp+4F0h+StringSid]
0x18006c090  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c095  jmp     loc_18006BD25
0x18006c09a  mov     rcx, [rbp+3F8h]; this
0x18006c0a1  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006c0a8  mov     r9d, 8000FFFFh; char *
0x18006c0ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c0b3  lea     rcx, [rsp+4F0h+String]
0x18006c0b8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c0bd  lea     rcx, [rsp+4F0h+var_488]
0x18006c0c2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c0c7  lea     rcx, [rsp+4F0h+var_490]; this
0x18006c0cc  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18006c0d1  lea     rcx, [rsp+4F0h+hMem]
0x18006c0d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c0db  lea     rcx, [rsp+4F0h+var_4B0]
0x18006c0e0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c0e5  lea     rcx, [rsp+4F0h+hKey]; this
0x18006c0ea  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18006c0ef  lea     rcx, [rsp+4F0h+StringSid]
0x18006c0f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c0f9  mov     rcx, [rsp+4F0h+hObject]; hObject
0x18006c0fe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006c102  jz      short loc_18006C109
0x18006c104  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18006c109  mov     eax, 8000FFFFh
0x18006c10e  jmp     loc_18006BD32
0x18006c113  mov     rcx, [rbp+3F8h]; this
  ... truncated ...
```
