# CThemeFile::_GetInboxScreenSaverName(ushort const *,ushort * *)

- ea: `0x180052e24`
- end: `0x180052f8b`
- name: `?_GetInboxScreenSaverName@CThemeFile@@AEAAJPEBGPEAPEAG@Z`
- size: `359`
- prototype: `int(CThemeFile *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800520d0`

## callees

- `0x1800089c0`
- `0x180015190`
- `0x1800358c0`
- `0x180052e24`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180052e6b`
- `SHELL32!SHGetFolderPathEx` at `0x180052e6b`
- `SHLWAPI!PathIsPrefixW` at `0x180052e86`
- `SHLWAPI!PathIsPrefixW` at `0x180052e86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052f27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052f27`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180052efb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180052efb`

## pseudocode

```c
__int64 __fastcall CThemeFile::_GetInboxScreenSaverName(
        CThemeFile *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v5; // ebx
  char v6; // di
  int v7; // esi
  WCHAR String2[264]; // [rsp+30h] [rbp-458h] BYREF
  WCHAR pszPrefix[264]; // [rsp+240h] [rbp-248h] BYREF

  v5 = SHGetFolderPathEx(&FOLDERID_System, 0, 0, pszPrefix, 260);
  if ( v5 >= 0 )
  {
    if ( PathIsPrefixW(pszPrefix, a2) )
    {
      v6 = 0;
      v7 = 0;
      while ( v5 >= 0 && !v6 )
      {
        v5 = StringCchPrintfW(String2, 0x104u, L"%s\\%s.scr", pszPrefix, (&off_18006FA00)[2 * v7]);
        if ( v5 >= 0 && CompareStringOrdinal(a2, -1, String2, -1, 1) == 2 )
        {
          v6 = 1;
          if ( LoadStringW(g_hinst, *((_DWORD *)&off_18006FA00 + 4 * v7 + 2), String2, 260) )
            v5 = HrSysAllocString(String2, a3);
          else
            v5 = -2147467259;
        }
        if ( (unsigned int)++v7 >= 6 )
        {
          if ( v5 < 0 || v6 )
            return (unsigned int)v5;
          return (unsigned int)-2147467259;
        }
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180052e24  mov     [rsp+arg_0], rbx
0x180052e29  push    rbp
0x180052e2a  push    rsi
0x180052e2b  push    rdi
0x180052e2c  push    r14
0x180052e2e  push    r15
0x180052e30  sub     rsp, 460h
0x180052e37  mov     rax, cs:__security_cookie
0x180052e3e  xor     rax, rsp
0x180052e41  mov     [rsp+488h+var_38], rax
0x180052e49  mov     r15, r8
0x180052e4c  mov     [rsp+488h+bIgnoreCase], 104h
0x180052e54  mov     rbp, rdx
0x180052e57  lea     r9, [rsp+488h+pszPrefix]
0x180052e5f  xor     r8d, r8d
0x180052e62  lea     rcx, FOLDERID_System
0x180052e69  xor     edx, edx
0x180052e6b  call    cs:__imp_SHGetFolderPathEx
0x180052e71  mov     ebx, eax
0x180052e73  test    eax, eax
0x180052e75  js      loc_180052F62
0x180052e7b  mov     rdx, rbp; pszPath
0x180052e7e  lea     rcx, [rsp+488h+pszPrefix]; pszPrefix
0x180052e86  call    cs:__imp_PathIsPrefixW
0x180052e8c  test    eax, eax
0x180052e8e  jz      loc_180052F5D
0x180052e94  xor     dil, dil
0x180052e97  xor     esi, esi
0x180052e99  lea     rax, off_18006FA00; "bubbles"
0x180052ea0  test    ebx, ebx
0x180052ea2  js      loc_180052F62
0x180052ea8  test    dil, dil
0x180052eab  jnz     loc_180052F62
0x180052eb1  movsxd  r14, esi
0x180052eb4  lea     r9, [rsp+488h+pszPrefix]
0x180052ebc  add     r14, r14
0x180052ebf  lea     r8, aSSScr; "%s\\%s.scr"
0x180052ec6  mov     edx, 104h; unsigned __int64
0x180052ecb  lea     rcx, [rsp+488h+String2]; unsigned __int16 *
0x180052ed0  mov     rax, [rax+r14*8]
0x180052ed4  mov     qword ptr [rsp+488h+bIgnoreCase], rax
0x180052ed9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052ede  mov     ebx, eax
0x180052ee0  test    eax, eax
0x180052ee2  js      short loc_180052F47
0x180052ee4  or      r9d, 0FFFFFFFFh; cchCount2
0x180052ee8  mov     [rsp+488h+bIgnoreCase], 1; bIgnoreCase
0x180052ef0  or      edx, r9d; cchCount1
0x180052ef3  lea     r8, [rsp+488h+String2]; lpString2
0x180052ef8  mov     rcx, rbp; lpString1
0x180052efb  call    cs:__imp_CompareStringOrdinal
0x180052f01  cmp     eax, 2
0x180052f04  jnz     short loc_180052F47
0x180052f06  mov     rcx, cs:g_hinst; hInstance
0x180052f0d  lea     rdx, off_18006FA00; "bubbles"
0x180052f14  mov     edx, [rdx+r14*8+8]; uID
0x180052f19  lea     r8, [rsp+488h+String2]; lpBuffer
0x180052f1e  mov     r9d, 104h; cchBufferMax
0x180052f24  mov     dil, 1
0x180052f27  call    cs:__imp_LoadStringW
0x180052f2d  test    eax, eax
0x180052f2f  jz      short loc_180052F42
0x180052f31  mov     rdx, r15; unsigned __int16 **
0x180052f34  lea     rcx, [rsp+488h+String2]; unsigned __int16 *
0x180052f39  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x180052f3e  mov     ebx, eax
0x180052f40  jmp     short loc_180052F47
0x180052f42  mov     ebx, 80004005h
0x180052f47  inc     esi
0x180052f49  mov     eax, ebx
0x180052f4b  cmp     esi, 6
0x180052f4e  jb      loc_180052E99
0x180052f54  test    eax, eax
0x180052f56  js      short loc_180052F62
0x180052f58  test    dil, dil
0x180052f5b  jnz     short loc_180052F62
0x180052f5d  mov     ebx, 80004005h
0x180052f62  mov     eax, ebx
0x180052f64  mov     rcx, [rsp+488h+var_38]
0x180052f6c  xor     rcx, rsp; StackCookie
0x180052f6f  call    __security_check_cookie
0x180052f74  mov     rbx, [rsp+488h+arg_0]
0x180052f7c  add     rsp, 460h
0x180052f83  pop     r15
0x180052f85  pop     r14
0x180052f87  pop     rdi
0x180052f88  pop     rsi
0x180052f89  pop     rbp
0x180052f8a  retn
```
