# Windows::Registry::SystemKeyExists(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18006e000`
- end: `0x18006e0fd`
- name: `?SystemKeyExists@Registry@Windows@@UEAA_NV?$basic_zstring_view@_W@wil@@0@Z`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18008b5c0`
- `0x18009c2e0`

## callees

- `0x180011680`
- `0x18006e000`
- `0x180083c20`
- `0x1800855a0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e0cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e0cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e06e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e06e`

## string_xrefs

- `0x18006e0b1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Registry::SystemKeyExists(__int64 a1, __int128 *a2, __int128 *a3)
{
  char v3; // bl
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  const char *v6; // r9
  LPCWSTR *v7; // rax
  __int128 v9; // [rsp+30h] [rbp-50h] BYREF
  __int128 v10; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v13; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v9 = *a3;
  v10 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, (__int64)lpSubKey, (const char **)&v10, (__int64)&v9);
  v3 = 0;
  hKey = 0;
  v4 = (const WCHAR *)lpSubKey;
  if ( v13 > 7 )
    v4 = lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = (const char *)v5;
  if ( v5 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v7 = lpSubKey;
    if ( v13 > 7 )
      v7 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xC7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      v6,
      (unsigned int)"%ws",
      (const char *)v7);
    if ( hKey )
      RegCloseKey(hKey);
    v3 = 1;
  }
  std::wstring::~wstring(lpSubKey);
  return v3;
}

```

## disassembly

```asm
0x18006e000  mov     [rsp-8+arg_0], rbx
0x18006e005  push    rbp
0x18006e006  mov     rbp, rsp
0x18006e009  sub     rsp, 80h
0x18006e010  mov     rax, cs:__security_cookie
0x18006e017  xor     rax, rsp
0x18006e01a  mov     [rbp+var_8], rax
0x18006e01e  movups  xmm0, xmmword ptr [r8]
0x18006e022  movdqu  [rbp+var_50], xmm0
0x18006e027  movups  xmm1, xmmword ptr [rdx]
0x18006e02a  movdqu  [rbp+var_40], xmm1
0x18006e02f  lea     r9, [rbp+var_50]
0x18006e033  lea     r8, [rbp+var_40]
0x18006e037  lea     rdx, [rbp+lpSubKey]
0x18006e03b  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18006e040  nop
0x18006e041  xor     ebx, ebx
0x18006e043  mov     [rbp+hKey], rbx
0x18006e047  lea     rdx, [rbp+lpSubKey]
0x18006e04b  cmp     [rbp+var_10], 7
0x18006e050  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x18006e055  lea     rax, [rbp+hKey]
0x18006e059  mov     [rsp+80h+phkResult], rax; phkResult
0x18006e05e  mov     r9d, 20019h; samDesired
0x18006e064  xor     r8d, r8d; ulOptions
0x18006e067  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e06e  call    cs:__imp_RegOpenKeyExW
0x18006e074  mov     r9d, eax; char *
0x18006e077  cmp     eax, 2
0x18006e07a  jnz     short loc_18006E08E
0x18006e07c  mov     rcx, [rbp+hKey]; hKey
0x18006e080  test    rcx, rcx
0x18006e083  jz      short loc_18006E08C
0x18006e085  call    cs:__imp_RegCloseKey
0x18006e08b  nop
0x18006e08c  jmp     short loc_18006E0D5
0x18006e08e  lea     rax, [rbp+lpSubKey]
0x18006e092  cmp     [rbp+var_10], 7
0x18006e097  cmova   rax, [rbp+lpSubKey]
0x18006e09c  mov     rcx, [rbp+8]; this
0x18006e0a0  mov     [rsp+80h+var_58], rax; char *
0x18006e0a5  lea     rax, aWs_0; "%ws"
0x18006e0ac  mov     [rsp+80h+phkResult], rax; unsigned int
0x18006e0b1  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006e0b8  mov     edx, 0C7h; void *
0x18006e0bd  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18006e0c2  nop
0x18006e0c3  mov     rcx, [rbp+hKey]; hKey
0x18006e0c7  test    rcx, rcx
0x18006e0ca  jz      short loc_18006E0D3
0x18006e0cc  call    cs:__imp_RegCloseKey
0x18006e0d2  nop
0x18006e0d3  mov     bl, 1
0x18006e0d5  lea     rcx, [rbp+lpSubKey]; void *
0x18006e0d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006e0de  mov     al, bl
0x18006e0e0  mov     rcx, [rbp+var_8]
0x18006e0e4  xor     rcx, rsp; StackCookie
0x18006e0e7  call    __security_check_cookie
0x18006e0ec  mov     rbx, [rsp+80h+arg_0]
0x18006e0f4  add     rsp, 80h
0x18006e0fb  pop     rbp
0x18006e0fc  retn
```
