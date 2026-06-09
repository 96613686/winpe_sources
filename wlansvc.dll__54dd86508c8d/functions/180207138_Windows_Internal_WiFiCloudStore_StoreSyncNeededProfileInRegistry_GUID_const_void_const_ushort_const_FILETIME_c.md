# Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(_GUID const &,void * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,bool *)

- ea: `0x180207138`
- end: `0x1802077c0`
- name: `?StoreSyncNeededProfileInRegistry@WiFiCloudStore@Internal@Windows@@YAJAEBU_GUID@@QEAXPEBGAEBU_FILETIME@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEA_N@Z`
- size: `1672`
- prototype: `int __high(const struct _GUID *, void *const, const unsigned __int16 *, const struct _FILETIME *, enum Windows::Internal::WiFiCloudStore::ProfileModificationType, enum Windows::Internal::WiFiCloudStore::ProfileGeneration, bool *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800babdc`
- `0x1800baeb8`

## callees

- `0x18000a994`
- `0x18000d650`
- `0x18001a0d0`
- `0x18001c9cc`
- `0x180069f44`
- `0x18006a050`
- `0x1800b9f40`
- `0x1800ba438`
- `0x1800cf244`
- `0x1800d4b9c`
- `0x1800e0580`
- `0x1800e09a0`
- `0x1800f17f8`
- `0x1800f7d84`
- `0x180106340`
- `0x18010a024`
- `0x180206ff8`
- `0x1802070f8`
- `0x180207138`
- `0x180207a1c`
- `0x180207ac8`
- `0x180207af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180207487`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180207487`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180207535`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180207535`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802073ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802073ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18020724c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180207705`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18020724c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180207705`

## string_xrefs

- `0x1802071c7`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x1802071fb`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18020725e`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x180207402`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18020749c`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18020754a`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x180207717`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x180207779`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x180207765`: `SID: %ws, Profile: %ws, Modification Type: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(
        __int64 a1,
        void *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5,
        unsigned int a6,
        _BYTE *a7)
{
  __int64 v8; // r12
  __int64 v10; // r15
  unsigned int v11; // edi
  unsigned int v12; // r14d
  char v13; // al
  int v14; // eax
  const char *v15; // r9
  unsigned int LastError; // ebx
  __int64 v18; // rax
  unsigned int v19; // ebx
  HKEY *phkResult; // rax
  const WCHAR *v21; // rdx
  unsigned int Key; // eax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  DWORD i; // esi
  unsigned int v27; // eax
  __int64 v28; // rax
  _BYTE *v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // r13d
  _QWORD *v32; // r13
  const char *v33; // r9
  LPWSTR v34; // rax
  const char *v35; // r9
  unsigned int v36; // ebx
  const char *v37; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-148h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-148h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-148h]
  LPWSTR StringSid; // [rsp+60h] [rbp-108h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-100h] BYREF
  LPWSTR v43; // [rsp+70h] [rbp-F8h] BYREF
  LPWSTR v44; // [rsp+78h] [rbp-F0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+80h] [rbp-E8h] BYREF
  DWORD cSubKeys; // [rsp+84h] [rbp-E4h] BYREF
  int v47; // [rsp+88h] [rbp-E0h] BYREF
  DWORD v48; // [rsp+8Ch] [rbp-DCh]
  _BYTE *v49; // [rsp+90h] [rbp-D8h] BYREF
  __int64 v50; // [rsp+98h] [rbp-D0h] BYREF
  LPWSTR lpName[3]; // [rsp+A0h] [rbp-C8h] BYREF
  _BYTE v52[8]; // [rsp+B8h] [rbp-B0h] BYREF
  _BYTE v53[8]; // [rsp+C0h] [rbp-A8h] BYREF
  LPWSTR v54; // [rsp+C8h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-98h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-90h]
  WCHAR *v57; // [rsp+E0h] [rbp-88h]
  LPCWSTR lpSubKey[4]; // [rsp+E8h] [rbp-80h] BYREF
  _BYTE v59[32]; // [rsp+108h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v44 = (LPWSTR)a4;
  v8 = a3;
  v10 = a1;
  v56 = a1;
  v50 = a3;
  v57 = (WCHAR *)a4;
  v49 = a7;
  v11 = a5;
  v12 = a6;
  if ( a5 != 1 || a6 == 0x7FFFFFFF )
    v13 = 0;
  else
    v13 = a5;
  if ( v13 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
      a4);
  switch ( a5 )
  {
    case 1u:
      v14 = 3;
      break;
    case 2u:
      v14 = 4;
      break;
    case 4u:
      v14 = 10;
      break;
    case 8u:
      v14 = 12;
      break;
    default:
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
        a4);
  }
  v47 = v14;
  *a7 = 0;
  if ( (unsigned int)Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(a2) == 1 )
  {
    StringSid = 0;
    if ( !ConvertSidToStringSidW(a2, &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x67,
                    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
                    v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      return LastError;
    }
    hKey = 0;
    if ( a5 - 1 <= 1 )
      v18 = Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(&v44, v10, v12, StringSid);
    else
      v18 = Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(&v44, v10, v12, StringSid);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
      &hKey,
      v18);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v44);
    v19 = (unsigned int)StringSid;
    std::wstring::wstring(lpSubKey, v8);
    Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile((unsigned int)lpSubKey, v10, a5, v12, v19);
    std::pair<std::wstring,void *>::~pair<std::wstring,void *>(lpSubKey);
    Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(hKey, v8, a4, a5);
    *v49 = 1;
    v49 = *(_BYTE **)a4;
    v44 = StringSid;
    WiFiCloudStoreTelemetry::WlanStoredNeededChange<unsigned short const * &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,enum WiFiSyncAction const &,unsigned short *>(
      (unsigned int)&v50,
      (unsigned int)&a6,
      v10,
      (unsigned int)&v49,
      (__int64)&v47,
      (__int64)&v44);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    return 0;
  }
  if ( a5 != 1 )
  {
    Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(lpSubKey);
    hKey = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v21 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v21 = lpSubKey[0];
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v21, 0, 0, 0, 0xFu, 0, phkResult, 0);
    if ( Key )
    {
      v23 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x83,
              (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
              (const char *)Key,
              dwOptions);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::pair<std::wstring,void *>::~pair<std::wstring,void *>(lpSubKey);
      return v23;
    }
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v24 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v24 )
    {
      v25 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x88,
              (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
              (const char *)v24,
              dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::pair<std::wstring,void *>::~pair<std::wstring,void *>(lpSubKey);
      return v25;
    }
    std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen + 1);
    for ( i = 0; ; ++i )
    {
      v48 = i;
      if ( i >= cSubKeys )
        break;
      LODWORD(StringSid) = lpName[1] - lpName[0];
      v27 = RegEnumKeyExW(hKey, i, lpName[0], (LPDWORD)&StringSid, 0, 0, 0, 0);
      try
      {
        if ( v27 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x93,
            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
            (const char *)v27,
            dwOptionsb);
        v43 = 0;
        if ( v11 == 2 )
        {
          v30 = Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(v53, v10, v12, lpName[0]);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
            &v43,
            v30);
          v29 = v53;
        }
        else
        {
          v28 = Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(v52, v10, v12, lpName[0]);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
            &v43,
            v28);
          v29 = v52;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v29);
        v31 = (unsigned int)lpName[0];
        std::wstring::wstring(v59, v8);
        Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile((unsigned int)v59, v10, v11, v12, v31);
        std::pair<std::wstring,void *>::~pair<std::wstring,void *>(v59);
        v32 = v44;
        Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(v43, v8, v44, v11);
        *v49 = 1;
        v55 = *v32;
        v54 = lpName[0];
        WiFiCloudStoreTelemetry::WlanStoredNeededChange<unsigned short const * &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,enum WiFiSyncAction const &,unsigned short *>(
          (unsigned int)&v50,
          (unsigned int)&a6,
          v10,
          (unsigned int)&v55,
          (__int64)&v47,
          (__int64)&v54);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
          v33);
        v12 = a6;
        v11 = a5;
        i = v48;
        v10 = v56;
        v8 = v50;
        v44 = v57;
        continue;
      }
    }
    std::vector<unsigned short>::_Tidy(lpName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::pair<std::wstring,void *>::~pair<std::wstring,void *>(lpSubKey);
    return 0;
  }
  v34 = 0;
  v43 = 0;
  if ( a2 )
  {
    if ( !ConvertSidToStringSidW(a2, &v43) )
    {
      v36 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xB1,
              (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
              v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
      return v36;
    }
    v34 = v43;
  }
  v37 = (const char *)L"null";
  if ( v34 )
    v37 = (const char *)v34;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
    (const char *)0x80070057LL,
    (int)"SID: %ws, Profile: %ws, Modification Type: %u",
    v37,
    v8,
    1);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180207138  mov     r11, rsp
