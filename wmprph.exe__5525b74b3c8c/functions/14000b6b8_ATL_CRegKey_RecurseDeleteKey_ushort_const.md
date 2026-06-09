# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x14000b6b8`
- end: `0x14000b7ff`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000b6b8`
- `0x14000bbf0`

## callees

- `0x140001390`
- `0x14000af48`
- `0x14000b6b8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000b719`
- `ADVAPI32!RegOpenKeyExW` at `0x14000b719`
- `ADVAPI32!RegEnumKeyExW` at `0x14000b79a`
- `ADVAPI32!RegEnumKeyExW` at `0x14000b79a`
- `ADVAPI32!RegCloseKey` at `0x14000b736`
- `ADVAPI32!RegCloseKey` at `0x14000b7ae`
- `ADVAPI32!RegCloseKey` at `0x14000b7d0`
- `ADVAPI32!RegCloseKey` at `0x14000b736`
- `ADVAPI32!RegCloseKey` at `0x14000b7ae`
- `ADVAPI32!RegCloseKey` at `0x14000b7d0`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x14000b6b8  mov     [rsp-8+arg_10], rbx
0x14000b6bd  mov     [rsp-8+arg_18], rsi
0x14000b6c2  push    rbp
0x14000b6c3  push    rdi
0x14000b6c4  push    r14
0x14000b6c6  lea     rbp, [rsp-180h]
0x14000b6ce  sub     rsp, 280h
0x14000b6d5  mov     rax, cs:__security_cookie
0x14000b6dc  xor     rax, rsp
0x14000b6df  mov     [rbp+190h+var_20], rax
0x14000b6e6  xor     r14d, r14d
0x14000b6e9  lea     rax, [rsp+290h+var_230]
0x14000b6ee  mov     rdi, rcx
0x14000b6f1  mov     [rsp+290h+hKey], r14
0x14000b6f6  mov     rcx, [rcx]; hKey
0x14000b6f9  mov     r9d, 2001Fh; samDesired
0x14000b6ff  xor     r8d, r8d; ulOptions
0x14000b702  mov     [rsp+290h+var_240], r14
0x14000b707  mov     [rsp+290h+var_238], r14
0x14000b70c  mov     rsi, rdx
0x14000b70f  mov     [rsp+290h+var_230], r14
0x14000b714  mov     [rsp+290h+phkResult], rax; phkResult
0x14000b719  call    cs:__imp_RegOpenKeyExW
0x14000b71f  mov     rcx, [rsp+290h+hKey]; hKey
0x14000b724  mov     ebx, eax
0x14000b726  test    eax, eax
0x14000b728  jnz     loc_14000B7CB
0x14000b72e  mov     ebx, r14d
0x14000b731  test    rcx, rcx
0x14000b734  jz      short loc_14000B73E
0x14000b736  call    cs:__imp_RegCloseKey
0x14000b73c  mov     ebx, eax
0x14000b73e  mov     rcx, [rsp+290h+var_230]
0x14000b743  mov     [rsp+290h+hKey], rcx
0x14000b748  test    ebx, ebx
0x14000b74a  jnz     short loc_14000B7CB
0x14000b74c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x14000b751  jmp     short loc_14000B76D
0x14000b753  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x14000b758  lea     rcx, [rsp+290h+hKey]; this
0x14000b75d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x14000b762  mov     rcx, [rsp+290h+hKey]; hKey
0x14000b767  mov     ebx, eax
0x14000b769  test    eax, eax
0x14000b76b  jnz     short loc_14000B7CB
0x14000b76d  lea     rax, [rsp+290h+ftLastWriteTime]
0x14000b772  mov     [rsp+290h+cchName], 100h
0x14000b77a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14000b77f  lea     r9, [rsp+290h+cchName]; lpcchName
0x14000b784  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x14000b789  lea     r8, [rsp+290h+Name]; lpName
0x14000b78e  mov     [rsp+290h+lpClass], r14; lpClass
0x14000b793  xor     edx, edx; dwIndex
0x14000b795  mov     [rsp+290h+phkResult], r14; lpReserved
0x14000b79a  call    cs:__imp_RegEnumKeyExW
0x14000b7a0  test    eax, eax
0x14000b7a2  jz      short loc_14000B753
0x14000b7a4  mov     rcx, [rsp+290h+hKey]; hKey
0x14000b7a9  test    rcx, rcx
0x14000b7ac  jz      short loc_14000B7B9
0x14000b7ae  call    cs:__imp_RegCloseKey
0x14000b7b4  mov     [rsp+290h+hKey], r14
0x14000b7b9  mov     rdx, rsi; unsigned __int16 *
0x14000b7bc  mov     rcx, rdi; this
0x14000b7bf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000b7c4  mov     rcx, [rsp+290h+hKey]; hKey
0x14000b7c9  mov     ebx, eax
0x14000b7cb  test    rcx, rcx
0x14000b7ce  jz      short loc_14000B7D6
0x14000b7d0  call    cs:__imp_RegCloseKey
0x14000b7d6  mov     eax, ebx
0x14000b7d8  mov     rcx, [rbp+190h+var_20]
0x14000b7df  xor     rcx, rsp; StackCookie
0x14000b7e2  call    __security_check_cookie
0x14000b7e7  lea     r11, [rsp+290h+var_10]
0x14000b7ef  mov     rbx, [r11+30h]
0x14000b7f3  mov     rsi, [r11+38h]
0x14000b7f7  mov     rsp, r11
0x14000b7fa  pop     r14
0x14000b7fc  pop     rdi
0x14000b7fd  pop     rbp
0x14000b7fe  retn
```
