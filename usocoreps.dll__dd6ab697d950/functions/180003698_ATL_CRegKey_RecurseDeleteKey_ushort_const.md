# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180003698`
- end: `0x1800037df`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003698`
- `0x180003b5c`

## callees

- `0x180001510`
- `0x180003054`
- `0x180003698`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000378e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000378e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037b0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000377a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000377a`

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
0x180003698  mov     [rsp-8+arg_10], rbx
0x18000369d  mov     [rsp-8+arg_18], rsi
0x1800036a2  push    rbp
0x1800036a3  push    rdi
0x1800036a4  push    r14
0x1800036a6  lea     rbp, [rsp-180h]
0x1800036ae  sub     rsp, 280h
0x1800036b5  mov     rax, cs:__security_cookie
0x1800036bc  xor     rax, rsp
0x1800036bf  mov     [rbp+190h+var_20], rax
0x1800036c6  xor     r14d, r14d
0x1800036c9  lea     rax, [rsp+290h+var_230]
0x1800036ce  mov     rdi, rcx
0x1800036d1  mov     [rsp+290h+hKey], r14
0x1800036d6  mov     rcx, [rcx]; hKey
0x1800036d9  mov     r9d, 2001Fh; samDesired
0x1800036df  xor     r8d, r8d; ulOptions
0x1800036e2  mov     [rsp+290h+var_240], r14
0x1800036e7  mov     [rsp+290h+var_238], r14
0x1800036ec  mov     rsi, rdx
0x1800036ef  mov     [rsp+290h+var_230], r14
0x1800036f4  mov     [rsp+290h+phkResult], rax; phkResult
0x1800036f9  call    cs:__imp_RegOpenKeyExW
0x1800036ff  mov     rcx, [rsp+290h+hKey]; hKey
0x180003704  mov     ebx, eax
0x180003706  test    eax, eax
0x180003708  jnz     loc_1800037AB
0x18000370e  mov     ebx, r14d
0x180003711  test    rcx, rcx
0x180003714  jz      short loc_18000371E
0x180003716  call    cs:__imp_RegCloseKey
0x18000371c  mov     ebx, eax
0x18000371e  mov     rcx, [rsp+290h+var_230]
0x180003723  mov     [rsp+290h+hKey], rcx
0x180003728  test    ebx, ebx
0x18000372a  jnz     short loc_1800037AB
0x18000372c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180003731  jmp     short loc_18000374D
0x180003733  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180003738  lea     rcx, [rsp+290h+hKey]; this
0x18000373d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003742  mov     rcx, [rsp+290h+hKey]; hKey
0x180003747  mov     ebx, eax
0x180003749  test    eax, eax
0x18000374b  jnz     short loc_1800037AB
0x18000374d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180003752  mov     [rsp+290h+cchName], 100h
0x18000375a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000375f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180003764  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180003769  lea     r8, [rsp+290h+Name]; lpName
0x18000376e  mov     [rsp+290h+lpClass], r14; lpClass
0x180003773  xor     edx, edx; dwIndex
0x180003775  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000377a  call    cs:__imp_RegEnumKeyExW
0x180003780  test    eax, eax
0x180003782  jz      short loc_180003733
0x180003784  mov     rcx, [rsp+290h+hKey]; hKey
0x180003789  test    rcx, rcx
0x18000378c  jz      short loc_180003799
0x18000378e  call    cs:__imp_RegCloseKey
0x180003794  mov     [rsp+290h+hKey], r14
0x180003799  mov     rdx, rsi; unsigned __int16 *
0x18000379c  mov     rcx, rdi; this
0x18000379f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800037a4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800037a9  mov     ebx, eax
0x1800037ab  test    rcx, rcx
0x1800037ae  jz      short loc_1800037B6
0x1800037b0  call    cs:__imp_RegCloseKey
0x1800037b6  mov     eax, ebx
0x1800037b8  mov     rcx, [rbp+190h+var_20]
0x1800037bf  xor     rcx, rsp; StackCookie
0x1800037c2  call    __security_check_cookie
0x1800037c7  lea     r11, [rsp+290h+var_10]
0x1800037cf  mov     rbx, [r11+30h]
0x1800037d3  mov     rsi, [r11+38h]
0x1800037d7  mov     rsp, r11
0x1800037da  pop     r14
0x1800037dc  pop     rdi
0x1800037dd  pop     rbp
0x1800037de  retn
```
