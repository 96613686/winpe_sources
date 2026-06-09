# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000409c`
- end: `0x180004206`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000409c`
- `0x18000459c`

## callees

- `0x1800015b0`
- `0x1800037ec`
- `0x18000409c`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000418e`
- `ADVAPI32!RegEnumKeyExW` at `0x18000418e`
- `ADVAPI32!RegCloseKey` at `0x180004120`
- `ADVAPI32!RegCloseKey` at `0x1800041a8`
- `ADVAPI32!RegCloseKey` at `0x1800041d0`
- `ADVAPI32!RegCloseKey` at `0x180004120`
- `ADVAPI32!RegCloseKey` at `0x1800041a8`
- `ADVAPI32!RegCloseKey` at `0x1800041d0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800040fd`
- `ADVAPI32!RegOpenKeyExW` at `0x1800040fd`

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
0x18000409c  mov     [rsp-8+arg_10], rbx
0x1800040a1  mov     [rsp-8+arg_18], rsi
0x1800040a6  push    rbp
0x1800040a7  push    rdi
0x1800040a8  push    r14
0x1800040aa  lea     rbp, [rsp-180h]
0x1800040b2  sub     rsp, 280h
0x1800040b9  mov     rax, cs:__security_cookie
0x1800040c0  xor     rax, rsp
0x1800040c3  mov     [rbp+190h+var_20], rax
0x1800040ca  xor     r14d, r14d
0x1800040cd  lea     rax, [rsp+290h+var_230]
0x1800040d2  mov     rdi, rcx
0x1800040d5  mov     [rsp+290h+hKey], r14
0x1800040da  mov     rcx, [rcx]; hKey
0x1800040dd  mov     r9d, 2001Fh; samDesired
0x1800040e3  xor     r8d, r8d; ulOptions
0x1800040e6  mov     [rsp+290h+var_240], r14
0x1800040eb  mov     [rsp+290h+var_238], r14
0x1800040f0  mov     rsi, rdx
0x1800040f3  mov     [rsp+290h+var_230], r14
0x1800040f8  mov     [rsp+290h+phkResult], rax; phkResult
0x1800040fd  call    cs:__imp_RegOpenKeyExW
0x180004104  nop     dword ptr [rax+rax+00h]
0x180004109  mov     rcx, [rsp+290h+hKey]; hKey
0x18000410e  mov     ebx, eax
0x180004110  test    eax, eax
0x180004112  jnz     loc_1800041CB
0x180004118  mov     ebx, r14d
0x18000411b  test    rcx, rcx
0x18000411e  jz      short loc_18000412E
0x180004120  call    cs:__imp_RegCloseKey
0x180004127  nop     dword ptr [rax+rax+00h]
0x18000412c  mov     ebx, eax
0x18000412e  mov     rcx, [rsp+290h+var_230]
0x180004133  mov     [rsp+290h+hKey], rcx
0x180004138  test    ebx, ebx
0x18000413a  jnz     loc_1800041CB
0x180004140  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180004145  jmp     short loc_180004161
0x180004147  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000414c  lea     rcx, [rsp+290h+hKey]; this
0x180004151  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004156  mov     rcx, [rsp+290h+hKey]; hKey
0x18000415b  mov     ebx, eax
0x18000415d  test    eax, eax
0x18000415f  jnz     short loc_1800041CB
0x180004161  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004166  mov     [rsp+290h+cchName], 100h
0x18000416e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004173  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004178  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000417d  lea     r8, [rsp+290h+Name]; lpName
0x180004182  mov     [rsp+290h+lpClass], r14; lpClass
0x180004187  xor     edx, edx; dwIndex
0x180004189  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000418e  call    cs:__imp_RegEnumKeyExW
0x180004195  nop     dword ptr [rax+rax+00h]
0x18000419a  test    eax, eax
0x18000419c  jz      short loc_180004147
0x18000419e  mov     rcx, [rsp+290h+hKey]; hKey
0x1800041a3  test    rcx, rcx
0x1800041a6  jz      short loc_1800041B9
0x1800041a8  call    cs:__imp_RegCloseKey
0x1800041af  nop     dword ptr [rax+rax+00h]
0x1800041b4  mov     [rsp+290h+hKey], r14
0x1800041b9  mov     rdx, rsi; unsigned __int16 *
0x1800041bc  mov     rcx, rdi; this
0x1800041bf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800041c4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800041c9  mov     ebx, eax
0x1800041cb  test    rcx, rcx
0x1800041ce  jz      short loc_1800041DC
0x1800041d0  call    cs:__imp_RegCloseKey
0x1800041d7  nop     dword ptr [rax+rax+00h]
0x1800041dc  mov     eax, ebx
0x1800041de  mov     rcx, [rbp+190h+var_20]
0x1800041e5  xor     rcx, rsp; StackCookie
0x1800041e8  call    __security_check_cookie
0x1800041ed  lea     r11, [rsp+290h+var_10]
0x1800041f5  mov     rbx, [r11+30h]
0x1800041f9  mov     rsi, [r11+38h]
0x1800041fd  mov     rsp, r11
0x180004200  pop     r14
0x180004202  pop     rdi
0x180004203  pop     rbp
0x180004204  retn
```
