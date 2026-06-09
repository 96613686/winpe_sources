# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180014668`
- end: `0x1800147b9`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014668`
- `0x180014b28`

## callees

- `0x180013e88`
- `0x180014668`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001474f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001474f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800146e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014763`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800146e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014763`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014785`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800146c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800146c9`

## pseudocode

```c
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
0x180014668  mov     [rsp-8+arg_10], rbx
0x18001466d  mov     [rsp-8+arg_18], rsi
0x180014672  push    rbp
0x180014673  push    rdi
0x180014674  push    r14
0x180014676  lea     rbp, [rsp-180h]
0x18001467e  sub     rsp, 280h
0x180014685  mov     rax, cs:__security_cookie
0x18001468c  xor     rax, rsp
0x18001468f  mov     [rbp+190h+var_20], rax
0x180014696  mov     rsi, rdx
0x180014699  mov     rdi, rcx
0x18001469c  xor     r14d, r14d
0x18001469f  mov     [rsp+290h+hKey], r14
0x1800146a4  mov     [rsp+290h+var_240], r14
0x1800146a9  mov     [rsp+290h+var_238], r14
0x1800146ae  mov     [rsp+290h+var_230], r14
0x1800146b3  lea     rax, [rsp+290h+var_230]
0x1800146b8  mov     [rsp+290h+phkResult], rax; phkResult
0x1800146bd  mov     r9d, 2001Fh; samDesired
0x1800146c3  xor     r8d, r8d; ulOptions
0x1800146c6  mov     rcx, [rcx]; hKey
0x1800146c9  call    cs:__imp_RegOpenKeyExW
0x1800146cf  mov     ebx, eax
0x1800146d1  test    eax, eax
0x1800146d3  jnz     loc_18001477B
0x1800146d9  mov     ebx, r14d
0x1800146dc  mov     rcx, [rsp+290h+hKey]; hKey
0x1800146e1  test    rcx, rcx
0x1800146e4  jz      short loc_1800146F3
0x1800146e6  call    cs:__imp_RegCloseKey
0x1800146ec  mov     ebx, eax
0x1800146ee  mov     [rsp+290h+hKey], r14
0x1800146f3  mov     rcx, [rsp+290h+var_230]
0x1800146f8  mov     [rsp+290h+hKey], rcx
0x1800146fd  test    ebx, ebx
0x1800146ff  jnz     short loc_18001477B
0x180014701  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180014706  jmp     short loc_180014722
0x180014708  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18001470d  lea     rcx, [rsp+290h+hKey]; this
0x180014712  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180014717  mov     ebx, eax
0x180014719  test    eax, eax
0x18001471b  jnz     short loc_18001477B
0x18001471d  mov     rcx, [rsp+290h+hKey]; hKey
0x180014722  lea     rax, [rsp+290h+ftLastWriteTime]
0x180014727  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001472c  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180014731  mov     [rsp+290h+lpClass], r14; lpClass
0x180014736  mov     [rsp+290h+phkResult], r14; lpReserved
0x18001473b  mov     [rsp+290h+cchName], 100h
0x180014743  lea     r9, [rsp+290h+cchName]; lpcchName
0x180014748  lea     r8, [rsp+290h+Name]; lpName
0x18001474d  xor     edx, edx; dwIndex
0x18001474f  call    cs:__imp_RegEnumKeyExW
0x180014755  test    eax, eax
0x180014757  jz      short loc_180014708
0x180014759  mov     rcx, [rsp+290h+hKey]; hKey
0x18001475e  test    rcx, rcx
0x180014761  jz      short loc_18001476E
0x180014763  call    cs:__imp_RegCloseKey
0x180014769  mov     [rsp+290h+hKey], r14
0x18001476e  mov     rdx, rsi; unsigned __int16 *
0x180014771  mov     rcx, rdi; this
0x180014774  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180014779  mov     ebx, eax
0x18001477b  mov     rcx, [rsp+290h+hKey]; hKey
0x180014780  test    rcx, rcx
0x180014783  jz      short loc_180014790
0x180014785  call    cs:__imp_RegCloseKey
0x18001478b  mov     [rsp+290h+hKey], r14
0x180014790  mov     eax, ebx
0x180014792  mov     rcx, [rbp+190h+var_20]
0x180014799  xor     rcx, rsp; StackCookie
0x18001479c  call    __security_check_cookie
0x1800147a1  lea     r11, [rsp+290h+var_10]
0x1800147a9  mov     rbx, [r11+30h]
0x1800147ad  mov     rsi, [r11+38h]
0x1800147b1  mov     rsp, r11
0x1800147b4  pop     r14
0x1800147b6  pop     rdi
0x1800147b7  pop     rbp
0x1800147b8  retn
```
