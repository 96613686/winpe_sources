# Windows::Registry::CopySystemKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180083ea0`
- end: `0x180084098`
- name: `?CopySystemKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@000@Z`
- size: `504`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180011680`
- `0x180083c20`
- `0x180083ea0`
- `0x1800855a0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084064`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084064`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083fd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083fd0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180083f67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180083f67`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180084010`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180084010`

## string_xrefs

- `0x18008402a`: `srcPath: %ws destPath: %ws`
- `0x180083f93`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180083ff5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180084039`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Registry::CopySystemKey(__int64 a1, __int128 *a2, const char **a3, __int128 *a4, _QWORD *a5)
{
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  LPCWSTR *v10; // rdx
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  LPCWSTR *v13; // rdx
  unsigned int v14; // eax
  __int128 v15; // [rsp+50h] [rbp-51h] BYREF
  __int128 v16; // [rsp+60h] [rbp-41h] BYREF
  HKEY hKeySrc; // [rsp+70h] [rbp-31h] BYREF
  HKEY hKeyDest; // [rsp+78h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp-21h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp-9h]
  LPCWSTR v21[3]; // [rsp+A0h] [rbp-1h] BYREF
  unsigned __int64 v22; // [rsp+B8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v15 = *(_OWORD *)a3;
  v16 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, (__int64)v21, (const char **)&v16, (__int64)&v15);
  v16 = *(_OWORD *)a5;
  v15 = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, (__int64)lpSubKey, (const char **)&v15, (__int64)&v16);
  hKeyDest = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v20 > 7 )
    v8 = lpSubKey[0];
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0xF003Fu, 0, &hKeyDest, 0);
  v10 = lpSubKey;
  if ( v20 > 7 )
    v10 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xEF,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v9,
    (unsigned int)"%ws",
    (const char *)v10);
  hKeySrc = 0;
  v11 = (const WCHAR *)v21;
  if ( v22 > 7 )
    v11 = v21[0];
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &hKeySrc);
  v13 = v21;
  if ( v22 > 7 )
    v13 = (LPCWSTR *)v21[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xF8,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v12,
    (unsigned int)"%ws",
    (const char *)v13);
  v14 = RegCopyTreeW(hKeySrc, 0, hKeyDest);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xFB,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v14,
    (unsigned int)"srcPath: %ws destPath: %ws",
    *a3,
    *a5);
  if ( hKeySrc )
    RegCloseKey(hKeySrc);
  if ( hKeyDest )
    RegCloseKey(hKeyDest);
  std::wstring::~wstring(lpSubKey);
  std::wstring::~wstring(v21);
}

