# CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x1802419c0`
- end: `0x180241f8e`
- name: `?RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z`
- size: `1486`
- prototype: `void(CSyncRootManagerBroker *__hidden this, HKEY, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180240d50`

## callees

- `0x180079ccc`
- `0x1800b5d60`
- `0x1801bc4d4`
- `0x1802419c0`
- `0x18036e998`
- `0x1803b1f60`
- `0x1804efabc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241b4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241b97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241ce2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241d91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241e70`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241eba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241b4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241b97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241ce2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241d91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241e70`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241eba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241eec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241eec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241f5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241a3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241ad2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241bfc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241c91`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241d47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241e26`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241a3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241ad2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241bfc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241c91`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241d47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241e26`

## string_xrefs

- `0x180241cd7`: `CLSID`
- `0x180241dbd`: `TargetFolderPath`
- `0x180241c25`: `%SystemRoot%\system32\shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CSyncRootManagerBroker::RegisterShellFolderCLSID(
        CSyncRootManagerBroker *this,
        HKEY a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  REGSAM samDesired; // esi
  unsigned int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsg; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsh; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsi; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsj; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsk; // [rsp+20h] [rbp-61h]
  HKEY hKey; // [rsp+50h] [rbp-31h] BYREF
  HKEY v43; // [rsp+58h] [rbp-29h] BYREF
  HKEY v44; // [rsp+60h] [rbp-21h] BYREF
  HKEY v45; // [rsp+68h] [rbp-19h] BYREF
  HKEY v46; // [rsp+70h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  samDesired = a4 | 0x20006;
  v11 = RegCreateKeyExW(a2, a3, 0, 0, 0, samDesired, 0, &hKey, 0);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5EA,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v11,
      dwOptions);
  v12 = SHRegSetString(hKey, 0, 0, a5);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5EC,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v12,
      dwOptions);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v13 = RegCreateKeyExW(hKey, L"DefaultIcon", 0, 0, 0, samDesired, 0, &phkResult, 0);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5EF,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v13,
      dwOptionsa);
  v15 = SHRegSetExpandStringW(phkResult, v14, 0, a6);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F0,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v15,
      dwOptionsa);
  v16 = RegSetValueExW(
          hKey,
          L"System.IsPinnedToNamespaceTree",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::pinnedState,
          4u);
  if ( v16 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v16,
      dwOptionsb);
  v17 = RegSetValueExW(
          hKey,
          L"SortOrderIndex",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::sortOrder,
          4u);
  if ( v17 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F5,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v17,
      dwOptionsc);
  v46 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v46,
    0);
  v18 = RegCreateKeyExW(hKey, L"InProcServer32", 0, 0, 0, samDesired, 0, &v46, 0);
  if ( v18 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v18,
      dwOptionsd);
  v20 = SHRegSetExpandStringW(v46, v19, 0, L"%SystemRoot%\\system32\\shell32.dll");
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5FA,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v20,
      dwOptionsd);
  v45 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v45,
    0);
  v21 = RegCreateKeyExW(hKey, L"Instance", 0, 0, 0, samDesired, 0, &v45, 0);
  if ( v21 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5FD,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v21,
      dwOptionse);
  v22 = RegSetValueExW(v45, L"CLSID", 0, 1u, L"{0E5AAE11-A475-4c5b-AB00-C66DE400274E}", 0x4Cu);
  if ( v22 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5FF,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v22,
      dwOptionsf);
  v44 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v44,
    0);
  v23 = RegCreateKeyExW(v45, L"InitPropertyBag", 0, 0, 0, samDesired, 0, &v44, 0);
  if ( v23 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x602,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v23,
      dwOptionsg);
  v24 = RegSetValueExW(
          v44,
          L"Attributes",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::attributes,
          4u);
  if ( v24 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x604,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v24,
      dwOptionsh);
  v26 = SHRegSetExpandStringW(v44, v25, L"TargetFolderPath", a7);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v26,
      dwOptionsh);
  v43 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v43,
    0);
  v27 = RegCreateKeyExW(hKey, L"ShellFolder", 0, 0, 0, samDesired, 0, &v43, 0);
  if ( v27 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x609,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v27,
      dwOptionsi);
  v28 = RegSetValueExW(
          v43,
          L"FolderValueFlags",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::folderValueFlags,
          4u);
  if ( v28 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x60B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v28,
      dwOptionsj);
  v29 = RegSetValueExW(v43, L"Attributes", 0, 4u, "M", 4u);
  if ( v29 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x60D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v29,
      dwOptionsk);
  if ( v43 )
    RegCloseKey(v43);
  if ( v44 )
    RegCloseKey(v44);
  if ( v45 )
    RegCloseKey(v45);
  if ( v46 )
    RegCloseKey(v46);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1802419c0  mov     [rsp-8+arg_0], rbx
