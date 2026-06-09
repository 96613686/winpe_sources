# ETCpGetDwordFromRegistry(ushort const *,ushort const *,ulong &)

- ea: `0x180031980`
- end: `0x180031a95`
- name: `?ETCpGetDwordFromRegistry@@YAJPEBG0AEAK@Z`
- size: `277`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180031a9c`
- `0x1800359e4`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x180031980`
- `0x180037440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800319c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800319c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800319fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800319fd`

## string_xrefs

- `0x180031a16`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x180031a54`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`

## pseudocode

```c
__int64 __fastcall ETCpGetDwordFromRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *a3)
{
  LSTATUS v5; // eax
  LSTATUS v6; // ebx
  __int64 v7; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  Type = 4;
  v6 = v5;
  cbData = 4;
  if ( v5 || (v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a3, &cbData)) != 0 )
  {
    if ( v6 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
        (const char *)(unsigned int)v6,
        phkResult);
    goto LABEL_13;
  }
  if ( Type != 4 )
  {
    v7 = 98;
LABEL_5:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
           (const char *)0xD,
           phkResult);
LABEL_13:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  if ( cbData != 4 )
  {
    v7 = 102;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180031980  mov     [rsp-18h+arg_18], rbx
0x180031985  push    rbp
0x180031986  push    rsi
0x180031987  push    rdi
0x180031988  mov     rbp, rsp
0x18003198b  sub     rsp, 50h
0x18003198f  mov     rax, cs:__security_cookie
0x180031996  xor     rax, rsp
0x180031999  mov     [rbp+var_10], rax
0x18003199d  mov     rdi, rdx
0x1800319a0  mov     [rbp+hKey], 0
0x1800319a8  mov     rdx, rcx; lpSubKey
0x1800319ab  lea     rax, [rbp+hKey]
0x1800319af  mov     rsi, r8
0x1800319b2  mov     [rsp+50h+phkResult], rax; int
0x1800319b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800319be  mov     r9d, 1; samDesired
0x1800319c4  xor     r8d, r8d; ulOptions
0x1800319c7  call    cs:__imp_RegOpenKeyExW
0x1800319cd  mov     [rbp+Type], 4
0x1800319d4  mov     ebx, eax
0x1800319d6  mov     [rbp+cbData], 4
0x1800319dd  test    eax, eax
0x1800319df  jnz     short loc_180031A4C
0x1800319e1  mov     rcx, [rbp+hKey]; hKey
0x1800319e5  lea     rax, [rbp+cbData]
0x1800319e9  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800319ee  lea     r9, [rbp+Type]; lpType
0x1800319f2  xor     r8d, r8d; lpReserved
0x1800319f5  mov     [rsp+50h+phkResult], rsi; unsigned int
0x1800319fa  mov     rdx, rdi; lpValueName
0x1800319fd  call    cs:__imp_RegQueryValueExW
0x180031a03  mov     ebx, eax
0x180031a05  test    eax, eax
0x180031a07  jnz     short loc_180031A4C
0x180031a09  cmp     [rbp+Type], 4
0x180031a0d  jz      short loc_180031A2C
0x180031a0f  lea     edx, [rax+62h]; void *
0x180031a12  mov     rcx, [rbp+18h]; this
0x180031a16  lea     r8, aOnecoreInterna_7; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180031a1d  mov     r9d, 0Dh; char *
0x180031a23  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031a28  mov     ebx, eax
0x180031a2a  jmp     short loc_180031A68
0x180031a2c  cmp     [rbp+cbData], 4
0x180031a30  jz      short loc_180031A39
0x180031a32  mov     edx, 66h ; 'f'
0x180031a37  jmp     short loc_180031A12
0x180031a39  mov     rcx, [rbp+hKey]; hKey
0x180031a3d  test    rcx, rcx
0x180031a40  jz      short loc_180031A48
0x180031a42  call    cs:__imp_RegCloseKey
0x180031a48  xor     eax, eax
0x180031a4a  jmp     short loc_180031A79
0x180031a4c  test    ebx, ebx
0x180031a4e  jns     short loc_180031A68
0x180031a50  mov     rcx, [rbp+18h]; this
0x180031a54  lea     r8, aOnecoreInterna_7; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180031a5b  mov     r9d, ebx; char *
0x180031a5e  mov     edx, 6Bh ; 'k'; void *
0x180031a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031a68  mov     rcx, [rbp+hKey]; hKey
0x180031a6c  test    rcx, rcx
0x180031a6f  jz      short loc_180031A77
0x180031a71  call    cs:__imp_RegCloseKey
0x180031a77  mov     eax, ebx
0x180031a79  mov     rcx, [rbp+var_10]
0x180031a7d  xor     rcx, rsp; StackCookie
0x180031a80  call    __security_check_cookie
0x180031a85  mov     rbx, [rsp+50h+arg_18]
0x180031a8d  add     rsp, 50h
0x180031a91  pop     rdi
0x180031a92  pop     rsi
0x180031a93  pop     rbp
0x180031a94  retn
```
