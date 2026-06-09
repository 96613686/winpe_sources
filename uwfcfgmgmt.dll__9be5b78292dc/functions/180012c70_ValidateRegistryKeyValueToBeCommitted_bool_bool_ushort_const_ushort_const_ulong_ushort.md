# ValidateRegistryKeyValueToBeCommitted(bool,bool,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180012c70`
- end: `0x180012def`
- name: `?ValidateRegistryKeyValueToBeCommitted@@YA?AW4REG_COMMIT_VALIDATE_RESULT@@_N0PEBG1KPEAPEAG@Z`
- size: `383`
- prototype: `__int64 __fastcall(char, char, wchar_t *, const WCHAR *, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800155f0`
- `0x180015870`

## callees

- `0x180012540`
- `0x180012930`
- `0x180012c70`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180012dab`
- `msvcrt!_wcsnicmp` at `0x180012dab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ce6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012d17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ce6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012d17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012cf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012cf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012d38`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012d38`

## pseudocode

```c
__int64 __fastcall ValidateRegistryKeyValueToBeCommitted(
        char a1,
        char a2,
        wchar_t *a3,
        const WCHAR *a4,
        unsigned int a5,
        unsigned __int16 **a6)
{
  unsigned int v9; // ebx
  HKEY v10; // rdi
  const WCHAR *v11; // rsi
  int v12; // r14d
  __int64 v13; // rax
  size_t v14; // r8
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-8h] BYREF

  hKey = 0;
  lpSubKey = 0;
  if ( !ParsePredefinedKey(a3, &lpSubKey, &hKey) )
    return 2;
  v10 = hKey;
  v11 = lpSubKey;
  if ( !a1 )
  {
    lpSubKey = 0;
    if ( RegOpenKeyExW(hKey, v11, 0, 0x20019u, (PHKEY)&lpSubKey) )
      return 1;
    RegCloseKey((HKEY)lpSubKey);
    if ( a2 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(v10, v11, 0, 0x20019u, &hKey) && !RegQueryValueExW(hKey, a4, 0, 0, 0, 0) )
      {
        RegCloseKey(hKey);
        goto LABEL_11;
      }
      return 1;
    }
LABEL_13:
    v12 = 0;
    while ( 1 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v11[v13] );
      v14 = v13 - 1;
      if ( v11[v13 - 1] != 92 )
        v14 = v13;
      if ( v10 == (HKEY)qword_18002A020[2 * v12] && !_wcsnicmp(v11, (const wchar_t *)qword_18002A020[2 * v12 + 1], v14) )
        return 3;
      if ( (unsigned int)++v12 >= 0xA )
        goto LABEL_21;
    }
  }
  if ( !a2 )
    goto LABEL_13;
LABEL_11:
  if ( v10 != HKEY_LOCAL_MACHINE )
    return 3;
LABEL_21:
  v9 = 0;
  if ( IsKeyInExclusionList(v10, v11, a5, a6) )
    return 4;
  return v9;
}

```

## disassembly

