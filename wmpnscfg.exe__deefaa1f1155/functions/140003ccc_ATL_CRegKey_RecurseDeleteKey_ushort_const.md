# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x140003ccc`
- end: `0x140003e13`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003ccc`
- `0x140004190`

## callees

- `0x1400014f0`
- `0x1400031b0`
- `0x140003ccc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140003d4a`
- `ADVAPI32!RegCloseKey` at `0x140003dc2`
- `ADVAPI32!RegCloseKey` at `0x140003de4`
- `ADVAPI32!RegCloseKey` at `0x140003d4a`
- `ADVAPI32!RegCloseKey` at `0x140003dc2`
- `ADVAPI32!RegCloseKey` at `0x140003de4`
- `ADVAPI32!RegEnumKeyExW` at `0x140003dae`
- `ADVAPI32!RegEnumKeyExW` at `0x140003dae`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d2d`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d2d`

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
0x140003ccc  mov     [rsp-8+arg_10], rbx
0x140003cd1  mov     [rsp-8+arg_18], rsi
0x140003cd6  push    rbp
0x140003cd7  push    rdi
0x140003cd8  push    r14
0x140003cda  lea     rbp, [rsp-180h]
0x140003ce2  sub     rsp, 280h
0x140003ce9  mov     rax, cs:__security_cookie
0x140003cf0  xor     rax, rsp
0x140003cf3  mov     [rbp+190h+var_20], rax
0x140003cfa  xor     r14d, r14d
0x140003cfd  lea     rax, [rsp+290h+var_230]
0x140003d02  mov     rdi, rcx
0x140003d05  mov     [rsp+290h+hKey], r14
0x140003d0a  mov     rcx, [rcx]; hKey
0x140003d0d  mov     r9d, 2001Fh; samDesired
0x140003d13  xor     r8d, r8d; ulOptions
0x140003d16  mov     [rsp+290h+var_240], r14
0x140003d1b  mov     [rsp+290h+var_238], r14
0x140003d20  mov     rsi, rdx
0x140003d23  mov     [rsp+290h+var_230], r14
0x140003d28  mov     [rsp+290h+phkResult], rax; phkResult
0x140003d2d  call    cs:__imp_RegOpenKeyExW
0x140003d33  mov     rcx, [rsp+290h+hKey]; hKey
0x140003d38  mov     ebx, eax
0x140003d3a  test    eax, eax
0x140003d3c  jnz     loc_140003DDF
0x140003d42  mov     ebx, r14d
0x140003d45  test    rcx, rcx
0x140003d48  jz      short loc_140003D52
0x140003d4a  call    cs:__imp_RegCloseKey
0x140003d50  mov     ebx, eax
0x140003d52  mov     rcx, [rsp+290h+var_230]
0x140003d57  mov     [rsp+290h+hKey], rcx
0x140003d5c  test    ebx, ebx
0x140003d5e  jnz     short loc_140003DDF
0x140003d60  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x140003d65  jmp     short loc_140003D81
0x140003d67  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x140003d6c  lea     rcx, [rsp+290h+hKey]; this
0x140003d71  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140003d76  mov     rcx, [rsp+290h+hKey]; hKey
0x140003d7b  mov     ebx, eax
0x140003d7d  test    eax, eax
0x140003d7f  jnz     short loc_140003DDF
0x140003d81  lea     rax, [rsp+290h+ftLastWriteTime]
0x140003d86  mov     [rsp+290h+cchName], 100h
0x140003d8e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140003d93  lea     r9, [rsp+290h+cchName]; lpcchName
0x140003d98  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x140003d9d  lea     r8, [rsp+290h+Name]; lpName
0x140003da2  mov     [rsp+290h+lpClass], r14; lpClass
0x140003da7  xor     edx, edx; dwIndex
0x140003da9  mov     [rsp+290h+phkResult], r14; lpReserved
0x140003dae  call    cs:__imp_RegEnumKeyExW
0x140003db4  test    eax, eax
0x140003db6  jz      short loc_140003D67
0x140003db8  mov     rcx, [rsp+290h+hKey]; hKey
0x140003dbd  test    rcx, rcx
0x140003dc0  jz      short loc_140003DCD
0x140003dc2  call    cs:__imp_RegCloseKey
0x140003dc8  mov     [rsp+290h+hKey], r14
0x140003dcd  mov     rdx, rsi; unsigned __int16 *
0x140003dd0  mov     rcx, rdi; this
0x140003dd3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140003dd8  mov     rcx, [rsp+290h+hKey]; hKey
0x140003ddd  mov     ebx, eax
0x140003ddf  test    rcx, rcx
0x140003de2  jz      short loc_140003DEA
0x140003de4  call    cs:__imp_RegCloseKey
0x140003dea  mov     eax, ebx
0x140003dec  mov     rcx, [rbp+190h+var_20]
0x140003df3  xor     rcx, rsp; StackCookie
0x140003df6  call    __security_check_cookie
0x140003dfb  lea     r11, [rsp+290h+var_10]
0x140003e03  mov     rbx, [r11+30h]
0x140003e07  mov     rsi, [r11+38h]
0x140003e0b  mov     rsp, r11
0x140003e0e  pop     r14
0x140003e10  pop     rdi
0x140003e11  pop     rbp
0x140003e12  retn
```
