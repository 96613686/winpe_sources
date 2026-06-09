# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800082d8`
- end: `0x180008429`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800082d8`
- `0x1800087a0`

## callees

- `0x180006268`
- `0x1800082d8`
- `0x1800b07d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180008356`
- `ADVAPI32!RegCloseKey` at `0x1800083d3`
- `ADVAPI32!RegCloseKey` at `0x1800083f5`
- `ADVAPI32!RegCloseKey` at `0x180008356`
- `ADVAPI32!RegCloseKey` at `0x1800083d3`
- `ADVAPI32!RegCloseKey` at `0x1800083f5`
- `ADVAPI32!RegEnumKeyExW` at `0x1800083bf`
- `ADVAPI32!RegEnumKeyExW` at `0x1800083bf`
- `ADVAPI32!RegOpenKeyExW` at `0x180008339`
- `ADVAPI32!RegOpenKeyExW` at `0x180008339`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  DWORD v4; // ebx
  HKEY v5; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  phkResult = 0;
  v4 = RegOpenKeyExW(*this, a2, 0, 0x2001Fu, &phkResult);
  if ( !v4 )
  {
    v5 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v5, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_9;
      v5 = hKey[0];
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_9:
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800082d8  mov     [rsp-8+arg_10], rbx
0x1800082dd  mov     [rsp-8+arg_18], rsi
0x1800082e2  push    rbp
0x1800082e3  push    rdi
0x1800082e4  push    r14
0x1800082e6  lea     rbp, [rsp-180h]
0x1800082ee  sub     rsp, 280h
0x1800082f5  mov     rax, cs:__security_cookie
0x1800082fc  xor     rax, rsp
0x1800082ff  mov     [rbp+190h+var_20], rax
0x180008306  mov     rsi, rdx
0x180008309  mov     rdi, rcx
0x18000830c  xor     r14d, r14d
0x18000830f  mov     [rsp+290h+hKey], r14
0x180008314  mov     [rsp+290h+var_240], r14
0x180008319  mov     [rsp+290h+var_238], r14
0x18000831e  mov     [rsp+290h+var_230], r14
0x180008323  lea     rax, [rsp+290h+var_230]
0x180008328  mov     [rsp+290h+phkResult], rax; phkResult
0x18000832d  mov     r9d, 2001Fh; samDesired
0x180008333  xor     r8d, r8d; ulOptions
0x180008336  mov     rcx, [rcx]; hKey
0x180008339  call    cs:__imp_RegOpenKeyExW
0x18000833f  mov     ebx, eax
0x180008341  test    eax, eax
0x180008343  jnz     loc_1800083EB
0x180008349  mov     ebx, r14d
0x18000834c  mov     rcx, [rsp+290h+hKey]; hKey
0x180008351  test    rcx, rcx
0x180008354  jz      short loc_180008363
0x180008356  call    cs:__imp_RegCloseKey
0x18000835c  mov     ebx, eax
0x18000835e  mov     [rsp+290h+hKey], r14
0x180008363  mov     rcx, [rsp+290h+var_230]
0x180008368  mov     [rsp+290h+hKey], rcx
0x18000836d  test    ebx, ebx
0x18000836f  jnz     short loc_1800083EB
0x180008371  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180008376  jmp     short loc_180008392
0x180008378  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000837d  lea     rcx, [rsp+290h+hKey]; this
0x180008382  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008387  mov     ebx, eax
0x180008389  test    eax, eax
0x18000838b  jnz     short loc_1800083EB
0x18000838d  mov     rcx, [rsp+290h+hKey]; hKey
0x180008392  lea     rax, [rsp+290h+ftLastWriteTime]
0x180008397  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000839c  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800083a1  mov     [rsp+290h+lpClass], r14; lpClass
0x1800083a6  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800083ab  mov     [rsp+290h+cchName], 100h
0x1800083b3  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800083b8  lea     r8, [rsp+290h+Name]; lpName
0x1800083bd  xor     edx, edx; dwIndex
0x1800083bf  call    cs:__imp_RegEnumKeyExW
0x1800083c5  test    eax, eax
0x1800083c7  jz      short loc_180008378
0x1800083c9  mov     rcx, [rsp+290h+hKey]; hKey
0x1800083ce  test    rcx, rcx
0x1800083d1  jz      short loc_1800083DE
0x1800083d3  call    cs:__imp_RegCloseKey
0x1800083d9  mov     [rsp+290h+hKey], r14
0x1800083de  mov     rdx, rsi; unsigned __int16 *
0x1800083e1  mov     rcx, rdi; this
0x1800083e4  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800083e9  mov     ebx, eax
0x1800083eb  mov     rcx, [rsp+290h+hKey]; hKey
0x1800083f0  test    rcx, rcx
0x1800083f3  jz      short loc_180008400
0x1800083f5  call    cs:__imp_RegCloseKey
0x1800083fb  mov     [rsp+290h+hKey], r14
0x180008400  mov     eax, ebx
0x180008402  mov     rcx, [rbp+190h+var_20]
0x180008409  xor     rcx, rsp; StackCookie
0x18000840c  call    __security_check_cookie
0x180008411  lea     r11, [rsp+290h+var_10]
0x180008419  mov     rbx, [r11+30h]
0x18000841d  mov     rsi, [r11+38h]
0x180008421  mov     rsp, r11
0x180008424  pop     r14
0x180008426  pop     rdi
0x180008427  pop     rbp
0x180008428  retn
```
