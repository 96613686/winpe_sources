# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004548`
- end: `0x18000468f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004548`
- `0x1800049ec`

## callees

- `0x180003ce8`
- `0x180004548`
- `0x18001bf40`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800045c6`
- `ADVAPI32!RegCloseKey` at `0x18000463e`
- `ADVAPI32!RegCloseKey` at `0x180004660`
- `ADVAPI32!RegCloseKey` at `0x1800045c6`
- `ADVAPI32!RegCloseKey` at `0x18000463e`
- `ADVAPI32!RegCloseKey` at `0x180004660`
- `ADVAPI32!RegEnumKeyExW` at `0x18000462a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000462a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800045a9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800045a9`

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
0x180004548  mov     [rsp-8+arg_10], rbx
0x18000454d  mov     [rsp-8+arg_18], rsi
0x180004552  push    rbp
0x180004553  push    rdi
0x180004554  push    r14
0x180004556  lea     rbp, [rsp-180h]
0x18000455e  sub     rsp, 280h
0x180004565  mov     rax, cs:__security_cookie
0x18000456c  xor     rax, rsp
0x18000456f  mov     [rbp+190h+var_20], rax
0x180004576  xor     r14d, r14d
0x180004579  lea     rax, [rsp+290h+var_230]
0x18000457e  mov     rdi, rcx
0x180004581  mov     [rsp+290h+hKey], r14
0x180004586  mov     rcx, [rcx]; hKey
0x180004589  mov     r9d, 2001Fh; samDesired
0x18000458f  xor     r8d, r8d; ulOptions
0x180004592  mov     [rsp+290h+var_240], r14
0x180004597  mov     [rsp+290h+var_238], r14
0x18000459c  mov     rsi, rdx
0x18000459f  mov     [rsp+290h+var_230], r14
0x1800045a4  mov     [rsp+290h+phkResult], rax; phkResult
0x1800045a9  call    cs:__imp_RegOpenKeyExW
0x1800045af  mov     rcx, [rsp+290h+hKey]; hKey
0x1800045b4  mov     ebx, eax
0x1800045b6  test    eax, eax
0x1800045b8  jnz     loc_18000465B
0x1800045be  mov     ebx, r14d
0x1800045c1  test    rcx, rcx
0x1800045c4  jz      short loc_1800045CE
0x1800045c6  call    cs:__imp_RegCloseKey
0x1800045cc  mov     ebx, eax
0x1800045ce  mov     rcx, [rsp+290h+var_230]
0x1800045d3  mov     [rsp+290h+hKey], rcx
0x1800045d8  test    ebx, ebx
0x1800045da  jnz     short loc_18000465B
0x1800045dc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800045e1  jmp     short loc_1800045FD
0x1800045e3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800045e8  lea     rcx, [rsp+290h+hKey]; this
0x1800045ed  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800045f2  mov     rcx, [rsp+290h+hKey]; hKey
0x1800045f7  mov     ebx, eax
0x1800045f9  test    eax, eax
0x1800045fb  jnz     short loc_18000465B
0x1800045fd  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004602  mov     [rsp+290h+cchName], 100h
0x18000460a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000460f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004614  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004619  lea     r8, [rsp+290h+Name]; lpName
0x18000461e  mov     [rsp+290h+lpClass], r14; lpClass
0x180004623  xor     edx, edx; dwIndex
0x180004625  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000462a  call    cs:__imp_RegEnumKeyExW
0x180004630  test    eax, eax
0x180004632  jz      short loc_1800045E3
0x180004634  mov     rcx, [rsp+290h+hKey]; hKey
0x180004639  test    rcx, rcx
0x18000463c  jz      short loc_180004649
0x18000463e  call    cs:__imp_RegCloseKey
0x180004644  mov     [rsp+290h+hKey], r14
0x180004649  mov     rdx, rsi; unsigned __int16 *
0x18000464c  mov     rcx, rdi; this
0x18000464f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004654  mov     rcx, [rsp+290h+hKey]; hKey
0x180004659  mov     ebx, eax
0x18000465b  test    rcx, rcx
0x18000465e  jz      short loc_180004666
0x180004660  call    cs:__imp_RegCloseKey
0x180004666  mov     eax, ebx
0x180004668  mov     rcx, [rbp+190h+var_20]
0x18000466f  xor     rcx, rsp; StackCookie
0x180004672  call    __security_check_cookie
0x180004677  lea     r11, [rsp+290h+var_10]
0x18000467f  mov     rbx, [r11+30h]
0x180004683  mov     rsi, [r11+38h]
0x180004687  mov     rsp, r11
0x18000468a  pop     r14
0x18000468c  pop     rdi
0x18000468d  pop     rbp
0x18000468e  retn
```
