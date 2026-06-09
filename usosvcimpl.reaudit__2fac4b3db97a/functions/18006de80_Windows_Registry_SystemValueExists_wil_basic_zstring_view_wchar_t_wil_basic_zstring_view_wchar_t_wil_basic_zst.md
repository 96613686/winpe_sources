# Windows::Registry::SystemValueExists(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18006de80`
- end: `0x18006dff4`
- name: `?SystemValueExists@Registry@Windows@@UEAA_NV?$basic_zstring_view@_W@wil@@00@Z`
- size: `372`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18008d420`
- `0x18009b920`
- `0x18009bbc4`
- `0x1800bef80`
- `0x1800bf2c4`

## callees

- `0x180011680`
- `0x18006de80`
- `0x180083c20`
- `0x1800855a0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006df12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dfbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006df12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006dfbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006defb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006defb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006df71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006df71`

## string_xrefs

- `0x18006df47`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18006dfa1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Registry::SystemValueExists(__int64 a1, __int128 *a2, __int128 *a3, __int128 *a4)
{
  __int128 v4; // xmm6
  char v5; // bl
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  const char *v8; // r9
  LPCWSTR *v9; // rax
  unsigned int Value; // eax
  const char *v11; // r9
  LPCWSTR *v12; // rax
  __int128 v14; // [rsp+48h] [rbp-19h] BYREF
  __int128 v15; // [rsp+58h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+7h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+70h] [rbp+Fh] BYREF
  unsigned __int64 v18; // [rsp+88h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v4 = *a4;
  v14 = *a3;
  v15 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v15, &v14);
  v5 = 0;
  hKey = 0;
  v6 = (const WCHAR *)lpSubKey;
  if ( v18 > 7 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  v8 = (const char *)v7;
  if ( v7 == 2 )
    goto LABEL_4;
  v9 = lpSubKey;
  if ( v18 > 7 )
    v9 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xA3,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    v8,
    (unsigned int)"%ws[%ws]",
    (const char *)v9,
    (_QWORD)v4);
  Value = RegQueryValueExW(hKey, (LPCWSTR)v4, 0, 0, 0, 0);
  v11 = (const char *)Value;
  if ( Value == 2 )
  {
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v12 = lpSubKey;
    if ( v18 > 7 )
      v12 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xB0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      v11,
      (unsigned int)"%ws[%ws]",
      (const char *)v12,
      (_QWORD)v4);
    if ( hKey )
      RegCloseKey(hKey);
    v5 = 1;
  }
  std::wstring::~wstring(lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x18006de80  mov     rax, rsp
0x18006de83  mov     [rax+8], rbx
0x18006de87  push    rbp
0x18006de88  push    rsi
0x18006de89  push    rdi
0x18006de8a  lea     rbp, [rax-5Fh]
0x18006de8e  sub     rsp, 0A0h
0x18006de95  movaps  xmmword ptr [rax-28h], xmm6
0x18006de99  mov     rax, cs:__security_cookie
0x18006dea0  xor     rax, rsp
0x18006dea3  mov     [rbp+57h+var_28], rax
0x18006dea7  movups  xmm6, xmmword ptr [r9]
0x18006deab  movups  xmm0, xmmword ptr [r8]
0x18006deaf  movdqu  [rbp+57h+var_70], xmm0
0x18006deb4  movups  xmm1, xmmword ptr [rdx]
0x18006deb7  movdqu  [rbp+57h+var_60], xmm1
0x18006debc  lea     r9, [rbp+57h+var_70]
0x18006dec0  lea     r8, [rbp+57h+var_60]
0x18006dec4  lea     rdx, [rbp+57h+lpSubKey]
0x18006dec8  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18006decd  nop
0x18006dece  xor     ebx, ebx
0x18006ded0  mov     [rbp+57h+hKey], rbx
0x18006ded4  lea     rdx, [rbp+57h+lpSubKey]
0x18006ded8  cmp     [rbp+57h+var_30], 7
0x18006dedd  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18006dee2  lea     rax, [rbp+57h+hKey]
0x18006dee6  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18006deeb  mov     r9d, 20019h; samDesired
0x18006def1  xor     r8d, r8d; ulOptions
0x18006def4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006defb  call    cs:__imp_RegOpenKeyExW
0x18006df01  mov     r9d, eax; char *
0x18006df04  cmp     eax, 2
0x18006df07  jnz     short loc_18006DF1E
0x18006df09  mov     rcx, [rbp+57h+hKey]; hKey
0x18006df0d  test    rcx, rcx
0x18006df10  jz      short loc_18006DF19
0x18006df12  call    cs:__imp_RegCloseKey
0x18006df18  nop
0x18006df19  jmp     loc_18006DFC5
0x18006df1e  lea     rax, [rbp+57h+lpSubKey]
0x18006df22  cmp     [rbp+57h+var_30], 7
0x18006df27  cmova   rax, [rbp+57h+lpSubKey]
0x18006df2c  mov     rcx, [rbp+5Fh]; this
0x18006df30  movq    [rsp+0B0h+var_80], xmm6
0x18006df36  mov     [rsp+0B0h+lpcbData], rax; char *
0x18006df3b  lea     rsi, aWsWs; "%ws[%ws]"
0x18006df42  mov     [rsp+0B0h+phkResult], rsi; unsigned int
0x18006df47  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006df4e  mov     edx, 0A3h; void *
0x18006df53  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18006df58  mov     [rsp+0B0h+lpcbData], rbx; lpcbData
0x18006df5d  mov     [rsp+0B0h+phkResult], rbx; lpData
0x18006df62  xor     r9d, r9d; lpType
0x18006df65  xor     r8d, r8d; lpReserved
0x18006df68  movq    rdx, xmm6; lpValueName
0x18006df6d  mov     rcx, [rbp+57h+hKey]; hKey
0x18006df71  call    cs:__imp_RegQueryValueExW
0x18006df77  mov     r9d, eax; char *
0x18006df7a  cmp     eax, 2
0x18006df7d  jz      short loc_18006DF09
0x18006df7f  lea     rax, [rbp+57h+lpSubKey]
0x18006df83  cmp     [rbp+57h+var_30], 7
0x18006df88  cmova   rax, [rbp+57h+lpSubKey]
0x18006df8d  mov     rcx, [rbp+5Fh]; this
0x18006df91  movq    [rsp+0B0h+var_80], xmm6
0x18006df97  mov     [rsp+0B0h+lpcbData], rax; char *
0x18006df9c  mov     [rsp+0B0h+phkResult], rsi; unsigned int
0x18006dfa1  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006dfa8  mov     edx, 0B0h; void *
0x18006dfad  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18006dfb2  nop
0x18006dfb3  mov     rcx, [rbp+57h+hKey]; hKey
0x18006dfb7  test    rcx, rcx
0x18006dfba  jz      short loc_18006DFC3
0x18006dfbc  call    cs:__imp_RegCloseKey
0x18006dfc2  nop
0x18006dfc3  mov     bl, 1
0x18006dfc5  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18006dfc9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006dfce  mov     al, bl
0x18006dfd0  mov     rcx, [rbp+57h+var_28]
0x18006dfd4  xor     rcx, rsp; StackCookie
0x18006dfd7  call    __security_check_cookie
0x18006dfdc  lea     r11, [rsp+0B0h+var_10]
0x18006dfe4  mov     rbx, [r11+20h]
0x18006dfe8  movaps  xmm6, xmmword ptr [r11-10h]
0x18006dfed  mov     rsp, r11
0x18006dff0  pop     rdi
0x18006dff1  pop     rsi
0x18006dff2  pop     rbp
0x18006dff3  retn
```
