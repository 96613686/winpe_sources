# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000b204`
- end: `0x18000b36e`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b204`
- `0x18000b6fc`

## callees

- `0x180004724`
- `0x18000b204`
- `0x180012db0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000b2f6`
- `ADVAPI32!RegEnumKeyExW` at `0x18000b2f6`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b265`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b265`
- `ADVAPI32!RegCloseKey` at `0x18000b288`
- `ADVAPI32!RegCloseKey` at `0x18000b310`
- `ADVAPI32!RegCloseKey` at `0x18000b338`
- `ADVAPI32!RegCloseKey` at `0x18000b288`
- `ADVAPI32!RegCloseKey` at `0x18000b310`
- `ADVAPI32!RegCloseKey` at `0x18000b338`

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
0x18000b204  mov     [rsp-8+arg_10], rbx
0x18000b209  mov     [rsp-8+arg_18], rsi
0x18000b20e  push    rbp
0x18000b20f  push    rdi
0x18000b210  push    r14
0x18000b212  lea     rbp, [rsp-180h]
0x18000b21a  sub     rsp, 280h
0x18000b221  mov     rax, cs:__security_cookie
0x18000b228  xor     rax, rsp
0x18000b22b  mov     [rbp+190h+var_20], rax
0x18000b232  xor     r14d, r14d
0x18000b235  lea     rax, [rsp+290h+var_230]
0x18000b23a  mov     rdi, rcx
0x18000b23d  mov     [rsp+290h+hKey], r14
0x18000b242  mov     rcx, [rcx]; hKey
0x18000b245  mov     r9d, 2001Fh; samDesired
0x18000b24b  xor     r8d, r8d; ulOptions
0x18000b24e  mov     [rsp+290h+var_240], r14
0x18000b253  mov     [rsp+290h+var_238], r14
0x18000b258  mov     rsi, rdx
0x18000b25b  mov     [rsp+290h+var_230], r14
0x18000b260  mov     [rsp+290h+phkResult], rax; phkResult
0x18000b265  call    cs:__imp_RegOpenKeyExW
0x18000b26c  nop     dword ptr [rax+rax+00h]
0x18000b271  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b276  mov     ebx, eax
0x18000b278  test    eax, eax
0x18000b27a  jnz     loc_18000B333
0x18000b280  mov     ebx, r14d
0x18000b283  test    rcx, rcx
0x18000b286  jz      short loc_18000B296
0x18000b288  call    cs:__imp_RegCloseKey
0x18000b28f  nop     dword ptr [rax+rax+00h]
0x18000b294  mov     ebx, eax
0x18000b296  mov     rcx, [rsp+290h+var_230]
0x18000b29b  mov     [rsp+290h+hKey], rcx
0x18000b2a0  test    ebx, ebx
0x18000b2a2  jnz     loc_18000B333
0x18000b2a8  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000b2ad  jmp     short loc_18000B2C9
0x18000b2af  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000b2b4  lea     rcx, [rsp+290h+hKey]; this
0x18000b2b9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000b2be  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b2c3  mov     ebx, eax
0x18000b2c5  test    eax, eax
0x18000b2c7  jnz     short loc_18000B333
0x18000b2c9  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000b2ce  mov     [rsp+290h+cchName], 100h
0x18000b2d6  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000b2db  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000b2e0  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000b2e5  lea     r8, [rsp+290h+Name]; lpName
0x18000b2ea  mov     [rsp+290h+lpClass], r14; lpClass
0x18000b2ef  xor     edx, edx; dwIndex
0x18000b2f1  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000b2f6  call    cs:__imp_RegEnumKeyExW
0x18000b2fd  nop     dword ptr [rax+rax+00h]
0x18000b302  test    eax, eax
0x18000b304  jz      short loc_18000B2AF
0x18000b306  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b30b  test    rcx, rcx
0x18000b30e  jz      short loc_18000B321
0x18000b310  call    cs:__imp_RegCloseKey
0x18000b317  nop     dword ptr [rax+rax+00h]
0x18000b31c  mov     [rsp+290h+hKey], r14
0x18000b321  mov     rdx, rsi; unsigned __int16 *
0x18000b324  mov     rcx, rdi; this
0x18000b327  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000b32c  mov     rcx, [rsp+290h+hKey]; hKey
0x18000b331  mov     ebx, eax
0x18000b333  test    rcx, rcx
0x18000b336  jz      short loc_18000B344
0x18000b338  call    cs:__imp_RegCloseKey
0x18000b33f  nop     dword ptr [rax+rax+00h]
0x18000b344  mov     eax, ebx
0x18000b346  mov     rcx, [rbp+190h+var_20]
0x18000b34d  xor     rcx, rsp; StackCookie
0x18000b350  call    __security_check_cookie
0x18000b355  lea     r11, [rsp+290h+var_10]
0x18000b35d  mov     rbx, [r11+30h]
0x18000b361  mov     rsi, [r11+38h]
0x18000b365  mov     rsp, r11
0x18000b368  pop     r14
0x18000b36a  pop     rdi
0x18000b36b  pop     rbp
0x18000b36c  retn
```
