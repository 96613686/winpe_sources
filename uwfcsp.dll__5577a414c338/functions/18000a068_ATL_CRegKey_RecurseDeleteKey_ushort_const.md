# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000a068`
- end: `0x18000a1af`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a068`
- `0x18000a50c`

## callees

- `0x1800090fc`
- `0x18000a068`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a0e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a15e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a0e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a15e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a180`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a14a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a14a`

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
0x18000a068  mov     [rsp-8+arg_10], rbx
0x18000a06d  mov     [rsp-8+arg_18], rsi
0x18000a072  push    rbp
0x18000a073  push    rdi
0x18000a074  push    r14
0x18000a076  lea     rbp, [rsp-180h]
0x18000a07e  sub     rsp, 280h
0x18000a085  mov     rax, cs:__security_cookie
0x18000a08c  xor     rax, rsp
0x18000a08f  mov     [rbp+190h+var_20], rax
0x18000a096  xor     r14d, r14d
0x18000a099  lea     rax, [rsp+290h+var_230]
0x18000a09e  mov     rdi, rcx
0x18000a0a1  mov     [rsp+290h+hKey], r14
0x18000a0a6  mov     rcx, [rcx]; hKey
0x18000a0a9  mov     r9d, 2001Fh; samDesired
0x18000a0af  xor     r8d, r8d; ulOptions
0x18000a0b2  mov     [rsp+290h+var_240], r14
0x18000a0b7  mov     [rsp+290h+var_238], r14
0x18000a0bc  mov     rsi, rdx
0x18000a0bf  mov     [rsp+290h+var_230], r14
0x18000a0c4  mov     [rsp+290h+phkResult], rax; phkResult
0x18000a0c9  call    cs:__imp_RegOpenKeyExW
0x18000a0cf  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a0d4  mov     ebx, eax
0x18000a0d6  test    eax, eax
0x18000a0d8  jnz     loc_18000A17B
0x18000a0de  mov     ebx, r14d
0x18000a0e1  test    rcx, rcx
0x18000a0e4  jz      short loc_18000A0EE
0x18000a0e6  call    cs:__imp_RegCloseKey
0x18000a0ec  mov     ebx, eax
0x18000a0ee  mov     rcx, [rsp+290h+var_230]
0x18000a0f3  mov     [rsp+290h+hKey], rcx
0x18000a0f8  test    ebx, ebx
0x18000a0fa  jnz     short loc_18000A17B
0x18000a0fc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000a101  jmp     short loc_18000A11D
0x18000a103  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000a108  lea     rcx, [rsp+290h+hKey]; this
0x18000a10d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000a112  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a117  mov     ebx, eax
0x18000a119  test    eax, eax
0x18000a11b  jnz     short loc_18000A17B
0x18000a11d  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000a122  mov     [rsp+290h+cchName], 100h
0x18000a12a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000a12f  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000a134  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000a139  lea     r8, [rsp+290h+Name]; lpName
0x18000a13e  mov     [rsp+290h+lpClass], r14; lpClass
0x18000a143  xor     edx, edx; dwIndex
0x18000a145  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000a14a  call    cs:__imp_RegEnumKeyExW
0x18000a150  test    eax, eax
0x18000a152  jz      short loc_18000A103
0x18000a154  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a159  test    rcx, rcx
0x18000a15c  jz      short loc_18000A169
0x18000a15e  call    cs:__imp_RegCloseKey
0x18000a164  mov     [rsp+290h+hKey], r14
0x18000a169  mov     rdx, rsi; unsigned __int16 *
0x18000a16c  mov     rcx, rdi; this
0x18000a16f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000a174  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a179  mov     ebx, eax
0x18000a17b  test    rcx, rcx
0x18000a17e  jz      short loc_18000A186
0x18000a180  call    cs:__imp_RegCloseKey
0x18000a186  mov     eax, ebx
0x18000a188  mov     rcx, [rbp+190h+var_20]
0x18000a18f  xor     rcx, rsp; StackCookie
0x18000a192  call    __security_check_cookie
0x18000a197  lea     r11, [rsp+290h+var_10]
0x18000a19f  mov     rbx, [r11+30h]
0x18000a1a3  mov     rsi, [r11+38h]
0x18000a1a7  mov     rsp, r11
0x18000a1aa  pop     r14
0x18000a1ac  pop     rdi
0x18000a1ad  pop     rbp
0x18000a1ae  retn
```
