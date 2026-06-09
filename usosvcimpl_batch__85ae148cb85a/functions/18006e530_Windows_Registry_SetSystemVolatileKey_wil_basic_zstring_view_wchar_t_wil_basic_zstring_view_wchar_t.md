# Windows::Registry::SetSystemVolatileKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18006e530`
- end: `0x18006e629`
- name: `?SetSystemVolatileKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180011680`
- `0x18006e530`
- `0x180083c20`
- `0x1800855a0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e604`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e5bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e5bd`

## string_xrefs

- `0x18006e5e9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Registry::SetSystemVolatileKey(__int64 a1, __int128 *a2, __int128 *a3)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  LPCWSTR *v5; // rdx
  __int128 v6; // [rsp+50h] [rbp+7h] BYREF
  __int128 v7; // [rsp+60h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+27h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp+2Fh] BYREF
  unsigned __int64 v10; // [rsp+90h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v6 = *a3;
  v7 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, (__int64)lpSubKey, (const char **)&v7, (__int64)&v6);
  hKey = 0;
  v3 = (const WCHAR *)lpSubKey;
  if ( v10 > 7 )
    v3 = lpSubKey[0];
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 1u, 0x2001Fu, 0, &hKey, 0);
  v5 = lpSubKey;
  if ( v10 > 7 )
    v5 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x112,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v4,
    (unsigned int)"%ws",
    (const char *)v5);
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
}

```

## disassembly

```asm
0x18006e530  push    rbp
0x18006e532  lea     rbp, [rsp-57h]
0x18006e537  sub     rsp, 0A0h
0x18006e53e  mov     rax, cs:__security_cookie
0x18006e545  xor     rax, rsp
0x18006e548  mov     [rbp+57h+var_8], rax
0x18006e54c  movups  xmm0, xmmword ptr [r8]
0x18006e550  movdqu  [rbp+57h+var_50], xmm0
0x18006e555  movups  xmm1, xmmword ptr [rdx]
0x18006e558  movdqu  [rbp+57h+var_40], xmm1
0x18006e55d  lea     r9, [rbp+57h+var_50]
0x18006e561  lea     r8, [rbp+57h+var_40]
0x18006e565  lea     rdx, [rbp+57h+lpSubKey]
0x18006e569  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18006e56e  nop
0x18006e56f  mov     [rbp+57h+hKey], 0
0x18006e577  lea     rdx, [rbp+57h+lpSubKey]
0x18006e57b  cmp     [rbp+57h+var_10], 7
0x18006e580  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18006e585  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x18006e58e  lea     rax, [rbp+57h+hKey]
0x18006e592  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18006e597  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006e5a0  mov     [rsp+0A0h+samDesired], 2001Fh; samDesired
0x18006e5a8  mov     [rsp+0A0h+dwOptions], 1; dwOptions
0x18006e5b0  xor     r9d, r9d; lpClass
0x18006e5b3  xor     r8d, r8d; Reserved
0x18006e5b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e5bd  call    cs:__imp_RegCreateKeyExW
0x18006e5c3  lea     rdx, [rbp+57h+lpSubKey]
0x18006e5c7  cmp     [rbp+57h+var_10], 7
0x18006e5cc  cmova   rdx, [rbp+57h+lpSubKey]
0x18006e5d1  mov     rcx, [rbp+5Fh]; this
0x18006e5d5  mov     qword ptr [rsp+0A0h+samDesired], rdx; char *
0x18006e5da  lea     rdx, aWs_0; "%ws"
0x18006e5e1  mov     qword ptr [rsp+0A0h+dwOptions], rdx; unsigned int
0x18006e5e6  mov     r9d, eax; char *
0x18006e5e9  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006e5f0  mov     edx, 112h; void *
0x18006e5f5  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18006e5fa  nop
0x18006e5fb  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e5ff  test    rcx, rcx
0x18006e602  jz      short loc_18006E60B
0x18006e604  call    cs:__imp_RegCloseKey
0x18006e60a  nop
0x18006e60b  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18006e60f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006e614  mov     rcx, [rbp+57h+var_8]
0x18006e618  xor     rcx, rsp; StackCookie
0x18006e61b  call    __security_check_cookie
0x18006e620  add     rsp, 0A0h
0x18006e627  pop     rbp
0x18006e628  retn
```
