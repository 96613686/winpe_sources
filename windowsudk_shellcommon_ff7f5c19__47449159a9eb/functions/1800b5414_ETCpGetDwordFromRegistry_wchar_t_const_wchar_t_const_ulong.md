# ETCpGetDwordFromRegistry(wchar_t const *,wchar_t const *,ulong &)

- ea: `0x1800b5414`
- end: `0x1800b551d`
- name: `?ETCpGetDwordFromRegistry@@YAJPEB_W0AEAK@Z`
- size: `265`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1801098e4`
- `0x1801099a4`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x1800b5414`
- `0x1800e34bc`
- `0x1800e3660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5456`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5456`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b5491`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b5491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5505`

## string_xrefs

- `0x1800b54ba`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x1800b54e7`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`

## pseudocode

```c
__int64 __fastcall ETCpGetDwordFromRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData)
{
  HKEY *v6; // rax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  hKey[0] = 0;
  v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, v6);
  Type = 4;
  v8 = v7;
  cbData = 4;
  if ( !v7 )
  {
    v8 = RegQueryValueExW(hKey[0], lpValueName, 0, &Type, lpData, &cbData);
    if ( !v8 )
    {
      if ( Type == 4 )
      {
        if ( cbData == 4 )
        {
          v8 = 0;
          goto LABEL_9;
        }
        v9 = 102;
      }
      else
      {
        v9 = 98;
      }
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
             (const char *)0xD,
             phkResult);
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
      return v8;
    }
  }
  if ( (v8 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
      (const char *)v8,
      phkResult);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v8;
}

```

## disassembly

```asm
0x1800b5414  mov     rax, rsp
0x1800b5417  mov     [rax+8], rbx
0x1800b541b  mov     [rax+10h], rsi
0x1800b541f  push    rdi
0x1800b5420  sub     rsp, 40h
0x1800b5424  mov     rbx, rcx
0x1800b5427  mov     qword ptr [rax-10h], 0
0x1800b542f  lea     rcx, [rax-10h]
0x1800b5433  mov     rdi, r8
0x1800b5436  mov     rsi, rdx
0x1800b5439  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800b543e  mov     r9d, 1; samDesired
0x1800b5444  mov     [rsp+48h+phkResult], rax; int
0x1800b5449  xor     r8d, r8d; ulOptions
0x1800b544c  mov     rdx, rbx; lpSubKey
0x1800b544f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b5456  call    cs:__imp_RegOpenKeyExW
0x1800b545c  mov     [rsp+48h+Type], 4
0x1800b5464  mov     ebx, eax
0x1800b5466  mov     [rsp+48h+cbData], 4
0x1800b546e  test    eax, eax
0x1800b5470  jnz     short loc_1800B54DE
0x1800b5472  mov     rcx, [rsp+48h+hKey]; hKey
0x1800b5477  lea     rax, [rsp+48h+cbData]
0x1800b547c  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800b5481  lea     r9, [rsp+48h+Type]; lpType
0x1800b5486  xor     r8d, r8d; lpReserved
0x1800b5489  mov     [rsp+48h+phkResult], rdi; unsigned int
0x1800b548e  mov     rdx, rsi; lpValueName
0x1800b5491  call    cs:__imp_RegQueryValueExW
0x1800b5497  mov     ebx, eax
0x1800b5499  test    eax, eax
0x1800b549b  jnz     short loc_1800B54DE
0x1800b549d  cmp     [rsp+48h+Type], 4
0x1800b54a2  jz      short loc_1800B54A9
0x1800b54a4  lea     edx, [rax+62h]
0x1800b54a7  jmp     short loc_1800B54B5
0x1800b54a9  cmp     [rsp+48h+cbData], 4
0x1800b54ae  jz      short loc_1800B54D0
0x1800b54b0  mov     edx, 66h ; 'f'; void *
0x1800b54b5  mov     rcx, [rsp+48h]; this
0x1800b54ba  lea     r8, aOnecoreInterna_19; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800b54c1  mov     r9d, 0Dh; char *
0x1800b54c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b54cc  mov     ebx, eax
0x1800b54ce  jmp     short loc_1800B54D2
0x1800b54d0  xor     ebx, ebx
0x1800b54d2  lea     rcx, [rsp+48h+hKey]
0x1800b54d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b54dc  jmp     short loc_1800B550B
0x1800b54de  test    ebx, ebx
0x1800b54e0  jns     short loc_1800B54FB
0x1800b54e2  mov     rcx, [rsp+48h]; this
0x1800b54e7  lea     r8, aOnecoreInterna_19; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800b54ee  mov     r9d, ebx; char *
0x1800b54f1  mov     edx, 6Bh ; 'k'; void *
0x1800b54f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b54fb  mov     rcx, [rsp+48h+hKey]; hKey
0x1800b5500  test    rcx, rcx
0x1800b5503  jz      short loc_1800B550B
0x1800b5505  call    cs:__imp_RegCloseKey
0x1800b550b  mov     rsi, [rsp+48h+arg_8]
0x1800b5510  mov     eax, ebx
0x1800b5512  mov     rbx, [rsp+48h+arg_0]
0x1800b5517  add     rsp, 40h
0x1800b551b  pop     rdi
0x1800b551c  retn
```
