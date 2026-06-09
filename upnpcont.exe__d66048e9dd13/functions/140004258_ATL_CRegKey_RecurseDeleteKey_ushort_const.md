# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x140004258`
- end: `0x14000439f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003c44`
- `0x140004258`
- `0x140004954`

## callees

- `0x140001490`
- `0x140003698`
- `0x140004258`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400042b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400042b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400042d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000434e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004370`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400042d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000434e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004370`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000433a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000433a`

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
0x140004258  mov     [rsp-8+arg_10], rbx
0x14000425d  mov     [rsp-8+arg_18], rsi
0x140004262  push    rbp
0x140004263  push    rdi
0x140004264  push    r14
0x140004266  lea     rbp, [rsp-180h]
0x14000426e  sub     rsp, 280h
0x140004275  mov     rax, cs:__security_cookie
0x14000427c  xor     rax, rsp
0x14000427f  mov     [rbp+190h+var_20], rax
0x140004286  xor     r14d, r14d
0x140004289  lea     rax, [rsp+290h+var_230]
0x14000428e  mov     rdi, rcx
0x140004291  mov     [rsp+290h+hKey], r14
0x140004296  mov     rcx, [rcx]; hKey
0x140004299  mov     r9d, 2001Fh; samDesired
0x14000429f  xor     r8d, r8d; ulOptions
0x1400042a2  mov     [rsp+290h+var_240], r14
0x1400042a7  mov     [rsp+290h+var_238], r14
0x1400042ac  mov     rsi, rdx
0x1400042af  mov     [rsp+290h+var_230], r14
0x1400042b4  mov     [rsp+290h+phkResult], rax; phkResult
0x1400042b9  call    cs:__imp_RegOpenKeyExW
0x1400042bf  mov     rcx, [rsp+290h+hKey]; hKey
0x1400042c4  mov     ebx, eax
0x1400042c6  test    eax, eax
0x1400042c8  jnz     loc_14000436B
0x1400042ce  mov     ebx, r14d
0x1400042d1  test    rcx, rcx
0x1400042d4  jz      short loc_1400042DE
0x1400042d6  call    cs:__imp_RegCloseKey
0x1400042dc  mov     ebx, eax
0x1400042de  mov     rcx, [rsp+290h+var_230]
0x1400042e3  mov     [rsp+290h+hKey], rcx
0x1400042e8  test    ebx, ebx
0x1400042ea  jnz     short loc_14000436B
0x1400042ec  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1400042f1  jmp     short loc_14000430D
0x1400042f3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1400042f8  lea     rcx, [rsp+290h+hKey]; this
0x1400042fd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140004302  mov     rcx, [rsp+290h+hKey]; hKey
0x140004307  mov     ebx, eax
0x140004309  test    eax, eax
0x14000430b  jnz     short loc_14000436B
0x14000430d  lea     rax, [rsp+290h+ftLastWriteTime]
0x140004312  mov     [rsp+290h+cchName], 100h
0x14000431a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14000431f  lea     r9, [rsp+290h+cchName]; lpcchName
0x140004324  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x140004329  lea     r8, [rsp+290h+Name]; lpName
0x14000432e  mov     [rsp+290h+lpClass], r14; lpClass
0x140004333  xor     edx, edx; dwIndex
0x140004335  mov     [rsp+290h+phkResult], r14; lpReserved
0x14000433a  call    cs:__imp_RegEnumKeyExW
0x140004340  test    eax, eax
0x140004342  jz      short loc_1400042F3
0x140004344  mov     rcx, [rsp+290h+hKey]; hKey
0x140004349  test    rcx, rcx
0x14000434c  jz      short loc_140004359
0x14000434e  call    cs:__imp_RegCloseKey
0x140004354  mov     [rsp+290h+hKey], r14
0x140004359  mov     rdx, rsi; unsigned __int16 *
0x14000435c  mov     rcx, rdi; this
0x14000435f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140004364  mov     rcx, [rsp+290h+hKey]; hKey
0x140004369  mov     ebx, eax
0x14000436b  test    rcx, rcx
0x14000436e  jz      short loc_140004376
0x140004370  call    cs:__imp_RegCloseKey
0x140004376  mov     eax, ebx
0x140004378  mov     rcx, [rbp+190h+var_20]
0x14000437f  xor     rcx, rsp; StackCookie
0x140004382  call    __security_check_cookie
0x140004387  lea     r11, [rsp+290h+var_10]
0x14000438f  mov     rbx, [r11+30h]
0x140004393  mov     rsi, [r11+38h]
0x140004397  mov     rsp, r11
0x14000439a  pop     r14
0x14000439c  pop     rdi
0x14000439d  pop     rbp
0x14000439e  retn
```
