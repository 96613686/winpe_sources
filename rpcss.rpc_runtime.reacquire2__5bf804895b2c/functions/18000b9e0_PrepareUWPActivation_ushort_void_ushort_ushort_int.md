# PrepareUWPActivation(ushort *,void *,ushort * *,ushort * *,int *)

- ea: `0x18000b9e0`
- end: `0x18000c2bf`
- name: `?PrepareUWPActivation@@YAJPEAGPEAXPEAPEAG2PEAH@Z`
- size: `2271`
- prototype: `int(unsigned __int16 *, void *, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c4b0`
- `0x18004e578`

## callees

- `0x18000b9e0`
- `0x18000c2c8`
- `0x18000c3f8`
- `0x18000ce5c`
- `0x18001037c`
- `0x180011db0`
- `0x1800210f8`
- `0x180025088`
- `0x18002efd4`
- `0x180072c6c`
- `0x180081764`
- `0x1800817ac`
- `0x180089758`
- `0x1800961a4`
- `0x1800b7ac0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000c124`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000c1ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000c124`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000c1ac`
- `ntdll!wcsstr` at `0x18000c1cd`
- `ntdll!wcsstr` at `0x18000c1e8`
- `ntdll!wcsstr` at `0x18000c1cd`
- `ntdll!wcsstr` at `0x18000c1e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bbd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bbd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bac5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bac5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc94`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ba63`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ba63`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000bb05`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000bb95`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000bde7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000be01`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000bb05`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000bb95`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000bde7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000be01`

## string_xrefs

- `0x18000bb2b`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000bb77`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000bbaa`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000bcf6`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000be1d`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000be7a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000bee5`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000bf5e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000bfd2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c04a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c06a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c0eb`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c288`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000bc02`: `path:%ls`
- `0x18000bcbe`: `path:%ls`
- `0x18000bbfb`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18000bcca`: `onecore\com\combase\inc\RegistryKey.hpp`

## pseudocode

```c
__int64 __fastcall PrepareUWPActivation(unsigned __int16 *a1, void *a2, HLOCAL *a3, HLOCAL *a4, int *a5)
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
  HKEY v21; // rax
  char *v22; // r14
  wchar_t *v23; // rbx
  void *v24; // rdx
  void *v25; // rdx
  void *v26; // rdx
  signed int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned int v30; // esi
  __int64 v31; // rdx
  unsigned __int16 *i; // rsi
  int v33; // r14d
  __int64 v34; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResultd; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL v42; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v46; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v47; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v49; // [rsp+78h] [rbp-88h] BYREF
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
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(a2, &StringSid) )
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
    goto LABEL_48;
  }
  v42 = 0;
  hMem = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v42,
    0);
  LOBYTE(v40) = 0;
  StringValue = RegistryKey::ReadStringValueWorker<0,unsigned short *>(
                  (RegistryKey *)&hKey,
                  (char *)&Class,
                  2u,
                  (__int64)&v40);
  LastError = StringValue;
  if ( StringValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A9,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)StringValue,
      phkResultb);
    goto LABEL_47;
  }
  v46 = 0;
  v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Ole\\Debug", 0, 0x20019u, &v46);
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
      RegistryKey::Close((RegistryKey *)&v46);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
      RegistryKey::Close((RegistryKey *)&hKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      if ( hObject != (HANDLE)-1LL )
        wil::details::RevertImpersonateToken(hObject, v20);
      return (unsigned int)v19;
    }
