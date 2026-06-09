# IsSystemSpecialCase

- ea: `0x18000ca2c`
- end: `0x18000cb1c`
- name: `IsSystemSpecialCase`
- size: `240`
- prototype: `__int64 __fastcall(LPCWSTR lpString2)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c8c0`

## callees

- `0x18000ca2c`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000ca5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000ca5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ca98`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ca98`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18000ca72`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18000caaf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18000ca72`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18000caaf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cad4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000caf0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cad4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000caf0`

## pseudocode

```c
_BOOL8 __fastcall IsSystemSpecialCase(LPCWSTR lpString2)
{
  const WCHAR *v2; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR pszSrch[264]; // [rsp+230h] [rbp-228h] BYREF

  if ( !lpString1 && GetWindowsDirectoryW(Buffer, 0x104u) - 1 <= 0x102 )
    lpString1 = StrDupW(Buffer);
  v2 = qword_180059940;
  if ( !qword_180059940 )
  {
    if ( GetSystemDirectoryW(pszSrch, 0x104u) - 1 > 0x102 )
    {
      v2 = qword_180059940;
    }
    else
    {
      v2 = StrDupW(pszSrch);
      qword_180059940 = v2;
    }
  }
  if ( lpString1 )
  {
    if ( !lstrcmpiW(lpString1, lpString2) )
      return 1;
    v2 = qword_180059940;
  }
  return v2 && !lstrcmpiW(v2, lpString2);
}

```

## disassembly

```asm
0x18000ca2c  push    rbx
0x18000ca2e  sub     rsp, 450h
0x18000ca35  mov     rax, cs:__security_cookie
0x18000ca3c  xor     rax, rsp
0x18000ca3f  mov     [rsp+458h+var_18], rax
0x18000ca47  cmp     cs:lpString1, 0
0x18000ca4f  mov     rbx, rcx
0x18000ca52  jnz     short loc_18000CA7F
0x18000ca54  mov     edx, 104h; uSize
0x18000ca59  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x18000ca5e  call    cs:__imp_GetWindowsDirectoryW
0x18000ca64  dec     eax
0x18000ca66  cmp     eax, 102h
0x18000ca6b  ja      short loc_18000CA7F
0x18000ca6d  lea     rcx, [rsp+458h+Buffer]; pszSrch
0x18000ca72  call    cs:__imp_StrDupW
0x18000ca78  mov     cs:lpString1, rax
0x18000ca7f  mov     rax, cs:qword_180059940
0x18000ca86  test    rax, rax
0x18000ca89  jnz     short loc_18000CAC5
0x18000ca8b  mov     edx, 104h; uSize
0x18000ca90  lea     rcx, [rsp+458h+pszSrch]; lpBuffer
0x18000ca98  call    cs:__imp_GetSystemDirectoryW
0x18000ca9e  dec     eax
0x18000caa0  cmp     eax, 102h
0x18000caa5  ja      short loc_18000CABE
0x18000caa7  lea     rcx, [rsp+458h+pszSrch]; pszSrch
0x18000caaf  call    cs:__imp_StrDupW
0x18000cab5  mov     cs:qword_180059940, rax
0x18000cabc  jmp     short loc_18000CAC5
0x18000cabe  mov     rax, cs:qword_180059940
0x18000cac5  mov     rcx, cs:lpString1; lpString1
0x18000cacc  test    rcx, rcx
0x18000cacf  jz      short loc_18000CAE5
0x18000cad1  mov     rdx, rbx; lpString2
0x18000cad4  call    cs:__imp_lstrcmpiW
0x18000cada  test    eax, eax
0x18000cadc  jz      short loc_18000CAFA
0x18000cade  mov     rax, cs:qword_180059940
0x18000cae5  test    rax, rax
0x18000cae8  jz      short loc_18000CB01
0x18000caea  mov     rdx, rbx; lpString2
0x18000caed  mov     rcx, rax; lpString1
0x18000caf0  call    cs:__imp_lstrcmpiW
0x18000caf6  test    eax, eax
0x18000caf8  jnz     short loc_18000CB01
0x18000cafa  mov     eax, 1
0x18000caff  jmp     short loc_18000CB03
0x18000cb01  xor     eax, eax
0x18000cb03  mov     rcx, [rsp+458h+var_18]
0x18000cb0b  xor     rcx, rsp; StackCookie
0x18000cb0e  call    __security_check_cookie
0x18000cb13  add     rsp, 450h
0x18000cb1a  pop     rbx
0x18000cb1b  retn
```
