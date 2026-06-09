# CThemeManager2::_GetInboxThemePath(tagTHEMECAT,ushort const *,ushort * *)

- ea: `0x180055d7c`
- end: `0x180055e2f`
- name: `?_GetInboxThemePath@CThemeManager2@@AEAAJW4tagTHEMECAT@@PEBGPEAPEAG@Z`
- size: `179`
- prototype: `int __high(enum tagTHEMECAT, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x180054390`

## callees

- `0x18000ab10`
- `0x18000ed70`
- `0x1800358c0`
- `0x180055d7c`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180055e08`
- `SHCORE!SHStrDupW` at `0x180055e08`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180055ddf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180055ddf`

## string_xrefs

- `0x180055db9`: `%windir%\Resources\Ease of Access Themes\`

## pseudocode

```c
int __fastcall CThemeManager2::_GetInboxThemePath(__int64 a1, int a2, __int64 a3, LPWSTR *a4)
{
  const unsigned __int16 *v5; // r8
  int result; // eax
  const WCHAR *v7; // r10
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( a2 == 1 )
  {
    v5 = L"%windir%\\Resources\\Themes\\";
  }
  else
  {
    result = -2147467259;
    if ( a2 != 3 )
      return result;
    v5 = L"%windir%\\Resources\\Ease of Access Themes\\";
  }
  result = StringCchCopyW(pszPath, 0x104u, v5);
  if ( result >= 0 )
  {
    result = PathCchAppend(pszPath, 0x104u, v7);
    if ( result >= 0 )
    {
      result = StringCchCatW(pszPath, 0x104u, L".theme");
      if ( result >= 0 )
        return SHStrDupW(pszPath, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055d7c  mov     [rsp+arg_0], rbx
0x180055d81  push    rdi
0x180055d82  sub     rsp, 240h
0x180055d89  mov     rax, cs:__security_cookie
0x180055d90  xor     rax, rsp
0x180055d93  mov     [rsp+248h+var_18], rax
0x180055d9b  mov     rdi, r9
0x180055d9e  mov     r10, r8
0x180055da1  cmp     edx, 1
0x180055da4  jnz     short loc_180055DAF
0x180055da6  lea     r8, aWindirResource_14; "%windir%\\Resources\\Themes\\"
0x180055dad  jmp     short loc_180055DC0
0x180055daf  mov     eax, 80004005h
0x180055db4  cmp     edx, 3
0x180055db7  jnz     short loc_180055E0E
0x180055db9  lea     r8, aWindirResource; "%windir%\\Resources\\Ease of Access The"...
0x180055dc0  mov     ebx, 104h
0x180055dc5  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180055dca  mov     edx, ebx; unsigned __int64
0x180055dcc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180055dd1  test    eax, eax
0x180055dd3  js      short loc_180055E0E
0x180055dd5  mov     r8, r10; pszMore
0x180055dd8  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180055ddd  mov     edx, ebx; cchPath
0x180055ddf  call    cs:__imp_PathCchAppend
0x180055de5  test    eax, eax
0x180055de7  js      short loc_180055E0E
0x180055de9  lea     r8, aTheme; ".theme"
0x180055df0  mov     edx, ebx; unsigned __int64
0x180055df2  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180055df7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180055dfc  test    eax, eax
0x180055dfe  js      short loc_180055E0E
0x180055e00  mov     rdx, rdi; ppwsz
0x180055e03  lea     rcx, [rsp+248h+pszPath]; psz
0x180055e08  call    cs:__imp_SHStrDupW
0x180055e0e  mov     rcx, [rsp+248h+var_18]
0x180055e16  xor     rcx, rsp; StackCookie
0x180055e19  call    __security_check_cookie
0x180055e1e  mov     rbx, [rsp+248h+arg_0]
0x180055e26  add     rsp, 240h
0x180055e2d  pop     rdi
0x180055e2e  retn
```
