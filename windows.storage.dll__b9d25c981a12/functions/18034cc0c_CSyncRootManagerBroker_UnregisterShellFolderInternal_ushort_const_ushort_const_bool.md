# CSyncRootManagerBroker::UnregisterShellFolderInternal(ushort const *,ushort const *,bool *)

- ea: `0x18034cc0c`
- end: `0x18034d06a`
- name: `?UnregisterShellFolderInternal@CSyncRootManagerBroker@@AEAAJPEBG0PEA_N@Z`
- size: `1118`
- prototype: `int(CSyncRootManagerBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180240d50`
- `0x18034c990`
- `0x180579600`

## callees

- `0x180012d30`
- `0x18002f7c0`
- `0x1800442d0`
- `0x180079ccc`
- `0x1800899a4`
- `0x1800b5d60`
- `0x1801720d0`
- `0x1801f4760`
- `0x1801ff4d0`
- `0x1802422dc`
- `0x18034cc0c`
- `0x18034dfc0`
- `0x1803b1f60`
- `0x1804efabc`
- `0x180577420`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18034ce0a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18034ce0a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034cdc8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034cdc8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18034ced2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18034cf2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18034cfdf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18034ced2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18034cf2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18034cfdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18034ce55`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18034cf94`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18034ce55`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18034cf94`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18034ccc3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18034ccc3`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18034cf72`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18034cf72`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryInfoKeyW` at `0x18034cd10`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryInfoKeyW` at `0x18034cd10`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18034cd80`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18034cd80`

## string_xrefs

- `0x18034cede`: `Software\Classes\CLSID\`
- `0x18034cde8`: `NamespaceCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CSyncRootManagerBroker::UnregisterShellFolderInternal(
        CSyncRootManagerBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  const unsigned __int16 **v7; // rdx
  int SyncRootManagerRegistryLocation; // eax
  unsigned int v9; // eax
  LSTATUS v10; // eax
  DWORD v11; // edi
  __int64 v12; // rbx
  LSTATUS v13; // eax
  int v14; // r9d
  unsigned int v15; // eax
  __int64 v16; // r8
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rdx
  const WCHAR *v19; // rdx
  unsigned int v20; // eax
  const WCHAR *v21; // rdx
  int dwOptions; // [rsp+20h] [rbp-F8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-F8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-F8h]
  unsigned int *samDesired; // [rsp+28h] [rbp-F0h]
  DWORD pcchMaxSubKeyLen; // [rsp+50h] [rbp-C8h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-C0h] BYREF
  DWORD pcchName[2]; // [rsp+60h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-B0h] BYREF
  DWORD pcSubKeys; // [rsp+70h] [rbp-A8h] BYREF
  LPWSTR pszName; // [rsp+78h] [rbp-A0h] BYREF
  LPCWSTR v33[3]; // [rsp+80h] [rbp-98h] BYREF
  unsigned __int64 v34; // [rsp+98h] [rbp-80h]
  LPCWSTR Src[4]; // [rsp+A0h] [rbp-78h] BYREF
  LPCWSTR pszSubKey[4]; // [rsp+C0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  lpSubKey = a2;
  CloudFilesTelemetry::UnregisterShellFolder<unsigned short const * &>(&lpSubKey);
  *a4 = 0;
  lpSubKey = 0;
  SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                      (Windows::Internal::SyncRootHelpers *)&lpSubKey,
                                      v7);
  if ( SyncRootManagerRegistryLocation < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)SyncRootManagerRegistryLocation,
      dwOptions);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20119u, 0, &hkey, 0);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x57F,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v9,
      dwOptionsa);
  pcSubKeys = 0;
  pcchMaxSubKeyLen = 0;
  v10 = SHQueryInfoKeyW(hkey, &pcSubKeys, &pcchMaxSubKeyLen, 0, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x583,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v10,
      dwOptionsb);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pszName,
    0,
    ++pcchMaxSubKeyLen);
  v11 = 0;
  v12 = -1;
  while ( v11 < pcSubKeys )
  {
    pcchName[0] = pcchMaxSubKeyLen;
    v13 = SHEnumKeyExW(hkey, v11, pszName, pcchName);
    if ( v13 >= 0 )
    {
      if ( !a3 || CompareStringOrdinal(pszName, -1, a3, -1, 1) != 2 )
      {
        lpSubKey = 0;
        if ( SHRegAllocData(hkey, pszName, L"NamespaceCLSID", v14, (void **)&lpSubKey, samDesired) >= 0
          && !(unsigned int)_o__wcsicmp(a2, lpSubKey) )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
          goto LABEL_35;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58C,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v13,
        dwOptionsb);
    }
    ++v11;
  }
  *(_QWORD *)pcchName = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    pcchName,
    0);
  v15 = RegOpenCurrentUser(0xF013Fu, (PHKEY)pcchName);
  if ( v15 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v15,
      dwOptionsb);
  std::wstring::wstring(Src, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Desktop\\Namespace\\");
  v16 = -1;
  do
    ++v16;
  while ( a2[v16] );
  std::wstring::_Append<unsigned short>(Src);
  v17 = (const WCHAR *)Src;
  if ( Src[3] > (LPCWSTR)7 )
    v17 = Src[0];
  RegDeleteTreeW(*(HKEY *)pcchName, v17);
  std::wstring::wstring(v33, L"Software\\Classes\\CLSID\\");
  do
    ++v12;
  while ( a2[v12] );
  std::wstring::_Append<unsigned short>(v33);
  v18 = (const WCHAR *)v33;
  if ( v34 > 7 )
    v18 = v33[0];
  RegDeleteTreeW(*(HKEY *)pcchName, v18);
  std::wstring::wstring(
    pszSubKey,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\HideDesktopIcons\\NewStartPanel");
  v19 = (const WCHAR *)pszSubKey;
  if ( pszSubKey[3] > (LPCWSTR)7 )
    v19 = pszSubKey[0];
  SHDeleteValueW(*(HKEY *)pcchName, v19, a2);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    pcchName,
    0);
  v20 = RegOpenCurrentUser(0xF023Fu, (PHKEY)pcchName);
  if ( v20 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5AF,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v20,
      dwOptionsb);
  v21 = (const WCHAR *)v33;
  if ( v34 > 7 )
    v21 = v33[0];
  RegDeleteTreeW(*(HKEY *)pcchName, v21);
  *a4 = 1;
  std::pair<std::wstring,int>::~pair<std::wstring,int>(pszSubKey);
  std::pair<std::wstring,int>::~pair<std::wstring,int>(v33);
  std::pair<std::wstring,int>::~pair<std::wstring,int>(Src);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(pcchName);
LABEL_35:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x18034cc0c  mov     [rsp+arg_0], rbx
0x18034cc11  push    rsi
0x18034cc12  push    rdi
0x18034cc13  push    r12
0x18034cc15  push    r14
0x18034cc17  push    r15
0x18034cc19  sub     rsp, 0F0h
0x18034cc20  mov     rax, cs:__security_cookie
0x18034cc27  xor     rax, rsp
0x18034cc2a  mov     [rsp+118h+var_38], rax
0x18034cc32  mov     r15, r9
0x18034cc35  mov     r14, r8
0x18034cc38  mov     rsi, rdx
0x18034cc3b  mov     [rsp+118h+lpSubKey], rdx
0x18034cc40  xor     r12d, r12d
0x18034cc43  lea     rcx, [rsp+118h+lpSubKey]
0x18034cc48  call    ??$UnregisterShellFolder@AEAPEBG@CloudFilesTelemetry@@SAXAEAPEBG@Z; CloudFilesTelemetry::UnregisterShellFolder<ushort const * &>(ushort const * &)
0x18034cc4d  mov     [r15], r12b
0x18034cc50  mov     [rsp+118h+lpSubKey], r12
0x18034cc55  lea     rcx, [rsp+118h+lpSubKey]; this
0x18034cc5a  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x18034cc5f  mov     rcx, [rsp+118h]; this
0x18034cc67  test    eax, eax
0x18034cc69  jns     short loc_18034CC7F
0x18034cc6b  mov     r9d, eax; char *
0x18034cc6e  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18034cc75  mov     edx, 57Dh; void *
0x18034cc7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18034cc7f  mov     [rsp+118h+hkey], r12
0x18034cc84  xor     edx, edx
0x18034cc86  lea     rcx, [rsp+118h+hkey]
0x18034cc8b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18034cc90  mov     [rsp+118h+lpdwDisposition], r12; lpdwDisposition
0x18034cc95  lea     rax, [rsp+118h+hkey]
0x18034cc9a  mov     [rsp+118h+phkResult], rax; phkResult
0x18034cc9f  mov     [rsp+118h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18034cca4  mov     dword ptr [rsp+118h+samDesired], 20119h; unsigned int *
0x18034ccac  mov     [rsp+118h+dwOptions], r12d; unsigned int
0x18034ccb1  xor     r9d, r9d; lpClass
0x18034ccb4  xor     r8d, r8d; Reserved
0x18034ccb7  mov     rdx, [rsp+118h+lpSubKey]; lpSubKey
0x18034ccbc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18034ccc3  call    cs:__imp_RegCreateKeyExW
0x18034ccca  nop     dword ptr [rax+rax+00h]
0x18034cccf  mov     rcx, [rsp+118h]; this
0x18034ccd7  test    eax, eax
0x18034ccd9  jz      short loc_18034CCEF
0x18034ccdb  mov     r9d, eax; char *
0x18034ccde  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18034cce5  mov     edx, 57Fh; void *
0x18034ccea  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18034ccef  mov     [rsp+118h+pcSubKeys], r12d
0x18034ccf4  mov     [rsp+118h+pcchMaxSubKeyLen], r12d
0x18034ccf9  mov     qword ptr [rsp+118h+dwOptions], r12; unsigned int
0x18034ccfe  xor     r9d, r9d; pcValues
0x18034cd01  lea     r8, [rsp+118h+pcchMaxSubKeyLen]; pcchMaxSubKeyLen
0x18034cd06  lea     rdx, [rsp+118h+pcSubKeys]; pcSubKeys
0x18034cd0b  mov     rcx, [rsp+118h+hkey]; hkey
0x18034cd10  call    cs:__imp_SHQueryInfoKeyW
0x18034cd17  nop     dword ptr [rax+rax+00h]
0x18034cd1c  mov     rcx, [rsp+118h]; this
0x18034cd24  test    eax, eax
0x18034cd26  jns     short loc_18034CD3C
0x18034cd28  mov     r9d, eax; char *
0x18034cd2b  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18034cd32  mov     edx, 583h; void *
0x18034cd37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18034cd3c  mov     eax, [rsp+118h+pcchMaxSubKeyLen]
0x18034cd40  inc     eax
0x18034cd42  mov     [rsp+118h+pcchMaxSubKeyLen], eax
0x18034cd46  mov     r8d, eax
0x18034cd49  xor     edx, edx
0x18034cd4b  lea     rcx, [rsp+118h+pszName]
0x18034cd50  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18034cd55  nop
0x18034cd56  mov     edi, r12d
0x18034cd59  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18034cd5d  cmp     edi, [rsp+118h+pcSubKeys]
0x18034cd61  jnb     loc_18034CE3A
0x18034cd67  mov     eax, [rsp+118h+pcchMaxSubKeyLen]
0x18034cd6b  mov     [rsp+118h+pcchName], eax
0x18034cd6f  lea     r9, [rsp+118h+pcchName]; pcchName
0x18034cd74  mov     r8, [rsp+118h+pszName]; pszName
0x18034cd79  mov     edx, edi; dwIndex
0x18034cd7b  mov     rcx, [rsp+118h+hkey]; hkey
0x18034cd80  call    cs:__imp_SHEnumKeyExW
0x18034cd87  nop     dword ptr [rax+rax+00h]
0x18034cd8c  mov     rcx, [rsp+118h]; this
0x18034cd94  test    eax, eax
0x18034cd96  jns     short loc_18034CDAE
0x18034cd98  mov     r9d, eax; char *
0x18034cd9b  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18034cda2  mov     edx, 58Ch; void *
0x18034cda7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18034cdac  jmp     short loc_18034CE24
0x18034cdae  test    r14, r14
0x18034cdb1  jz      short loc_18034CDD9
0x18034cdb3  mov     [rsp+118h+dwOptions], 1; bIgnoreCase
0x18034cdbb  mov     r9d, ebx; cchCount2
0x18034cdbe  mov     r8, r14; lpString2
0x18034cdc1  mov     edx, ebx; cchCount1
0x18034cdc3  mov     rcx, [rsp+118h+pszName]; lpString1
0x18034cdc8  call    cs:__imp_CompareStringOrdinal
0x18034cdcf  nop     dword ptr [rax+rax+00h]
0x18034cdd4  cmp     eax, 2
0x18034cdd7  jz      short loc_18034CE24
0x18034cdd9  mov     [rsp+118h+lpSubKey], r12
0x18034cdde  lea     rax, [rsp+118h+lpSubKey]
0x18034cde3  mov     qword ptr [rsp+118h+dwOptions], rax; void **
0x18034cde8  lea     r8, aNamespaceclsid; "NamespaceCLSID"
0x18034cdef  mov     rdx, [rsp+118h+pszName]; unsigned __int16 *
0x18034cdf4  mov     rcx, [rsp+118h+hkey]; HKEY
0x18034cdf9  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18034cdfe  test    eax, eax
0x18034ce00  js      short loc_18034CE1A
0x18034ce02  mov     rdx, [rsp+118h+lpSubKey]
0x18034ce07  mov     rcx, rsi
0x18034ce0a  call    cs:__imp__o__wcsicmp
0x18034ce11  nop     dword ptr [rax+rax+00h]
0x18034ce16  test    eax, eax
0x18034ce18  jz      short loc_18034CE2B
0x18034ce1a  lea     rcx, [rsp+118h+lpSubKey]; void *
0x18034ce1f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18034ce24  inc     edi
0x18034ce26  jmp     loc_18034CD5D
0x18034ce2b  lea     rcx, [rsp+118h+lpSubKey]; void *
0x18034ce30  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18034ce35  jmp     loc_18034D024
0x18034ce3a  mov     qword ptr [rsp+118h+pcchName], r12
0x18034ce3f  xor     edx, edx
0x18034ce41  lea     rcx, [rsp+118h+pcchName]
0x18034ce46  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18034ce4b  lea     rdx, [rsp+118h+pcchName]; phkResult
0x18034ce50  mov     ecx, 0F013Fh; samDesired
0x18034ce55  call    cs:__imp_RegOpenCurrentUser
0x18034ce5c  nop     dword ptr [rax+rax+00h]
0x18034ce61  mov     rcx, [rsp+118h]; this
0x18034ce69  test    eax, eax
0x18034ce6b  jz      short loc_18034CE81
0x18034ce6d  mov     r9d, eax; char *
0x18034ce70  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18034ce77  mov     edx, 5A1h; void *
0x18034ce7c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18034ce81  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18034ce88  lea     rcx, [rsp+118h+Src]
0x18034ce90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18034ce95  nop
0x18034ce96  mov     r8, rbx
0x18034ce99  inc     r8
0x18034ce9c  cmp     [rsi+r8*2], r12w
0x18034cea1  jnz     short loc_18034CE99
0x18034cea3  mov     rdx, rsi
0x18034cea6  lea     rcx, [rsp+118h+Src]; Src
0x18034ceae  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18034ceb3  lea     rdx, [rsp+118h+Src]
0x18034cebb  cmp     [rsp+118h+var_60], 7
0x18034cec4  cmova   rdx, [rsp+118h+Src]; lpSubKey
0x18034cecd  mov     rcx, qword ptr [rsp+118h+pcchName]; hKey
0x18034ced2  call    cs:__imp_RegDeleteTreeW
0x18034ced9  nop     dword ptr [rax+rax+00h]
0x18034cede  lea     rdx, aSoftwareClasse_4; "Software\\Classes\\CLSID\\"
0x18034cee5  lea     rcx, [rsp+118h+var_98]
0x18034ceed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18034cef2  nop
0x18034cef3  inc     rbx
0x18034cef6  cmp     [rsi+rbx*2], r12w
0x18034cefb  jnz     short loc_18034CEF3
0x18034cefd  mov     r8, rbx
0x18034cf00  mov     rdx, rsi
0x18034cf03  lea     rcx, [rsp+118h+var_98]; Src
0x18034cf0b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18034cf10  lea     rdx, [rsp+118h+var_98]
0x18034cf18  cmp     [rsp+118h+var_80], 7
0x18034cf21  cmova   rdx, [rsp+118h+var_98]; lpSubKey
0x18034cf2a  mov     rcx, qword ptr [rsp+118h+pcchName]; hKey
0x18034cf2f  call    cs:__imp_RegDeleteTreeW
0x18034cf36  nop     dword ptr [rax+rax+00h]
0x18034cf3b  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18034cf42  lea     rcx, [rsp+118h+pszSubKey]
0x18034cf4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18034cf4f  nop
0x18034cf50  lea     rdx, [rsp+118h+pszSubKey]
0x18034cf58  cmp     [rsp+118h+var_40], 7
0x18034cf61  cmova   rdx, [rsp+118h+pszSubKey]; pszSubKey
0x18034cf6a  mov     r8, rsi; pszValue
0x18034cf6d  mov     rcx, qword ptr [rsp+118h+pcchName]; hkey
0x18034cf72  call    cs:__imp_SHDeleteValueW
0x18034cf79  nop     dword ptr [rax+rax+00h]
0x18034cf7e  xor     edx, edx
0x18034cf80  lea     rcx, [rsp+118h+pcchName]
0x18034cf85  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18034cf8a  lea     rdx, [rsp+118h+pcchName]; phkResult
0x18034cf8f  mov     ecx, 0F023Fh; samDesired
0x18034cf94  call    cs:__imp_RegOpenCurrentUser
0x18034cf9b  nop     dword ptr [rax+rax+00h]
0x18034cfa0  mov     rcx, [rsp+118h]; this
0x18034cfa8  test    eax, eax
0x18034cfaa  jz      short loc_18034CFC0
0x18034cfac  mov     r9d, eax; char *
0x18034cfaf  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18034cfb6  mov     edx, 5AFh; void *
0x18034cfbb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18034cfc0  lea     rdx, [rsp+118h+var_98]
0x18034cfc8  cmp     [rsp+118h+var_80], 7
0x18034cfd1  cmova   rdx, [rsp+118h+var_98]; lpSubKey
0x18034cfda  mov     rcx, qword ptr [rsp+118h+pcchName]; hKey
0x18034cfdf  call    cs:__imp_RegDeleteTreeW
0x18034cfe6  nop     dword ptr [rax+rax+00h]
0x18034cfeb  mov     byte ptr [r15], 1
0x18034cfef  lea     rcx, [rsp+118h+pszSubKey]; void *
0x18034cff7  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@QEAA@XZ; std::pair<std::wstring,int>::~pair<std::wstring,int>(void)
0x18034cffc  nop
0x18034cffd  lea     rcx, [rsp+118h+var_98]; void *
0x18034d005  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@QEAA@XZ; std::pair<std::wstring,int>::~pair<std::wstring,int>(void)
0x18034d00a  nop
0x18034d00b  lea     rcx, [rsp+118h+Src]; void *
0x18034d013  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@QEAA@XZ; std::pair<std::wstring,int>::~pair<std::wstring,int>(void)
0x18034d018  nop
0x18034d019  lea     rcx, [rsp+118h+pcchName]
0x18034d01e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18034d023  nop
0x18034d024  lea     rcx, [rsp+118h+pszName]; void *
0x18034d029  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18034d02e  nop
0x18034d02f  lea     rcx, [rsp+118h+hkey]
0x18034d034  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18034d039  xor     eax, eax
0x18034d03b  jmp     short loc_18034D041
0x18034d03d  mov     eax, [rsp+118h+pcchName]
0x18034d041  mov     rcx, [rsp+118h+var_38]
0x18034d049  xor     rcx, rsp; StackCookie
0x18034d04c  call    __security_check_cookie
0x18034d051  mov     rbx, [rsp+118h+arg_0]
0x18034d059  add     rsp, 0F0h
0x18034d060  pop     r15
0x18034d062  pop     r14
0x18034d064  pop     r12
0x18034d066  pop     rdi
0x18034d067  pop     rsi
0x18034d068  retn
```
