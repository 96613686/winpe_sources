# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000b718`
- end: `0x18000b85f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b718`
- `0x18000c254`

## callees

- `0x18000aa78`
- `0x18000b718`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b796`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b80e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b830`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b796`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b80e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b830`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b7fa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b7fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b779`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b779`

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
0x18000b718  mov     [rsp-8+arg_10], rbx
0x18000b71d  mov     [rsp-8+arg_18], rsi
0x18000b722  push    rbp
0x18000b723  push    rdi
0x18000b724  push    r14
0x18000b726  lea     rbp, [rsp-180h]
0x18000b72e  sub     rsp, 280h
0x18000b735  mov     rax, cs:__security_cookie
0x18000b73c  xor     rax, rsp
0x18000b73f  mov     [rbp+190h+var_20], rax
0x18000b746  xor     r14d, r14d
0x18000b749  lea     rax, [rsp+290h+var_230]
0x18000b74e  mov     rdi, rcx
0x18000b751  mov     [rsp+290h+hKey], r14
0x18000b756  mov     rcx, [rcx]; hKey
0x18000b759  mov     r9d, 2001Fh; samDesired
0x18000b75f  xor     r8d, r8d; ulOptions
0x18000b762  mov     [rsp+290h+var_240], r14
0x18000b767  mov     [rsp+290h+var_238], r14
0x18000b76c  mov     rsi, rdx
0x18000b76f  mov     [rsp+290h+var_230], r14
0x18000b774  mov     [rsp+290h+phkResult], rax; phkResult
0x18000b779  call    cs:__imp_RegOpenKeyExW
0x18000b77f  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b784  mov     ebx, eax
0x18000b786  test    eax, eax
0x18000b788  jnz     loc_18000B82B
0x18000b78e  mov     ebx, r14d
0x18000b791  test    rcx, rcx
0x18000b794  jz      short loc_18000B79E
0x18000b796  call    cs:__imp_RegCloseKey
0x18000b79c  mov     ebx, eax
0x18000b79e  mov     rcx, [rsp+290h+var_230]
0x18000b7a3  mov     [rsp+290h+hKey], rcx
0x18000b7a8  test    ebx, ebx
0x18000b7aa  jnz     short loc_18000B82B
0x18000b7ac  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000b7b1  jmp     short loc_18000B7CD
0x18000b7b3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000b7b8  lea     rcx, [rsp+290h+hKey]; this
0x18000b7bd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000b7c2  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b7c7  mov     ebx, eax
0x18000b7c9  test    eax, eax
0x18000b7cb  jnz     short loc_18000B82B
0x18000b7cd  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000b7d2  mov     [rsp+290h+cchName], 100h
0x18000b7da  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000b7df  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000b7e4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000b7e9  lea     r8, [rsp+290h+Name]; lpName
0x18000b7ee  mov     [rsp+290h+lpClass], r14; lpClass
0x18000b7f3  xor     edx, edx; dwIndex
0x18000b7f5  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000b7fa  call    cs:__imp_RegEnumKeyExW
0x18000b800  test    eax, eax
0x18000b802  jz      short loc_18000B7B3
0x18000b804  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b809  test    rcx, rcx
0x18000b80c  jz      short loc_18000B819
0x18000b80e  call    cs:__imp_RegCloseKey
0x18000b814  mov     [rsp+290h+hKey], r14
0x18000b819  mov     rdx, rsi; unsigned __int16 *
0x18000b81c  mov     rcx, rdi; this
0x18000b81f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000b824  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b829  mov     ebx, eax
0x18000b82b  test    rcx, rcx
0x18000b82e  jz      short loc_18000B836
0x18000b830  call    cs:__imp_RegCloseKey
0x18000b836  mov     eax, ebx
0x18000b838  mov     rcx, [rbp+190h+var_20]
0x18000b83f  xor     rcx, rsp; StackCookie
0x18000b842  call    __security_check_cookie
0x18000b847  lea     r11, [rsp+290h+var_10]
0x18000b84f  mov     rbx, [r11+30h]
0x18000b853  mov     rsi, [r11+38h]
0x18000b857  mov     rsp, r11
0x18000b85a  pop     r14
0x18000b85c  pop     rdi
0x18000b85d  pop     rbp
0x18000b85e  retn
```
