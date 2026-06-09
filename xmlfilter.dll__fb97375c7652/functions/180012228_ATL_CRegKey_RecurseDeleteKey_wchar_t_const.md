# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x180012228`
- end: `0x18001236f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012228`
- `0x1800126ec`

## callees

- `0x1800020e0`
- `0x180011958`
- `0x180012228`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001230a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001230a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012289`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012289`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001231e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012340`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001231e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012340`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const wchar_t *a2)
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
0x180012228  mov     [rsp-8+arg_10], rbx
0x18001222d  mov     [rsp-8+arg_18], rsi
0x180012232  push    rbp
0x180012233  push    rdi
0x180012234  push    r14
0x180012236  lea     rbp, [rsp-180h]
0x18001223e  sub     rsp, 280h
0x180012245  mov     rax, cs:__security_cookie
0x18001224c  xor     rax, rsp
0x18001224f  mov     [rbp+190h+var_20], rax
0x180012256  xor     r14d, r14d
0x180012259  lea     rax, [rsp+290h+var_230]
0x18001225e  mov     rdi, rcx
0x180012261  mov     [rsp+290h+hKey], r14
0x180012266  mov     rcx, [rcx]; hKey
0x180012269  mov     r9d, 2001Fh; samDesired
0x18001226f  xor     r8d, r8d; ulOptions
0x180012272  mov     [rsp+290h+var_240], r14
0x180012277  mov     [rsp+290h+var_238], r14
0x18001227c  mov     rsi, rdx
0x18001227f  mov     [rsp+290h+var_230], r14
0x180012284  mov     [rsp+290h+phkResult], rax; phkResult
0x180012289  call    cs:__imp_RegOpenKeyExW
0x18001228f  mov     rcx, [rsp+290h+hKey]; hKey
0x180012294  mov     ebx, eax
0x180012296  test    eax, eax
0x180012298  jnz     loc_18001233B
0x18001229e  mov     ebx, r14d
0x1800122a1  test    rcx, rcx
0x1800122a4  jz      short loc_1800122AE
0x1800122a6  call    cs:__imp_RegCloseKey
0x1800122ac  mov     ebx, eax
0x1800122ae  mov     rcx, [rsp+290h+var_230]
0x1800122b3  mov     [rsp+290h+hKey], rcx
0x1800122b8  test    ebx, ebx
0x1800122ba  jnz     short loc_18001233B
0x1800122bc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800122c1  jmp     short loc_1800122DD
0x1800122c3  lea     rdx, [rsp+290h+Name]; wchar_t *
0x1800122c8  lea     rcx, [rsp+290h+hKey]; this
0x1800122cd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x1800122d2  mov     rcx, [rsp+290h+hKey]; hKey
0x1800122d7  mov     ebx, eax
0x1800122d9  test    eax, eax
0x1800122db  jnz     short loc_18001233B
0x1800122dd  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800122e2  mov     [rsp+290h+cchName], 100h
0x1800122ea  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800122ef  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800122f4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800122f9  lea     r8, [rsp+290h+Name]; lpName
0x1800122fe  mov     [rsp+290h+lpClass], r14; lpClass
0x180012303  xor     edx, edx; dwIndex
0x180012305  mov     [rsp+290h+phkResult], r14; lpReserved
0x18001230a  call    cs:__imp_RegEnumKeyExW
0x180012310  test    eax, eax
0x180012312  jz      short loc_1800122C3
0x180012314  mov     rcx, [rsp+290h+hKey]; hKey
0x180012319  test    rcx, rcx
0x18001231c  jz      short loc_180012329
0x18001231e  call    cs:__imp_RegCloseKey
0x180012324  mov     [rsp+290h+hKey], r14
0x180012329  mov     rdx, rsi; wchar_t *
0x18001232c  mov     rcx, rdi; this
0x18001232f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180012334  mov     rcx, [rsp+290h+hKey]; hKey
0x180012339  mov     ebx, eax
0x18001233b  test    rcx, rcx
0x18001233e  jz      short loc_180012346
0x180012340  call    cs:__imp_RegCloseKey
0x180012346  mov     eax, ebx
0x180012348  mov     rcx, [rbp+190h+var_20]
0x18001234f  xor     rcx, rsp; StackCookie
0x180012352  call    __security_check_cookie
0x180012357  lea     r11, [rsp+290h+var_10]
0x18001235f  mov     rbx, [r11+30h]
0x180012363  mov     rsi, [r11+38h]
0x180012367  mov     rsp, r11
0x18001236a  pop     r14
0x18001236c  pop     rdi
0x18001236d  pop     rbp
0x18001236e  retn
```
