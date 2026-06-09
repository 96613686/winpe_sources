# DeleteKeyRecursivelyW

- ea: `0x180043be8`
- end: `0x180043d7a`
- name: `DeleteKeyRecursivelyW`
- size: `402`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180043be8`
- `0x180070830`
- `0x1800708b0`

## callees

- `0x180043be8`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043cde`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043cde`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180043d6e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180043d6e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180043d04`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180043d04`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180043c8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180043c8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043ced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043ced`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043c35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043c35`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043d3c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043d3c`

## pseudocode

```c
__int64 __fastcall DeleteKeyRecursivelyW(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  HKEY v5; // rcx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x3001Fu, &hKey);
  if ( !v4 )
  {
    cSubKeys = 0;
    cchName = 261;
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !v4 )
    {
      while ( 1 )
      {
        --cSubKeys;
        cchName = 261;
        if ( RegEnumKeyExW(hKey, cSubKeys, Name, &cchName, 0, 0, 0, 0) )
          break;
        DeleteKeyRecursivelyW(hKey, Name);
      }
    }
    RegCloseKey(hKey);
    v5 = a1;
    if ( a2 )
    {
      return (unsigned int)RegDeleteKeyExW(a1, a2, 0, 0);
    }
    else
    {
      while ( 1 )
      {
        cchName = 261;
        if ( RegEnumValueW(v5, 0, Name, &cchName, 0, 0, 0, 0) || RegDeleteValueW(a1, Name) )
          break;
        v5 = a1;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180043be8  mov     [rsp-8+arg_10], rbx
0x180043bed  push    rbp
0x180043bee  push    rsi
0x180043bef  push    rdi
0x180043bf0  push    r14
0x180043bf2  push    r15
0x180043bf4  lea     rbp, [rsp-190h]
0x180043bfc  sub     rsp, 290h
0x180043c03  mov     rax, cs:__security_cookie
0x180043c0a  xor     rax, rsp
0x180043c0d  mov     [rbp+1B0h+var_30], rax
0x180043c14  lea     rax, [rsp+2B0h+hKey]
0x180043c19  xor     r14d, r14d
0x180043c1c  mov     r9d, 3001Fh; samDesired
0x180043c22  mov     [rsp+2B0h+hKey], r14
0x180043c27  xor     r8d, r8d; ulOptions
0x180043c2a  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180043c2f  mov     rsi, rdx
0x180043c32  mov     rdi, rcx
0x180043c35  call    cs:__imp_RegOpenKeyExW
0x180043c3b  mov     ebx, eax
0x180043c3d  test    eax, eax
0x180043c3f  jnz     loc_180043D0C
0x180043c45  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180043c4a  lea     rax, [rsp+2B0h+cSubKeys]
0x180043c4f  mov     [rsp+2B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180043c54  mov     r15d, 105h
0x180043c5a  mov     [rsp+2B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180043c5f  xor     r9d, r9d; lpReserved
0x180043c62  mov     [rsp+2B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180043c67  xor     r8d, r8d; lpcchClass
0x180043c6a  mov     [rsp+2B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180043c6f  xor     edx, edx; lpClass
0x180043c71  mov     [rsp+2B0h+lpcValues], r14; lpcValues
0x180043c76  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180043c7b  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180043c80  mov     [rsp+2B0h+phkResult], rax; lpcSubKeys
0x180043c85  mov     [rsp+2B0h+cSubKeys], r14d
0x180043c8a  mov     [rsp+2B0h+cchName], r15d
0x180043c8f  call    cs:__imp_RegQueryInfoKeyW
0x180043c95  mov     ebx, eax
0x180043c97  test    eax, eax
0x180043c99  jnz     short loc_180043CE8
0x180043c9b  jmp     short loc_180043CAC
0x180043c9d  mov     rcx, [rsp+2B0h+hKey]
0x180043ca2  lea     rdx, [rsp+2B0h+Name]
0x180043ca7  call    DeleteKeyRecursivelyW
0x180043cac  mov     edx, [rsp+2B0h+cSubKeys]
0x180043cb0  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x180043cb5  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180043cba  lea     r8, [rsp+2B0h+Name]; lpName
0x180043cbf  mov     [rsp+2B0h+lpcValues], r14; lpftLastWriteTime
0x180043cc4  dec     edx; dwIndex
0x180043cc6  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpcchClass
0x180043ccb  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpClass
0x180043cd0  mov     [rsp+2B0h+cSubKeys], edx
0x180043cd4  mov     [rsp+2B0h+phkResult], r14; lpReserved
0x180043cd9  mov     [rsp+2B0h+cchName], r15d
0x180043cde  call    cs:__imp_RegEnumKeyExW
0x180043ce4  test    eax, eax
0x180043ce6  jz      short loc_180043C9D
0x180043ce8  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180043ced  call    cs:__imp_RegCloseKey
0x180043cf3  mov     rcx, rdi; hKey
0x180043cf6  test    rsi, rsi
0x180043cf9  jz      short loc_180043D49
0x180043cfb  xor     r9d, r9d; Reserved
0x180043cfe  xor     r8d, r8d; samDesired
0x180043d01  mov     rdx, rsi; lpSubKey
0x180043d04  call    cs:__imp_RegDeleteKeyExW
0x180043d0a  mov     ebx, eax
0x180043d0c  mov     eax, ebx
0x180043d0e  mov     rcx, [rbp+1B0h+var_30]
0x180043d15  xor     rcx, rsp; StackCookie
0x180043d18  call    __security_check_cookie
0x180043d1d  mov     rbx, [rsp+2B0h+arg_10]
0x180043d25  add     rsp, 290h
0x180043d2c  pop     r15
0x180043d2e  pop     r14
0x180043d30  pop     rdi
0x180043d31  pop     rsi
0x180043d32  pop     rbp
0x180043d33  retn
0x180043d34  lea     rdx, [rsp+2B0h+Name]; lpValueName
0x180043d39  mov     rcx, rdi; hKey
0x180043d3c  call    cs:__imp_RegDeleteValueW
0x180043d42  test    eax, eax
0x180043d44  jnz     short loc_180043D0C
0x180043d46  mov     rcx, rdi; hKey
0x180043d49  mov     [rsp+2B0h+lpcValues], r14; lpcbData
0x180043d4e  lea     r9, [rsp+2B0h+cchName]; lpcchValueName
0x180043d53  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpData
0x180043d58  lea     r8, [rsp+2B0h+Name]; lpValueName
0x180043d5d  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpType
0x180043d62  xor     edx, edx; dwIndex
0x180043d64  mov     [rsp+2B0h+phkResult], r14; lpReserved
0x180043d69  mov     [rsp+2B0h+cchName], r15d
0x180043d6e  call    cs:__imp_RegEnumValueW
0x180043d74  test    eax, eax
0x180043d76  jnz     short loc_180043D0C
0x180043d78  jmp     short loc_180043D34
```