```

## disassembly

```asm
0x180083ea0  push    rbp
0x180083ea2  push    rbx
0x180083ea3  push    rsi
0x180083ea4  push    rdi
0x180083ea5  push    r14
0x180083ea7  lea     rbp, [rsp-2Fh]
0x180083eac  sub     rsp, 0D0h
0x180083eb3  mov     rax, cs:__security_cookie
0x180083eba  xor     rax, rsp
0x180083ebd  mov     [rbp+4Fh+var_30], rax
0x180083ec1  mov     rbx, r9
0x180083ec4  mov     r14, r8
0x180083ec7  mov     rdi, rcx
0x180083eca  mov     rsi, [rbp+4Fh+arg_20]
0x180083ece  movups  xmm0, xmmword ptr [r8]
0x180083ed2  movdqu  [rbp+4Fh+var_A0], xmm0
0x180083ed7  movups  xmm1, xmmword ptr [rdx]
0x180083eda  movdqu  [rbp+4Fh+var_90], xmm1
0x180083edf  lea     r9, [rbp+4Fh+var_A0]
0x180083ee3  lea     r8, [rbp+4Fh+var_90]
0x180083ee7  lea     rdx, [rbp+4Fh+var_50]
0x180083eeb  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180083ef0  nop
0x180083ef1  movups  xmm0, xmmword ptr [rsi]
0x180083ef4  movdqu  [rbp+4Fh+var_90], xmm0
0x180083ef9  movups  xmm1, xmmword ptr [rbx]
0x180083efc  movdqu  [rbp+4Fh+var_A0], xmm1
0x180083f01  lea     r9, [rbp+4Fh+var_90]
0x180083f05  lea     r8, [rbp+4Fh+var_A0]
0x180083f09  lea     rdx, [rbp+4Fh+lpSubKey]
0x180083f0d  mov     rcx, rdi
0x180083f10  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180083f15  nop
0x180083f16  mov     [rbp+4Fh+hKeyDest], 0
0x180083f1e  lea     rdx, [rbp+4Fh+lpSubKey]
0x180083f22  cmp     [rbp+4Fh+var_58], 7
0x180083f27  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x180083f2c  mov     [rsp+0F0h+lpdwDisposition], 0; lpdwDisposition
0x180083f35  lea     rax, [rbp+4Fh+hKeyDest]
0x180083f39  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180083f3e  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180083f47  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x180083f4f  mov     [rsp+0F0h+dwOptions], 0; dwOptions
0x180083f57  xor     r9d, r9d; lpClass
0x180083f5a  xor     r8d, r8d; Reserved
0x180083f5d  mov     rbx, 0FFFFFFFF80000002h
0x180083f64  mov     rcx, rbx; hKey
0x180083f67  call    cs:__imp_RegCreateKeyExW
0x180083f6d  lea     rdx, [rbp+4Fh+lpSubKey]
0x180083f71  cmp     [rbp+4Fh+var_58], 7
0x180083f76  cmova   rdx, [rbp+4Fh+lpSubKey]
0x180083f7b  mov     rcx, [rbp+57h]; this
0x180083f7f  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x180083f84  lea     rdi, aWs_0; "%ws"
0x180083f8b  mov     qword ptr [rsp+0F0h+dwOptions], rdi; unsigned int
0x180083f90  mov     r9d, eax; char *
0x180083f93  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180083f9a  mov     edx, 0EFh; void *
0x180083f9f  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180083fa4  nop
0x180083fa5  mov     [rbp+4Fh+hKeySrc], 0
0x180083fad  lea     rdx, [rbp+4Fh+var_50]
0x180083fb1  cmp     [rbp+4Fh+var_38], 7
0x180083fb6  cmova   rdx, [rbp+4Fh+var_50]; lpSubKey
0x180083fbb  lea     rax, [rbp+4Fh+hKeySrc]
0x180083fbf  mov     qword ptr [rsp+0F0h+dwOptions], rax; phkResult
0x180083fc4  mov     r9d, 20019h; samDesired
0x180083fca  xor     r8d, r8d; ulOptions
0x180083fcd  mov     rcx, rbx; hKey
0x180083fd0  call    cs:__imp_RegOpenKeyExW
0x180083fd6  lea     rdx, [rbp+4Fh+var_50]
0x180083fda  cmp     [rbp+4Fh+var_38], 7
0x180083fdf  cmova   rdx, [rbp+4Fh+var_50]
0x180083fe4  mov     rcx, [rbp+57h]; this
0x180083fe8  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x180083fed  mov     qword ptr [rsp+0F0h+dwOptions], rdi; unsigned int
0x180083ff2  mov     r9d, eax; char *
0x180083ff5  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180083ffc  mov     edx, 0F8h; void *
0x180084001  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180084006  mov     r8, [rbp+4Fh+hKeyDest]; hKeyDest
0x18008400a  xor     edx, edx; lpSubKey
0x18008400c  mov     rcx, [rbp+4Fh+hKeySrc]; hKeySrc
0x180084010  call    cs:__imp_RegCopyTreeW
0x180084016  mov     rcx, [rbp+57h]; this
0x18008401a  mov     rdx, [rsi]
0x18008401d  mov     [rsp+0F0h+lpSecurityAttributes], rdx
0x180084022  mov     rdx, [r14]
0x180084025  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x18008402a  lea     rdx, aSrcpathWsDestp; "srcPath: %ws destPath: %ws"
0x180084031  mov     qword ptr [rsp+0F0h+dwOptions], rdx; unsigned int
0x180084036  mov     r9d, eax; char *
0x180084039  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180084040  mov     edx, 0FBh; void *
0x180084045  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18008404a  nop
0x18008404b  mov     rcx, [rbp+4Fh+hKeySrc]; hKey
0x18008404f  test    rcx, rcx
0x180084052  jz      short loc_18008405B
0x180084054  call    cs:__imp_RegCloseKey
0x18008405a  nop
0x18008405b  mov     rcx, [rbp+4Fh+hKeyDest]; hKey
0x18008405f  test    rcx, rcx
0x180084062  jz      short loc_18008406B
0x180084064  call    cs:__imp_RegCloseKey
0x18008406a  nop
0x18008406b  lea     rcx, [rbp+4Fh+lpSubKey]; void *
0x18008406f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084074  nop
0x180084075  lea     rcx, [rbp+4Fh+var_50]; void *
0x180084079  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008407e  mov     rcx, [rbp+4Fh+var_30]
0x180084082  xor     rcx, rsp; StackCookie
0x180084085  call    __security_check_cookie
0x18008408a  add     rsp, 0D0h
0x180084091  pop     r14
0x180084093  pop     rdi
0x180084094  pop     rsi
0x180084095  pop     rbx
0x180084096  pop     rbp
0x180084097  retn
```