```asm
0x180012c70  push    rbp
0x180012c72  push    rbx
0x180012c73  push    rsi
0x180012c74  push    rdi
0x180012c75  push    r12
0x180012c77  push    r14
0x180012c79  push    r15
0x180012c7b  mov     rbp, rsp
0x180012c7e  sub     rsp, 40h
0x180012c82  mov     rax, r8
0x180012c85  mov     bl, dl
0x180012c87  mov     r14b, cl
0x180012c8a  lea     r8, [rbp+hKey]; HKEY *
0x180012c8e  xor     r12d, r12d
0x180012c91  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x180012c95  mov     rcx, rax; String2
0x180012c98  mov     [rbp+hKey], r12
0x180012c9c  mov     r15, r9
0x180012c9f  mov     [rbp+lpSubKey], r12
0x180012ca3  call    ?ParsePredefinedKey@@YA_NPEBGPEAPEBGPEAPEAUHKEY__@@@Z; ParsePredefinedKey(ushort const *,ushort const * *,HKEY__ * *)
0x180012ca8  test    al, al
0x180012caa  jnz     short loc_180012CB6
0x180012cac  lea     ebx, [r12+2]
0x180012cb1  jmp     loc_180012DDE
0x180012cb6  mov     rdi, [rbp+hKey]
0x180012cba  mov     rsi, [rbp+lpSubKey]
0x180012cbe  test    r14b, r14b
0x180012cc1  jnz     loc_180012D58
0x180012cc7  lea     rax, [rbp+lpSubKey]
0x180012ccb  mov     [rbp+lpSubKey], r12
0x180012ccf  mov     r14d, 20019h
0x180012cd5  mov     [rsp+40h+phkResult], rax; phkResult
0x180012cda  mov     r9d, r14d; samDesired
0x180012cdd  xor     r8d, r8d; ulOptions
0x180012ce0  mov     rdx, rsi; lpSubKey
0x180012ce3  mov     rcx, rdi; hKey
0x180012ce6  call    cs:__imp_RegOpenKeyExW
0x180012cec  test    eax, eax
0x180012cee  jnz     short loc_180012D4E
0x180012cf0  mov     rcx, [rbp+lpSubKey]; hKey
0x180012cf4  call    cs:__imp_RegCloseKey
0x180012cfa  test    bl, bl
0x180012cfc  jz      short loc_180012D6C
0x180012cfe  lea     rax, [rbp+hKey]
0x180012d02  mov     [rbp+hKey], r12
0x180012d06  mov     r9d, r14d; samDesired
0x180012d09  mov     [rsp+40h+phkResult], rax; phkResult
0x180012d0e  xor     r8d, r8d; ulOptions
0x180012d11  mov     rdx, rsi; lpSubKey
0x180012d14  mov     rcx, rdi; hKey
0x180012d17  call    cs:__imp_RegOpenKeyExW
0x180012d1d  test    eax, eax
0x180012d1f  jnz     short loc_180012D4E
0x180012d21  mov     rcx, [rbp+hKey]; hKey
0x180012d25  xor     r9d, r9d; lpType
0x180012d28  mov     [rsp+40h+lpcbData], r12; lpcbData
0x180012d2d  xor     r8d, r8d; lpReserved
0x180012d30  mov     rdx, r15; lpValueName
0x180012d33  mov     [rsp+40h+phkResult], r12; lpData
0x180012d38  call    cs:__imp_RegQueryValueExW
0x180012d3e  test    eax, eax
0x180012d40  jnz     short loc_180012D4E
0x180012d42  mov     rcx, [rbp+hKey]; hKey
0x180012d46  call    cs:__imp_RegCloseKey
0x180012d4c  jmp     short loc_180012D5C
0x180012d4e  mov     ebx, 1
0x180012d53  jmp     loc_180012DDE
0x180012d58  test    bl, bl
0x180012d5a  jz      short loc_180012D6C
0x180012d5c  cmp     rdi, 0FFFFFFFF80000002h
0x180012d63  jz      short loc_180012DBE
0x180012d65  mov     ebx, 3
0x180012d6a  jmp     short loc_180012DDE
0x180012d6c  mov     r14d, r12d
0x180012d6f  lea     r15, qword_18002A020
0x180012d76  mov     ebx, 1
0x180012d7b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012d7f  inc     rax
0x180012d82  cmp     [rsi+rax*2], r12w
0x180012d87  jnz     short loc_180012D7F
0x180012d89  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x180012d8f  lea     r8, [rax-1]
0x180012d93  movsxd  rdx, r14d
0x180012d96  cmovnz  r8, rax; MaxCount
0x180012d9a  add     rdx, rdx
0x180012d9d  cmp     rdi, [r15+rdx*8]
0x180012da1  jnz     short loc_180012DB5
0x180012da3  mov     rdx, [r15+rdx*8+8]; String2
0x180012da8  mov     rcx, rsi; String1
0x180012dab  call    cs:__imp__wcsnicmp
0x180012db1  test    eax, eax
0x180012db3  jz      short loc_180012D65
0x180012db5  add     r14d, ebx
0x180012db8  cmp     r14d, 0Ah
0x180012dbc  jb      short loc_180012D7B
0x180012dbe  mov     r9, [rbp+arg_28]; unsigned __int16 **
0x180012dc2  mov     rdx, rsi; unsigned __int16 *
0x180012dc5  mov     r8d, [rbp+arg_20]; unsigned int
0x180012dc9  mov     rcx, rdi; HKEY
0x180012dcc  mov     ebx, r12d
0x180012dcf  call    ?IsKeyInExclusionList@@YA_NPEAUHKEY__@@PEBGKPEAPEAG@Z; IsKeyInExclusionList(HKEY__ *,ushort const *,ulong,ushort * *)
0x180012dd4  test    al, al
0x180012dd6  mov     ecx, 4
0x180012ddb  cmovnz  ebx, ecx
0x180012dde  mov     eax, ebx
0x180012de0  add     rsp, 40h
0x180012de4  pop     r15
0x180012de6  pop     r14
0x180012de8  pop     r12
0x180012dea  pop     rdi
0x180012deb  pop     rsi
0x180012dec  pop     rbx
0x180012ded  pop     rbp
0x180012dee  retn
```