LABEL_34:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hMem,
      0);
    LOBYTE(v40) = 0;
    LastError = RegistryKey::ReadStringValueWorker<0,unsigned short *>(
                  (RegistryKey *)&hKey,
                  (char *)L"DebuggerEnvironment",
                  0x20u,
                  (__int64)&v40);
    if ( (int)(LastError + 0x80000000) < 0 || LastError == -2147024894 )
    {
      *a4 = hMem;
      *a3 = v42;
      v21 = v46;
      hMem = 0;
      v42 = 0;
      *a5 = 1;
      if ( v21 )
      {
        RegCloseKey(v46);
        v46 = 0;
      }
      if ( hMem )
        LocalFree(hMem);
      if ( v42 )
        LocalFree(v42);
      goto LABEL_7;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)LastError,
      phkResultd);
    goto LABEL_46;
  }
  v47 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v47,
    0);
  LOBYTE(v40) = 0;
  v27 = RegistryKey::ReadStringValueWorker<0,unsigned short *>(
          (RegistryKey *)&v46,
          (char *)L"NonNativeDebuggerExclusionList",
          0x20u,
          (__int64)&v40);
  String = 0;
  v19 = v27;
  v28 = StringCchLengthW((const unsigned __int16 *)v42, 0x7FFFFFFFu, (unsigned __int64 *)&String);
  LastError = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C4,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)v28,
      phkResultc);
    goto LABEL_45;
  }
  v22 = (char *)String + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &String,
    v42,
    (char *)String + 1);
  v23 = String;
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
LABEL_45:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
LABEL_46:
    RegistryKey::Close((RegistryKey *)&v46);
LABEL_47:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
LABEL_48:
    RegistryKey::Close((RegistryKey *)&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_15;
  }
  v29 = StringCchCopyW(String, (unsigned __int64)v22, (const unsigned __int16 *)v42);
  v30 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C7,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)v29,
      phkResultc);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
    RegistryKey::Close((RegistryKey *)&v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
    RegistryKey::Close((RegistryKey *)&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    if ( hObject != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(hObject, v26);
    return v30;
  }
  if ( !_wcslwr_s(v23, (size_t)v22) )
  {
    if ( v19 >= 0 )
    {
      for ( i = v47; ; i += v49 + 1 )
      {
        if ( !*i )
          goto LABEL_33;
        v49 = 0;
        v33 = StringCchLengthW(i, 0x7FFFFFFFu, &v49);
        if ( v33 < 0 )
          break;
        v33 = StringCchPrintfW(SubStr, 0x104u, L"%s", i);
        if ( v33 < 0 )
        {
          v34 = 977;
LABEL_52:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)v33,
            phkResultc);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
          RegistryKey::Close((RegistryKey *)&v46);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
          RegistryKey::Close((RegistryKey *)&hKey);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          if ( hObject != (HANDLE)-1LL )
            wil::details::RevertImpersonateToken(hObject, v25);
          return (unsigned int)v33;
        }
        if ( _wcslwr_s(SubStr, 0x104u) )
        {
          v31 = 978;
          goto LABEL_49;
        }
        if ( wcsstr(v23, SubStr) && !wcsstr(v23, L"\\x64\\") )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
          RegistryKey::Close((RegistryKey *)&v46);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
          RegistryKey::Close((RegistryKey *)&hKey);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          goto LABEL_11;
        }
      }
      v34 = 975;
      goto LABEL_52;
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
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
      goto LABEL_30;
    }
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
    if ( v19 >= 0 )
      goto LABEL_34;
    goto LABEL_28;
  }
  v31 = 968;