0x18020713b  push    rbx
0x18020713c  push    rsi
0x18020713d  push    rdi
0x18020713e  push    r12
0x180207140  push    r13
0x180207142  push    r14
0x180207144  push    r15
0x180207146  sub     rsp, 130h
0x18020714d  mov     rax, cs:__security_cookie
0x180207154  xor     rax, rsp
0x180207157  mov     [rsp+168h+var_40], rax
0x18020715f  mov     r13, r9
0x180207162  mov     [rsp+168h+var_F0], r9
0x180207167  mov     r12, r8
0x18020716a  mov     rsi, rdx
0x18020716d  mov     r15, rcx
0x180207170  mov     [rsp+168h+var_90], rcx
0x180207178  mov     [r11-0D0h], r8
0x18020717f  mov     [rsp+168h+var_88], r9
0x180207187  mov     rdx, [rsp+168h+arg_30]
0x18020718f  mov     [rsp+168h+var_D8], rdx
0x180207197  mov     edi, [rsp+168h+arg_20]
0x18020719e  mov     r14d, [r11+30h]
0x1802071a2  cmp     edi, 1
0x1802071a5  jnz     short loc_1802071B7
0x1802071a7  cmp     r14d, 7FFFFFFFh
0x1802071ae  jz      short loc_1802071B7
0x1802071b0  mov     al, dil
0x1802071b3  xor     ebx, ebx
0x1802071b5  jmp     short loc_1802071BB
0x1802071b7  xor     ebx, ebx
0x1802071b9  mov     al, bl
0x1802071bb  mov     rcx, [rsp+168h]; this
0x1802071c3  test    al, al
0x1802071c5  jz      short loc_1802071D9
0x1802071c7  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x1802071ce  mov     edx, 5Ch ; '\'; void *
0x1802071d3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802071d9  mov     ecx, edi
0x1802071db  sub     ecx, 1
0x1802071de  jz      short loc_180207220
0x1802071e0  sub     ecx, 1
0x1802071e3  jz      short loc_180207219
0x1802071e5  sub     ecx, 2
0x1802071e8  jz      short loc_180207212
0x1802071ea  mov     eax, 4
0x1802071ef  cmp     ecx, eax
0x1802071f1  jz      short loc_18020720B
0x1802071f3  mov     rcx, [rsp+168h]; this
0x1802071fb  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180207202  lea     edx, [rax+50h]; void *
0x180207205  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18020720b  mov     eax, 0Ch
0x180207210  jmp     short loc_180207225
0x180207212  mov     eax, 0Ah
0x180207217  jmp     short loc_180207225
0x180207219  mov     eax, 4
0x18020721e  jmp     short loc_180207225
0x180207220  mov     eax, 3
0x180207225  mov     [rsp+168h+var_E0], eax
0x18020722c  mov     [rdx], bl
0x18020722e  mov     rcx, rsi
0x180207231  call    ?GetOwnerSecurityOfSid@WiFiCloudStore@Internal@Windows@@YA?AW4ProfileOwnerSecurity@123@QEAX@Z; Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void * const)
0x180207236  cmp     eax, 1
0x180207239  jnz     loc_180207385
0x18020723f  mov     [rsp+168h+StringSid], rbx
0x180207244  lea     rdx, [rsp+168h+StringSid]; StringSid
0x180207249  mov     rcx, rsi; Sid
0x18020724c  call    cs:__imp_ConvertSidToStringSidW
0x180207252  test    eax, eax
0x180207254  jnz     short loc_180207280
0x180207256  mov     rcx, [rsp+168h]; this
0x18020725e  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180207265  lea     edx, [rax+67h]; void *
0x180207268  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18020726d  mov     ebx, eax
0x18020726f  lea     rcx, [rsp+168h+StringSid]
0x180207274  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180207279  mov     eax, ebx
0x18020727b  jmp     loc_18020779C
0x180207280  mov     [rsp+168h+hKey], rbx
0x180207285  lea     eax, [rdi-1]
0x180207288  mov     r9, [rsp+168h+StringSid]
0x18020728d  mov     r8d, r14d
0x180207290  mov     rdx, r15
0x180207293  lea     rcx, [rsp+168h+var_F0]
0x180207298  cmp     eax, 1
0x18020729b  jbe     short loc_1802072A4
0x18020729d  call    ?OpenCostSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x1802072a2  jmp     short loc_1802072A9
0x1802072a4  call    ?OpenProfileSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x1802072a9  mov     rdx, rax
0x1802072ac  lea     rcx, [rsp+168h+hKey]
0x1802072b1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x1802072b6  lea     rcx, [rsp+168h+var_F0]
0x1802072bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802072c0  mov     rbx, [rsp+168h+StringSid]
0x1802072c5  mov     rdx, r12
0x1802072c8  lea     rcx, [rsp+168h+lpSubKey]
0x1802072d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802072d5  nop
0x1802072d6  mov     qword ptr [rsp+168h+dwOptions], rbx
0x1802072db  mov     r9d, r14d
0x1802072de  mov     r8d, edi
0x1802072e1  mov     rdx, r15
0x1802072e4  lea     rcx, [rsp+168h+lpSubKey]
0x1802072ec  call    ?DeleteRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x1802072f1  nop
0x1802072f2  lea     rcx, [rsp+168h+lpSubKey]; void *
0x1802072fa  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x1802072ff  mov     r9d, edi
0x180207302  mov     r8, r13
0x180207305  mov     rdx, r12
0x180207308  mov     rcx, [rsp+168h+hKey]
0x18020730d  call    ?StoreSyncNeededProfileForUser@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@PEBGAEBU_FILETIME@@W4ProfileModificationType@123@@Z; Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(HKEY__ * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType)
0x180207312  mov     rax, [rsp+168h+var_D8]
0x18020731a  mov     byte ptr [rax], 1
0x18020731d  mov     rax, [r13+0]
0x180207321  mov     [rsp+168h+var_D8], rax
0x180207329  mov     rax, [rsp+168h+StringSid]
0x18020732e  mov     [rsp+168h+var_F0], rax
0x180207333  lea     rax, [rsp+168h+var_F0]
0x180207338  mov     qword ptr [rsp+168h+samDesired], rax
0x18020733d  lea     rax, [rsp+168h+var_E0]
0x180207345  mov     qword ptr [rsp+168h+dwOptions], rax
0x18020734a  lea     r9, [rsp+168h+var_D8]
0x180207352  mov     r8, r15
0x180207355  lea     rdx, [rsp+168h+arg_28]
0x18020735d  lea     rcx, [rsp+168h+var_D0]
0x180207365  call    ??$WlanStoredNeededChange@AEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@AEA_KAEBW4WiFiSyncAction@@PEAG@WiFiCloudStoreTelemetry@@SAXAEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@AEA_KAEBW4WiFiSyncAction@@$$QEAPEAG@Z; WiFiCloudStoreTelemetry::WlanStoredNeededChange<ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,WiFiSyncAction const &,ushort *>(ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,WiFiSyncAction const &,ushort * &&)
0x18020736a  nop
0x18020736b  lea     rcx, [rsp+168h+hKey]
0x180207370  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180207375  nop
0x180207376  lea     rcx, [rsp+168h+StringSid]
0x18020737b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180207380  jmp     loc_1802076E9
0x180207385  cmp     edi, 1
0x180207388  jz      loc_1802076F0
0x18020738e  lea     rcx, [rsp+168h+lpSubKey]; Src
0x180207396  call    ?GetMutableCDSRegistryKey@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(void)
0x18020739b  nop
0x18020739c  mov     [rsp+168h+hKey], rbx
0x1802073a1  lea     rcx, [rsp+168h+hKey]
0x1802073a6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1802073ab  lea     rdx, [rsp+168h+lpSubKey]
0x1802073b3  cmp     [rsp+168h+var_68], 7
0x1802073bc  cmova   rdx, [rsp+168h+lpSubKey]; lpSubKey
0x1802073c5  mov     [rsp+168h+lpdwDisposition], rbx; lpdwDisposition
0x1802073ca  mov     [rsp+168h+phkResult], rax; phkResult
0x1802073cf  mov     [rsp+168h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1802073d4  mov     [rsp+168h+samDesired], 0Fh; samDesired
0x1802073dc  mov     [rsp+168h+dwOptions], ebx; unsigned int
0x1802073e0  xor     r9d, r9d; lpClass
0x1802073e3  xor     r8d, r8d; Reserved
0x1802073e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802073ed  call    cs:__imp_RegCreateKeyExW
0x1802073f3  test    eax, eax
0x1802073f5  jz      short loc_180207434
0x1802073f7  mov     rcx, [rsp+168h]; this
0x1802073ff  mov     r9d, eax; char *
0x180207402  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180207409  mov     edx, 83h; void *
0x18020740e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180207413  mov     ebx, eax
0x180207415  lea     rcx, [rsp+168h+hKey]
0x18020741a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18020741f  nop
0x180207420  lea     rcx, [rsp+168h+lpSubKey]; void *
0x180207428  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x18020742d  mov     eax, ebx
0x18020742f  jmp     loc_18020779C
0x180207434  mov     [rsp+168h+cSubKeys], ebx
0x18020743b  mov     [rsp+168h+cbMaxSubKeyLen], ebx
0x180207442  mov     [rsp+168h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180207447  mov     [rsp+168h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18020744c  mov     [rsp+168h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180207451  mov     [rsp+168h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x180207456  mov     [rsp+168h+phkResult], rbx; lpcValues
0x18020745b  mov     [rsp+168h+lpSecurityAttributes], rbx; lpcbMaxClassLen
0x180207460  lea     rax, [rsp+168h+cbMaxSubKeyLen]
0x180207468  mov     qword ptr [rsp+168h+samDesired], rax; lpcbMaxSubKeyLen
0x18020746d  lea     rax, [rsp+168h+cSubKeys]
0x180207475  mov     qword ptr [rsp+168h+dwOptions], rax; unsigned int
0x18020747a  xor     r9d, r9d; lpReserved
0x18020747d  xor     r8d, r8d; lpcchClass
0x180207480  xor     edx, edx; lpClass
0x180207482  mov     rcx, [rsp+168h+hKey]; hKey
0x180207487  call    cs:__imp_RegQueryInfoKeyW
0x18020748d  test    eax, eax
0x18020748f  jz      short loc_1802074CE
0x180207491  mov     rcx, [rsp+168h]; this
0x180207499  mov     r9d, eax; char *
0x18020749c  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x1802074a3  mov     edx, 88h; void *
0x1802074a8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802074ad  mov     ebx, eax
0x1802074af  lea     rcx, [rsp+168h+hKey]
0x1802074b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802074b9  nop
0x1802074ba  lea     rcx, [rsp+168h+lpSubKey]; void *
0x1802074c2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x1802074c7  mov     eax, ebx
0x1802074c9  jmp     loc_18020779C
0x1802074ce  mov     edx, [rsp+168h+cbMaxSubKeyLen]
0x1802074d5  inc     edx
0x1802074d7  lea     rcx, [rsp+168h+lpName]
0x1802074df  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1802074e4  nop
0x1802074e5  mov     esi, ebx
0x1802074e7  mov     [rsp+168h+var_DC], esi
0x1802074ee  cmp     esi, [rsp+168h+cSubKeys]
0x1802074f5  jnb     loc_1802076C3
0x1802074fb  mov     rax, [rsp+168h+var_C0]
0x180207503  mov     r8, [rsp+168h+lpName]; lpName
0x18020750b  sub     rax, r8
0x18020750e  sar     rax, 1
0x180207511  mov     dword ptr [rsp+168h+StringSid], eax
0x180207515  mov     [rsp+168h+phkResult], rbx; lpftLastWriteTime
0x18020751a  mov     [rsp+168h+lpSecurityAttributes], rbx; lpcchClass
0x18020751f  mov     qword ptr [rsp+168h+samDesired], rbx; lpClass
0x180207524  mov     qword ptr [rsp+168h+dwOptions], rbx; unsigned int
0x180207529  lea     r9, [rsp+168h+StringSid]; lpcchName
0x18020752e  mov     edx, esi; dwIndex
0x180207530  mov     rcx, [rsp+168h+hKey]; hKey
0x180207535  call    cs:__imp_RegEnumKeyExW
0x18020753b  mov     rcx, [rsp+168h]; this
0x180207543  test    eax, eax
0x180207545  jz      short loc_18020755B
0x180207547  mov     r9d, eax; char *
0x18020754a  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180207551  mov     edx, 93h; void *
0x180207556  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18020755b  mov     [rsp+168h+var_F8], rbx
0x180207560  mov     r9, [rsp+168h+lpName]
0x180207568  mov     r8d, r14d
0x18020756b  mov     rdx, r15
0x18020756e  cmp     edi, 2
0x180207571  jz      short loc_180207597
0x180207573  lea     rcx, [rsp+168h+var_B0]
0x18020757b  call    ?OpenCostSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x180207580  mov     rdx, rax
0x180207583  lea     rcx, [rsp+168h+var_F8]
0x180207588  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18020758d  lea     rcx, [rsp+168h+var_B0]
0x180207595  jmp     short loc_1802075B9
0x180207597  lea     rcx, [rsp+168h+var_A8]
0x18020759f  call    ?OpenProfileSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x1802075a4  mov     rdx, rax
0x1802075a7  lea     rcx, [rsp+168h+var_F8]
0x1802075ac  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x1802075b1  lea     rcx, [rsp+168h+var_A8]
0x1802075b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802075be  mov     r13, [rsp+168h+lpName]
0x1802075c6  mov     rdx, r12
0x1802075c9  lea     rcx, [rsp+168h+var_60]
0x1802075d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802075d6  nop
0x1802075d7  mov     qword ptr [rsp+168h+dwOptions], r13
0x1802075dc  mov     r9d, r14d
0x1802075df  mov     r8d, edi
0x1802075e2  mov     rdx, r15
0x1802075e5  lea     rcx, [rsp+168h+var_60]
0x1802075ed  call    ?DeleteRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x1802075f2  nop
0x1802075f3  lea     rcx, [rsp+168h+var_60]; void *
0x1802075fb  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x180207600  mov     r9d, edi
0x180207603  mov     r13, [rsp+168h+var_F0]
0x180207608  mov     r8, r13
0x18020760b  mov     rdx, r12
0x18020760e  mov     rcx, [rsp+168h+var_F8]
0x180207613  call    ?StoreSyncNeededProfileForUser@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@PEBGAEBU_FILETIME@@W4ProfileModificationType@123@@Z; Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(HKEY__ * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType)
0x180207618  mov     rax, [rsp+168h+var_D8]
0x180207620  mov     byte ptr [rax], 1
0x180207623  mov     rax, [r13+0]
0x180207627  mov     [rsp+168h+var_98], rax
0x18020762f  mov     rax, [rsp+168h+lpName]
0x180207637  mov     [rsp+168h+var_A0], rax
0x18020763f  lea     rax, [rsp+168h+var_A0]
0x180207647  mov     qword ptr [rsp+168h+samDesired], rax
0x18020764c  lea     rax, [rsp+168h+var_E0]
0x180207654  mov     qword ptr [rsp+168h+dwOptions], rax
0x180207659  lea     r9, [rsp+168h+var_98]
0x180207661  mov     r8, r15
0x180207664  lea     rdx, [rsp+168h+arg_28]
0x18020766c  lea     rcx, [rsp+168h+var_D0]
0x180207674  call    ??$WlanStoredNeededChange@AEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@AEA_KAEBW4WiFiSyncAction@@PEAG@WiFiCloudStoreTelemetry@@SAXAEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@AEA_KAEBW4WiFiSyncAction@@$$QEAPEAG@Z; WiFiCloudStoreTelemetry::WlanStoredNeededChange<ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,WiFiSyncAction const &,ushort *>(ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,WiFiSyncAction const &,ushort * &&)
0x180207679  nop
0x18020767a  lea     rcx, [rsp+168h+var_F8]
0x18020767f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180207684  nop
0x180207685  jmp     short loc_1802076BC
0x180207687  xor     ebx, ebx
0x180207689  mov     r14d, [rsp+168h+arg_28]
0x180207691  mov     edi, [rsp+168h+arg_20]
0x180207698  mov     esi, [rsp+168h+var_DC]
0x18020769f  mov     r15, [rsp+168h+var_90]
0x1802076a7  mov     r12, [rsp+168h+var_D0]
  ... truncated ...
```
