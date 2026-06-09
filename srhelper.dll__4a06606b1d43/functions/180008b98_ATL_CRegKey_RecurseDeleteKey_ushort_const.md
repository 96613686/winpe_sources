# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180008b98`
- end: `0x180008cdf`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008b98`
- `0x18000902c`

## callees

- `0x180008308`
- `0x180008b98`
- `0x1800157f0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180008bf9`
- `ADVAPI32!RegOpenKeyExW` at `0x180008bf9`
- `ADVAPI32!RegEnumKeyExW` at `0x180008c7a`
- `ADVAPI32!RegEnumKeyExW` at `0x180008c7a`
- `ADVAPI32!RegCloseKey` at `0x180008c16`
- `ADVAPI32!RegCloseKey` at `0x180008c8e`
- `ADVAPI32!RegCloseKey` at `0x180008cb0`
- `ADVAPI32!RegCloseKey` at `0x180008c16`
- `ADVAPI32!RegCloseKey` at `0x180008c8e`
- `ADVAPI32!RegCloseKey` at `0x180008cb0`

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
0x180008b98  mov     [rsp-8+arg_10], rbx
0x180008b9d  mov     [rsp-8+arg_18], rsi
0x180008ba2  push    rbp
0x180008ba3  push    rdi
0x180008ba4  push    r14
0x180008ba6  lea     rbp, [rsp-180h]
0x180008bae  sub     rsp, 280h
0x180008bb5  mov     rax, cs:__security_cookie
0x180008bbc  xor     rax, rsp
0x180008bbf  mov     [rbp+190h+var_20], rax
0x180008bc6  xor     r14d, r14d
0x180008bc9  lea     rax, [rsp+290h+var_230]
0x180008bce  mov     rdi, rcx
0x180008bd1  mov     [rsp+290h+hKey], r14
0x180008bd6  mov     rcx, [rcx]; hKey
0x180008bd9  mov     r9d, 2001Fh; samDesired
0x180008bdf  xor     r8d, r8d; ulOptions
0x180008be2  mov     [rsp+290h+var_240], r14
0x180008be7  mov     [rsp+290h+var_238], r14
0x180008bec  mov     rsi, rdx
0x180008bef  mov     [rsp+290h+var_230], r14
0x180008bf4  mov     [rsp+290h+phkResult], rax; phkResult
0x180008bf9  call    cs:__imp_RegOpenKeyExW
0x180008bff  mov     rcx, [rsp+290h+hKey]; hKey
0x180008c04  mov     ebx, eax
0x180008c06  test    eax, eax
0x180008c08  jnz     loc_180008CAB
0x180008c0e  mov     ebx, r14d
0x180008c11  test    rcx, rcx
0x180008c14  jz      short loc_180008C1E
0x180008c16  call    cs:__imp_RegCloseKey
0x180008c1c  mov     ebx, eax
0x180008c1e  mov     rcx, [rsp+290h+var_230]
0x180008c23  mov     [rsp+290h+hKey], rcx
0x180008c28  test    ebx, ebx
0x180008c2a  jnz     short loc_180008CAB
0x180008c2c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180008c31  jmp     short loc_180008C4D
0x180008c33  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180008c38  lea     rcx, [rsp+290h+hKey]; this
0x180008c3d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008c42  mov     rcx, [rsp+290h+hKey]; hKey
0x180008c47  mov     ebx, eax
0x180008c49  test    eax, eax
0x180008c4b  jnz     short loc_180008CAB
0x180008c4d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180008c52  mov     [rsp+290h+cchName], 100h
0x180008c5a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180008c5f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180008c64  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180008c69  lea     r8, [rsp+290h+Name]; lpName
0x180008c6e  mov     [rsp+290h+lpClass], r14; lpClass
0x180008c73  xor     edx, edx; dwIndex
0x180008c75  mov     [rsp+290h+phkResult], r14; lpReserved
0x180008c7a  call    cs:__imp_RegEnumKeyExW
0x180008c80  test    eax, eax
0x180008c82  jz      short loc_180008C33
0x180008c84  mov     rcx, [rsp+290h+hKey]; hKey
0x180008c89  test    rcx, rcx
0x180008c8c  jz      short loc_180008C99
0x180008c8e  call    cs:__imp_RegCloseKey
0x180008c94  mov     [rsp+290h+hKey], r14
0x180008c99  mov     rdx, rsi; unsigned __int16 *
0x180008c9c  mov     rcx, rdi; this
0x180008c9f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008ca4  mov     rcx, [rsp+290h+hKey]; hKey
0x180008ca9  mov     ebx, eax
0x180008cab  test    rcx, rcx
0x180008cae  jz      short loc_180008CB6
0x180008cb0  call    cs:__imp_RegCloseKey
0x180008cb6  mov     eax, ebx
0x180008cb8  mov     rcx, [rbp+190h+var_20]
0x180008cbf  xor     rcx, rsp; StackCookie
0x180008cc2  call    __security_check_cookie
0x180008cc7  lea     r11, [rsp+290h+var_10]
0x180008ccf  mov     rbx, [r11+30h]
0x180008cd3  mov     rsi, [r11+38h]
0x180008cd7  mov     rsp, r11
0x180008cda  pop     r14
0x180008cdc  pop     rdi
0x180008cdd  pop     rbp
0x180008cde  retn
```
