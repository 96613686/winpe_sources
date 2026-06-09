# FindResourceId

- ea: `0x1800272f8`
- end: `0x1800273c1`
- name: `FindResourceId`
- size: `201`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800275e8`

## callees

- `0x180024910`
- `0x1800272f8`
- `0x180028f60`

## import_xrefs

- `msvcrt!_wtoi` at `0x180027392`
- `msvcrt!_wtoi` at `0x180027392`
- `msvcrt!wcschr` at `0x18002734c`
- `msvcrt!wcschr` at `0x18002734c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027383`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027383`

## string_xrefs

- `0x18002736f`: `@tzres.dll,`

## pseudocode

```c
__int64 __fastcall FindResourceId(STRSAFE_LPCWSTR pszSrc, int *a2)
{
  HRESULT v3; // ebx
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  int v6; // eax
  wchar_t pszDest[8]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h]
  int v10; // [rsp+50h] [rbp-18h]

  v10 = 0;
  *(_OWORD *)pszDest = 0;
  v9 = 0;
  v3 = StringCchCopyW(pszDest, 0x12u, pszSrc);
  if ( v3 >= 0 )
  {
    v4 = wcschr(pszDest, 0x2Du);
    v5 = v4;
    v3 = -2147467259;
    if ( v4 )
    {
      *v4 = 0;
      if ( CompareStringW(0x7Fu, 0, pszDest, -1, L"@tzres.dll,", -1) == 2 )
      {
        v6 = _wtoi(v5 + 1);
        if ( v6 )
        {
          *a2 = v6;
          return 0;
        }
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800272f8  mov     [rsp+arg_10], rbx
0x1800272fd  mov     [rsp+arg_18], rsi
0x180027302  push    rdi
0x180027303  sub     rsp, 60h
0x180027307  mov     rax, cs:__security_cookie
0x18002730e  xor     rax, rsp
0x180027311  mov     [rsp+68h+var_10], rax
0x180027316  xor     eax, eax
0x180027318  mov     rsi, rdx
0x18002731b  xorps   xmm0, xmm0
0x18002731e  mov     [rsp+68h+var_18], eax
0x180027322  mov     r8, rcx; pszSrc
0x180027325  lea     rcx, [rsp+68h+pszDest]; pszDest
0x18002732a  movups  xmmword ptr [rsp+68h+pszDest], xmm0
0x18002732f  lea     edx, [rax+12h]; cchDest
0x180027332  movups  [rsp+68h+var_28], xmm0
0x180027337  call    StringCchCopyW
0x18002733c  mov     ebx, eax
0x18002733e  test    eax, eax
0x180027340  js      short loc_1800273A0
0x180027342  mov     edx, 2Dh ; '-'; Ch
0x180027347  lea     rcx, [rsp+68h+pszDest]; Str
0x18002734c  call    cs:__imp_wcschr
0x180027352  mov     rdi, rax
0x180027355  mov     ebx, 80004005h
0x18002735a  test    rax, rax
0x18002735d  jz      short loc_1800273A0
0x18002735f  xor     ecx, ecx
0x180027361  lea     r8, [rsp+68h+pszDest]; lpString1
0x180027366  mov     [rax], cx
0x180027369  xor     edx, edx; dwCmpFlags
0x18002736b  or      r9d, 0FFFFFFFFh; cchCount1
0x18002736f  lea     rax, aTzresDll; "@tzres.dll,"
0x180027376  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x18002737b  mov     [rsp+68h+lpString2], rax; lpString2
0x180027380  lea     ecx, [rdx+7Fh]; Locale
0x180027383  call    cs:__imp_CompareStringW
0x180027389  cmp     eax, 2
0x18002738c  jnz     short loc_1800273A0
0x18002738e  lea     rcx, [rdi+2]; String
0x180027392  call    cs:__imp__wtoi
0x180027398  test    eax, eax
0x18002739a  jz      short loc_1800273A0
0x18002739c  mov     [rsi], eax
0x18002739e  xor     ebx, ebx
0x1800273a0  mov     eax, ebx
0x1800273a2  mov     rcx, [rsp+68h+var_10]
0x1800273a7  xor     rcx, rsp; StackCookie
0x1800273aa  call    __security_check_cookie
0x1800273af  lea     r11, [rsp+68h+var_8]
0x1800273b4  mov     rbx, [r11+20h]
0x1800273b8  mov     rsi, [r11+28h]
0x1800273bc  mov     rsp, r11
0x1800273bf  pop     rdi
0x1800273c0  retn
```