0x1802419c5  push    rbp
0x1802419c6  push    rsi
0x1802419c7  push    rdi
0x1802419c8  push    r12
0x1802419ca  push    r13
0x1802419cc  push    r14
0x1802419ce  push    r15
0x1802419d0  lea     rbp, [rsp-0Fh]
0x1802419d5  sub     rsp, 90h
0x1802419dc  mov     rax, cs:__security_cookie
0x1802419e3  xor     rax, rsp
0x1802419e6  mov     [rbp+3Fh+var_40], rax
0x1802419ea  mov     esi, r9d
0x1802419ed  mov     rdi, r8
0x1802419f0  mov     rbx, rdx
0x1802419f3  mov     r14, [rbp+3Fh+arg_20]
0x1802419f7  mov     r15, [rbp+3Fh+arg_28]
0x1802419fb  mov     r12, [rbp+3Fh+arg_30]
0x1802419ff  xor     r13d, r13d
0x180241a02  mov     [rbp+3Fh+hKey], r13
0x180241a06  xor     edx, edx
0x180241a08  lea     rcx, [rbp+3Fh+hKey]
0x180241a0c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180241a11  or      esi, 20006h
0x180241a17  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180241a1c  lea     rax, [rbp+3Fh+hKey]
0x180241a20  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180241a25  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180241a2a  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180241a2e  mov     [rsp+0C0h+dwOptions], r13d; int
0x180241a33  xor     r9d, r9d; lpClass
0x180241a36  xor     r8d, r8d; Reserved
0x180241a39  mov     rdx, rdi; lpSubKey
0x180241a3c  mov     rcx, rbx; hKey
0x180241a3f  call    cs:__imp_RegCreateKeyExW
0x180241a46  nop     dword ptr [rax+rax+00h]
0x180241a4b  mov     rcx, [rbp+47h]; this
0x180241a4f  test    eax, eax
0x180241a51  jz      short loc_180241A68
0x180241a53  mov     r9d, eax; char *
0x180241a56  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241a5d  mov     edx, 5EAh; void *
0x180241a62  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241a68  mov     r9, r14; unsigned __int16 *
0x180241a6b  xor     r8d, r8d; unsigned __int16 *
0x180241a6e  xor     edx, edx; unsigned __int16 *
0x180241a70  mov     rcx, [rbp+3Fh+hKey]; HKEY
0x180241a74  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180241a79  mov     rcx, [rbp+47h]; this
0x180241a7d  test    eax, eax
0x180241a7f  jns     short loc_180241A96
0x180241a81  mov     r9d, eax; char *
0x180241a84  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241a8b  mov     edx, 5ECh; void *
0x180241a90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180241a96  mov     [rbp+3Fh+var_48], r13
0x180241a9a  xor     edx, edx
0x180241a9c  lea     rcx, [rbp+3Fh+var_48]
0x180241aa0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180241aa5  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180241aaa  lea     rax, [rbp+3Fh+var_48]
0x180241aae  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180241ab3  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180241ab8  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180241abc  mov     [rsp+0C0h+dwOptions], r13d; int
0x180241ac1  xor     r9d, r9d; lpClass
0x180241ac4  xor     r8d, r8d; Reserved
0x180241ac7  lea     rdx, aDefaulticon; "DefaultIcon"
0x180241ace  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180241ad2  call    cs:__imp_RegCreateKeyExW
0x180241ad9  nop     dword ptr [rax+rax+00h]
0x180241ade  mov     rcx, [rbp+47h]; this
0x180241ae2  test    eax, eax
0x180241ae4  jz      short loc_180241AFB
0x180241ae6  mov     r9d, eax; char *
0x180241ae9  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241af0  mov     edx, 5EFh; void *
0x180241af5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241afb  mov     r9, r15
0x180241afe  xor     r8d, r8d
0x180241b01  mov     rcx, [rbp+3Fh+var_48]
0x180241b05  call    SHRegSetExpandStringW
0x180241b0a  mov     rcx, [rbp+47h]; this
0x180241b0e  test    eax, eax
0x180241b10  jns     short loc_180241B27
0x180241b12  mov     r9d, eax; char *
0x180241b15  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241b1c  mov     edx, 5F0h; void *
0x180241b21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180241b27  mov     ebx, 4
0x180241b2c  mov     [rsp+0C0h+samDesired], ebx; cbData
0x180241b30  lea     rax, ?pinnedState@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::pinnedState
0x180241b37  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x180241b3c  mov     r9d, ebx; dwType
0x180241b3f  xor     r8d, r8d; Reserved
0x180241b42  lea     rdx, aSystemIspinned; "System.IsPinnedToNamespaceTree"
0x180241b49  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180241b4d  call    cs:__imp_RegSetValueExW
0x180241b54  nop     dword ptr [rax+rax+00h]
0x180241b59  mov     rcx, [rbp+47h]; this
0x180241b5d  test    eax, eax
0x180241b5f  jz      short loc_180241B76
0x180241b61  mov     r9d, eax; char *
0x180241b64  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241b6b  mov     edx, 5F3h; void *
0x180241b70  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241b76  mov     [rsp+0C0h+samDesired], ebx; cbData
0x180241b7a  lea     rax, ?sortOrder@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::sortOrder
0x180241b81  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x180241b86  mov     r9d, ebx; dwType
0x180241b89  xor     r8d, r8d; Reserved
0x180241b8c  lea     rdx, aSortorderindex; "SortOrderIndex"
0x180241b93  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180241b97  call    cs:__imp_RegSetValueExW
0x180241b9e  nop     dword ptr [rax+rax+00h]
0x180241ba3  mov     rcx, [rbp+47h]; this
0x180241ba7  test    eax, eax
0x180241ba9  jz      short loc_180241BC0
0x180241bab  mov     r9d, eax; char *
0x180241bae  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241bb5  mov     edx, 5F5h; void *
0x180241bba  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241bc0  mov     [rbp+3Fh+var_50], r13
0x180241bc4  xor     edx, edx
0x180241bc6  lea     rcx, [rbp+3Fh+var_50]
0x180241bca  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180241bcf  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180241bd4  lea     rax, [rbp+3Fh+var_50]
0x180241bd8  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180241bdd  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180241be2  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180241be6  mov     [rsp+0C0h+dwOptions], r13d; int
0x180241beb  xor     r9d, r9d; lpClass
0x180241bee  xor     r8d, r8d; Reserved
0x180241bf1  lea     rdx, aInprocserver32_0; "InProcServer32"
0x180241bf8  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180241bfc  call    cs:__imp_RegCreateKeyExW
0x180241c03  nop     dword ptr [rax+rax+00h]
0x180241c08  mov     rcx, [rbp+47h]; this
0x180241c0c  test    eax, eax
0x180241c0e  jz      short loc_180241C25
0x180241c10  mov     r9d, eax; char *
0x180241c13  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241c1a  mov     edx, 5F8h; void *
0x180241c1f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241c25  lea     r9, aSystemrootSyst_1; "%SystemRoot%\\system32\\shell32.dll"
0x180241c2c  xor     r8d, r8d
0x180241c2f  mov     rcx, [rbp+3Fh+var_50]
0x180241c33  call    SHRegSetExpandStringW
0x180241c38  mov     rcx, [rbp+47h]; this
0x180241c3c  test    eax, eax
0x180241c3e  jns     short loc_180241C55
0x180241c40  mov     r9d, eax; char *
0x180241c43  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241c4a  mov     edx, 5FAh; void *
0x180241c4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180241c55  mov     [rbp+3Fh+var_58], r13
0x180241c59  xor     edx, edx
0x180241c5b  lea     rcx, [rbp+3Fh+var_58]
0x180241c5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180241c64  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180241c69  lea     rax, [rbp+3Fh+var_58]
0x180241c6d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180241c72  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180241c77  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180241c7b  mov     [rsp+0C0h+dwOptions], r13d; unsigned int
0x180241c80  xor     r9d, r9d; lpClass
0x180241c83  xor     r8d, r8d; Reserved
0x180241c86  lea     rdx, aInstance; "Instance"
0x180241c8d  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180241c91  call    cs:__imp_RegCreateKeyExW
0x180241c98  nop     dword ptr [rax+rax+00h]
0x180241c9d  mov     rcx, [rbp+47h]; this
0x180241ca1  test    eax, eax
0x180241ca3  jz      short loc_180241CBA
0x180241ca5  mov     r9d, eax; char *
0x180241ca8  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241caf  mov     edx, 5FDh; void *
0x180241cb4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241cba  mov     [rsp+0C0h+samDesired], 4Ch ; 'L'; cbData
0x180241cc2  lea     rax, Data; "{0E5AAE11-A475-4c5b-AB00-C66DE400274E}"
0x180241cc9  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x180241cce  mov     r9d, 1; dwType
0x180241cd4  xor     r8d, r8d; Reserved
0x180241cd7  lea     rdx, aClsid_3; "CLSID"
0x180241cde  mov     rcx, [rbp+3Fh+var_58]; hKey
0x180241ce2  call    cs:__imp_RegSetValueExW
0x180241ce9  nop     dword ptr [rax+rax+00h]
0x180241cee  mov     rcx, [rbp+47h]; this
0x180241cf2  test    eax, eax
0x180241cf4  jz      short loc_180241D0B
0x180241cf6  mov     r9d, eax; char *
0x180241cf9  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241d00  mov     edx, 5FFh; void *
0x180241d05  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241d0b  mov     [rbp+3Fh+var_60], r13
0x180241d0f  xor     edx, edx
0x180241d11  lea     rcx, [rbp+3Fh+var_60]
0x180241d15  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180241d1a  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180241d1f  lea     rax, [rbp+3Fh+var_60]
0x180241d23  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180241d28  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180241d2d  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180241d31  mov     [rsp+0C0h+dwOptions], r13d; unsigned int
0x180241d36  xor     r9d, r9d; lpClass
0x180241d39  xor     r8d, r8d; Reserved
0x180241d3c  lea     rdx, aInitpropertyba; "InitPropertyBag"
0x180241d43  mov     rcx, [rbp+3Fh+var_58]; hKey
0x180241d47  call    cs:__imp_RegCreateKeyExW
0x180241d4e  nop     dword ptr [rax+rax+00h]
0x180241d53  mov     rcx, [rbp+47h]; this
0x180241d57  test    eax, eax
0x180241d59  jz      short loc_180241D70
0x180241d5b  mov     r9d, eax; char *
0x180241d5e  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241d65  mov     edx, 602h; void *
0x180241d6a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241d70  mov     [rsp+0C0h+samDesired], ebx; cbData
0x180241d74  lea     rax, ?attributes@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::attributes
0x180241d7b  mov     qword ptr [rsp+0C0h+dwOptions], rax; int
0x180241d80  mov     r9d, ebx; dwType
0x180241d83  xor     r8d, r8d; Reserved
0x180241d86  lea     rdx, aAttributes; "Attributes"
0x180241d8d  mov     rcx, [rbp+3Fh+var_60]; hKey
0x180241d91  call    cs:__imp_RegSetValueExW
0x180241d98  nop     dword ptr [rax+rax+00h]
0x180241d9d  mov     rcx, [rbp+47h]; this
0x180241da1  test    eax, eax
0x180241da3  jz      short loc_180241DBA
0x180241da5  mov     r9d, eax; char *
0x180241da8  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241daf  mov     edx, 604h; void *
0x180241db4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241dba  mov     r9, r12
0x180241dbd  lea     r8, aTargetfolderpa; "TargetFolderPath"
0x180241dc4  mov     rcx, [rbp+3Fh+var_60]
0x180241dc8  call    SHRegSetExpandStringW
0x180241dcd  mov     rcx, [rbp+47h]; this
0x180241dd1  test    eax, eax
0x180241dd3  jns     short loc_180241DEA
0x180241dd5  mov     r9d, eax; char *
0x180241dd8  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241ddf  mov     edx, 606h; void *
0x180241de4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180241dea  mov     [rbp+3Fh+var_68], r13
0x180241dee  xor     edx, edx
0x180241df0  lea     rcx, [rbp+3Fh+var_68]
0x180241df4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180241df9  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180241dfe  lea     rax, [rbp+3Fh+var_68]
0x180241e02  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180241e07  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180241e0c  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180241e10  mov     [rsp+0C0h+dwOptions], r13d; unsigned int
0x180241e15  xor     r9d, r9d; lpClass
0x180241e18  xor     r8d, r8d; Reserved
0x180241e1b  lea     rdx, pszSubKey; "ShellFolder"
0x180241e22  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180241e26  call    cs:__imp_RegCreateKeyExW
0x180241e2d  nop     dword ptr [rax+rax+00h]
0x180241e32  mov     rcx, [rbp+47h]; this
0x180241e36  test    eax, eax
0x180241e38  jz      short loc_180241E4F
0x180241e3a  mov     r9d, eax; char *
0x180241e3d  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241e44  mov     edx, 609h; void *
0x180241e49  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241e4f  mov     [rsp+0C0h+samDesired], ebx; cbData
0x180241e53  lea     rax, ?folderValueFlags@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::folderValueFlags
0x180241e5a  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x180241e5f  mov     r9d, ebx; dwType
0x180241e62  xor     r8d, r8d; Reserved
0x180241e65  lea     rdx, aFoldervaluefla; "FolderValueFlags"
0x180241e6c  mov     rcx, [rbp+3Fh+var_68]; hKey
0x180241e70  call    cs:__imp_RegSetValueExW
0x180241e77  nop     dword ptr [rax+rax+00h]
0x180241e7c  mov     rcx, [rbp+47h]; this
0x180241e80  test    eax, eax
0x180241e82  jz      short loc_180241E99
0x180241e84  mov     r9d, eax; char *
0x180241e87  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241e8e  mov     edx, 60Bh; void *
0x180241e93  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180241e99  mov     [rsp+0C0h+samDesired], ebx; cbData
0x180241e9d  lea     rax, ?folderAttributes@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; "M"
0x180241ea4  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x180241ea9  mov     r9d, ebx; dwType
0x180241eac  xor     r8d, r8d; Reserved
0x180241eaf  lea     rdx, aAttributes; "Attributes"
0x180241eb6  mov     rcx, [rbp+3Fh+var_68]; hKey
0x180241eba  call    cs:__imp_RegSetValueExW
0x180241ec1  nop     dword ptr [rax+rax+00h]
0x180241ec6  mov     rcx, [rbp+47h]; this
0x180241eca  test    eax, eax
0x180241ecc  jz      short loc_180241EE3
0x180241ece  mov     r9d, eax; char *
0x180241ed1  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180241ed8  mov     edx, 60Dh; void *
  ... truncated ...
```