LABEL_49:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v31,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
    (const char *)0x8000FFFFLL,
    phkResultc);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
  RegistryKey::Close((RegistryKey *)&v46);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
  RegistryKey::Close((RegistryKey *)&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  if ( hObject != (HANDLE)-1LL )
    wil::details::RevertImpersonateToken(hObject, v24);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000b9e0  push    rbp
0x18000b9e2  push    rbx
0x18000b9e3  push    rsi
0x18000b9e4  push    rdi
0x18000b9e5  push    r12
0x18000b9e7  push    r13
0x18000b9e9  push    r14
0x18000b9eb  push    r15
0x18000b9ed  lea     rbp, [rsp-3B8h]
0x18000b9f5  sub     rsp, 4B8h
0x18000b9fc  mov     rax, cs:__security_cookie
0x18000ba03  xor     rax, rsp
0x18000ba06  mov     [rbp+3F0h+var_50], rax
0x18000ba0d  mov     r13, [rbp+3F0h+arg_20]
0x18000ba14  xor     r14d, r14d
0x18000ba17  mov     [r8], r14
0x18000ba1a  mov     rdi, rdx
0x18000ba1d  mov     [r9], r14
0x18000ba20  lea     rdx, [rsp+4F0h+hObject]
0x18000ba25  mov     r12, r9
0x18000ba28  mov     [rsp+4F0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000ba31  mov     [r13+0], r14d
0x18000ba35  mov     r15, r8
0x18000ba38  mov     rsi, rcx
0x18000ba3b  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18000ba40  mov     ebx, eax
0x18000ba42  test    eax, eax
0x18000ba44  js      loc_18000BB24
0x18000ba4a  xor     edx, edx
0x18000ba4c  mov     [rsp+4F0h+StringSid], r14
0x18000ba51  lea     rcx, [rsp+4F0h+StringSid]
0x18000ba56  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000ba5b  lea     rdx, [rsp+4F0h+StringSid]; StringSid
0x18000ba60  mov     rcx, rdi; Sid
0x18000ba63  call    cs:__imp_ConvertSidToStringSidW
0x18000ba6a  nop     dword ptr [rax+rax+00h]
0x18000ba6f  test    eax, eax
0x18000ba71  jz      loc_18000BBA3
0x18000ba77  mov     r9, [rsp+4F0h+StringSid]
0x18000ba7c  lea     r8, aSSoftwareMicro; "%s\\SOFTWARE\\Microsoft\\Windows\\Curre"...
0x18000ba83  mov     edx, 104h; unsigned __int64
0x18000ba88  mov     [rsp+4F0h+phkResult], rsi; int
0x18000ba8d  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x18000ba91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ba96  mov     ebx, eax
0x18000ba98  test    eax, eax
0x18000ba9a  js      loc_18000BB70
0x18000baa0  lea     rax, [rsp+4F0h+hKey]
0x18000baa5  mov     [rsp+4F0h+hKey], r14
0x18000baaa  mov     edi, 20019h
0x18000baaf  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18000bab4  mov     r9d, edi; samDesired
0x18000bab7  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x18000babb  xor     r8d, r8d; ulOptions
0x18000babe  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000bac5  call    cs:__imp_RegOpenKeyExW
0x18000bacc  nop     dword ptr [rax+rax+00h]
0x18000bad1  mov     ebx, eax
0x18000bad3  test    eax, eax
0x18000bad5  jle     short loc_18000BAE0
0x18000bad7  movzx   ebx, ax
0x18000bada  or      ebx, 80070000h
0x18000bae0  mov     esi, 80070002h
0x18000bae5  cmp     ebx, esi
0x18000bae7  jnz     loc_18000BBEB
0x18000baed  mov     rax, [rsp+4F0h+hKey]
0x18000baf2  test    rax, rax
0x18000baf5  jnz     loc_18000BBD0
0x18000bafb  mov     rcx, [rsp+4F0h+StringSid]; hMem
0x18000bb00  test    rcx, rcx
0x18000bb03  jz      short loc_18000BB11
0x18000bb05  call    cs:__imp_LocalFree
0x18000bb0c  nop     dword ptr [rax+rax+00h]
0x18000bb11  mov     rcx, [rsp+4F0h+hObject]; hObject
0x18000bb16  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bb1a  jnz     loc_18000BBC6
0x18000bb20  xor     eax, eax
0x18000bb22  jmp     short loc_18000BB4C
0x18000bb24  mov     rcx, [rbp+3F8h]; this
0x18000bb2b  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000bb32  mov     r9d, ebx; char *
0x18000bb35  mov     edx, 394h; void *
0x18000bb3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb3f  mov     rcx, [rsp+4F0h+hObject]; hObject
0x18000bb44  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bb48  jnz     short loc_18000BBBF
0x18000bb4a  mov     eax, ebx
0x18000bb4c  mov     rcx, [rbp+3F0h+var_50]
0x18000bb53  xor     rcx, rsp; StackCookie
0x18000bb56  call    __security_check_cookie
0x18000bb5b  add     rsp, 4B8h
0x18000bb62  pop     r15
0x18000bb64  pop     r14
0x18000bb66  pop     r13
0x18000bb68  pop     r12
0x18000bb6a  pop     rdi
0x18000bb6b  pop     rsi
0x18000bb6c  pop     rbx
0x18000bb6d  pop     rbp
0x18000bb6e  retn
0x18000bb70  mov     rcx, [rbp+3F8h]; this
0x18000bb77  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000bb7e  mov     r9d, ebx; char *
0x18000bb81  mov     edx, 399h; void *
0x18000bb86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb8b  mov     rcx, [rsp+4F0h+StringSid]; hMem
0x18000bb90  test    rcx, rcx
0x18000bb93  jz      short loc_18000BB3F
0x18000bb95  call    cs:__imp_LocalFree
0x18000bb9c  nop     dword ptr [rax+rax+00h]
0x18000bba1  jmp     short loc_18000BB3F
0x18000bba3  mov     rcx, [rbp+3F8h]; this
0x18000bbaa  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000bbb1  mov     edx, 398h; void *
0x18000bbb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bbbb  mov     ebx, eax
0x18000bbbd  jmp     short loc_18000BB8B
0x18000bbbf  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18000bbc4  jmp     short loc_18000BB4A
0x18000bbc6  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18000bbcb  jmp     loc_18000BB20
0x18000bbd0  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18000bbd5  call    cs:__imp_RegCloseKey
0x18000bbdc  nop     dword ptr [rax+rax+00h]
0x18000bbe1  mov     [rsp+4F0h+hKey], r14
0x18000bbe6  jmp     loc_18000BAFB
0x18000bbeb  mov     rcx, [rbp+3F8h]; this
0x18000bbf2  lea     rax, [rbp+3F0h+SubKey]
0x18000bbf6  mov     [rsp+4F0h+var_4C8], rax; char *
0x18000bbfb  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18000bc02  lea     rax, aPathLs; "path:%ls"
0x18000bc09  mov     r9d, ebx; char *
0x18000bc0c  mov     edx, 10Eh; void *
0x18000bc11  mov     [rsp+4F0h+phkResult], rax; int
0x18000bc16  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000bc1b  test    ebx, ebx
0x18000bc1d  js      loc_18000C043
0x18000bc23  xor     edx, edx
0x18000bc25  mov     [rsp+4F0h+var_4B0], r14
0x18000bc2a  lea     rcx, [rsp+4F0h+var_4B0]
0x18000bc2f  mov     [rsp+4F0h+hMem], r14
0x18000bc34  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000bc39  lea     rax, [rsp+4F0h+var_4C0]
0x18000bc3e  mov     byte ptr [rsp+4F0h+var_4C0], r14b
0x18000bc43  lea     r9, [rsp+4F0h+var_4B0]
0x18000bc48  mov     [rsp+4F0h+phkResult], rax; int
0x18000bc4d  mov     r8d, 2
0x18000bc53  lea     rdx, Class
0x18000bc5a  lea     rcx, [rsp+4F0h+hKey]
0x18000bc5f  call    ??$ReadStringValueWorker@$0A@PEAG@RegistryKey@@AEBAJPEBGKPEAPEAGPEA_N@Z; RegistryKey::ReadStringValueWorker<0,ushort *>(ushort const *,ulong,ushort * *,bool *)
0x18000bc64  mov     ebx, eax
0x18000bc66  test    eax, eax
0x18000bc68  js      loc_18000C063
0x18000bc6e  lea     rax, [rsp+4F0h+var_490]
0x18000bc73  mov     [rsp+4F0h+var_490], r14
0x18000bc78  lea     rbx, SubKey; "SOFTWARE\\Microsoft\\Ole\\Debug"
0x18000bc7f  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18000bc84  mov     rdx, rbx; lpSubKey
0x18000bc87  mov     r9d, edi; samDesired
0x18000bc8a  xor     r8d, r8d; ulOptions
0x18000bc8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bc94  call    cs:__imp_RegOpenKeyExW
0x18000bc9b  nop     dword ptr [rax+rax+00h]
0x18000bca0  mov     edi, eax
0x18000bca2  test    eax, eax
0x18000bca4  jle     short loc_18000BCAF
0x18000bca6  movzx   edi, ax
0x18000bca9  or      edi, 80070000h
0x18000bcaf  cmp     edi, esi
0x18000bcb1  jz      loc_18000BD6B
0x18000bcb7  mov     rcx, [rbp+3F8h]; this
0x18000bcbe  lea     rax, aPathLs; "path:%ls"
0x18000bcc5  mov     [rsp+4F0h+var_4C8], rbx; char *
0x18000bcca  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18000bcd1  mov     r9d, edi; char *
0x18000bcd4  mov     [rsp+4F0h+phkResult], rax; int
0x18000bcd9  mov     edx, 10Eh; void *
0x18000bcde  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000bce3  test    edi, edi
0x18000bce5  jns     loc_18000C083
0x18000bceb  cmp     edi, esi
0x18000bced  jz      short loc_18000BD6B
0x18000bcef  mov     rcx, [rbp+3F8h]; this
0x18000bcf6  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000bcfd  mov     r9d, edi; char *
0x18000bd00  mov     edx, 3DDh; void *
0x18000bd05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd0a  lea     rcx, [rsp+4F0h+var_490]; this
0x18000bd0f  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18000bd14  lea     rcx, [rsp+4F0h+hMem]
0x18000bd19  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bd1e  lea     rcx, [rsp+4F0h+var_4B0]
0x18000bd23  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bd28  lea     rcx, [rsp+4F0h+hKey]; this
0x18000bd2d  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18000bd32  lea     rcx, [rsp+4F0h+StringSid]
0x18000bd37  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bd3c  mov     rcx, [rsp+4F0h+hObject]; hObject
0x18000bd41  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bd45  jz      short loc_18000BD4C
0x18000bd47  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18000bd4c  mov     eax, edi
0x18000bd4e  jmp     loc_18000BB4C
0x18000bd53  lea     rcx, [rsp+4F0h+String]
0x18000bd58  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bd5d  lea     rcx, [rsp+4F0h+var_488]
0x18000bd62  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bd67  test    edi, edi
0x18000bd69  js      short loc_18000BCEB
0x18000bd6b  xor     edx, edx
0x18000bd6d  lea     rcx, [rsp+4F0h+hMem]
0x18000bd72  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000bd77  lea     rax, [rsp+4F0h+var_4C0]
0x18000bd7c  mov     byte ptr [rsp+4F0h+var_4C0], r14b
0x18000bd81  lea     r9, [rsp+4F0h+hMem]
0x18000bd86  mov     [rsp+4F0h+phkResult], rax; int
0x18000bd8b  mov     r8d, 20h ; ' '
0x18000bd91  lea     rdx, aDebuggerenviro; "DebuggerEnvironment"
0x18000bd98  lea     rcx, [rsp+4F0h+hKey]
0x18000bd9d  call    ??$ReadStringValueWorker@$0A@PEAG@RegistryKey@@AEBAJPEBGKPEAPEAGPEA_N@Z; RegistryKey::ReadStringValueWorker<0,ushort *>(ushort const *,ulong,ushort * *,bool *)
0x18000bda2  mov     ebx, eax
0x18000bda4  mov     eax, 80000000h
0x18000bda9  lea     ecx, [rbx+rax]
0x18000bdac  test    eax, ecx
0x18000bdae  jz      short loc_18000BE12
0x18000bdb0  mov     rax, [rsp+4F0h+hMem]
0x18000bdb5  mov     [r12], rax
0x18000bdb9  mov     rax, [rsp+4F0h+var_4B0]
0x18000bdbe  mov     [r15], rax
0x18000bdc1  mov     rax, [rsp+4F0h+var_490]
0x18000bdc6  mov     [rsp+4F0h+hMem], r14
0x18000bdcb  mov     [rsp+4F0h+var_4B0], r14
0x18000bdd0  mov     dword ptr [r13+0], 1
0x18000bdd8  test    rax, rax
0x18000bddb  jnz     short loc_18000BE33
0x18000bddd  mov     rcx, [rsp+4F0h+hMem]; hMem
0x18000bde2  test    rcx, rcx
0x18000bde5  jz      short loc_18000BDF3
0x18000bde7  call    cs:__imp_LocalFree
0x18000bdee  nop     dword ptr [rax+rax+00h]
0x18000bdf3  mov     rcx, [rsp+4F0h+var_4B0]; hMem
0x18000bdf8  test    rcx, rcx
0x18000bdfb  jz      loc_18000BAED
0x18000be01  call    cs:__imp_LocalFree
0x18000be08  nop     dword ptr [rax+rax+00h]
0x18000be0d  jmp     loc_18000BAED
0x18000be12  cmp     ebx, esi
0x18000be14  jz      short loc_18000BDB0
0x18000be16  mov     rcx, [rbp+3F8h]; this
0x18000be1d  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000be24  mov     r9d, ebx; char *
0x18000be27  mov     edx, 3E1h; void *
0x18000be2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be31  jmp     short loc_18000BEA7
0x18000be33  mov     rcx, [rsp+4F0h+var_490]; hKey
0x18000be38  call    cs:__imp_RegCloseKey
0x18000be3f  nop     dword ptr [rax+rax+00h]
0x18000be44  mov     [rsp+4F0h+var_490], r14
0x18000be49  jmp     short loc_18000BDDD
0x18000be4b  mov     r14, [rsp+4F0h+String]
0x18000be50  lea     rcx, [rsp+4F0h+String]
0x18000be55  mov     rdx, [rsp+4F0h+var_4B0]
0x18000be5a  inc     r14
0x18000be5d  mov     r8, r14
0x18000be60  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000be65  mov     rbx, [rsp+4F0h+String]
0x18000be6a  test    rbx, rbx
0x18000be6d  jnz     loc_18000C104
0x18000be73  mov     rcx, [rbp+3F8h]; this
0x18000be7a  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000be81  mov     ebx, 8007000Eh
0x18000be86  mov     edx, 3C6h; void *
0x18000be8b  mov     r9d, ebx; char *
0x18000be8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be93  lea     rcx, [rsp+4F0h+String]
0x18000be98  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000be9d  lea     rcx, [rsp+4F0h+var_488]
0x18000bea2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bea7  lea     rcx, [rsp+4F0h+var_490]; this
0x18000beac  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18000beb1  lea     rcx, [rsp+4F0h+hMem]
0x18000beb6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bebb  lea     rcx, [rsp+4F0h+var_4B0]
0x18000bec0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bec5  lea     rcx, [rsp+4F0h+hKey]; this
0x18000beca  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18000becf  lea     rcx, [rsp+4F0h+StringSid]
0x18000bed4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bed9  jmp     loc_18000BB3F
0x18000bede  mov     rcx, [rbp+3F8h]; this
0x18000bee5  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000beec  mov     r9d, 8000FFFFh; char *
0x18000bef2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bef7  lea     rcx, [rsp+4F0h+String]
0x18000befc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bf01  lea     rcx, [rsp+4F0h+var_488]
0x18000bf06  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bf0b  lea     rcx, [rsp+4F0h+var_490]; this
0x18000bf10  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18000bf15  lea     rcx, [rsp+4F0h+hMem]
  ... truncated ...
```
