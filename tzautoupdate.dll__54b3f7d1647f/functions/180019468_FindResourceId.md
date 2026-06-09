# FindResourceId

- ea: `0x180019468`
- end: `0x180019531`
- name: `FindResourceId`
- size: `201`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019758`

## callees

- `0x180017d24`
- `0x180019468`
- `0x18001b150`

## import_xrefs

- `msvcrt!_wtoi` at `0x180019502`
- `msvcrt!_wtoi` at `0x180019502`
- `msvcrt!wcschr` at `0x1800194bc`
- `msvcrt!wcschr` at `0x1800194bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800194f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800194f3`

## string_xrefs

- `0x1800194df`: `@tzres.dll,`

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
0x180019468  mov     [rsp+arg_10], rbx
0x18001946d  mov     [rsp+arg_18], rsi
0x180019472  push    rdi
0x180019473  sub     rsp, 60h
0x180019477  mov     rax, cs:__security_cookie
0x18001947e  xor     rax, rsp
0x180019481  mov     [rsp+68h+var_10], rax
0x180019486  xor     eax, eax
0x180019488  mov     rsi, rdx
0x18001948b  xorps   xmm0, xmm0
0x18001948e  mov     [rsp+68h+var_18], eax
0x180019492  mov     r8, rcx; pszSrc
0x180019495  lea     rcx, [rsp+68h+pszDest]; pszDest
0x18001949a  movups  xmmword ptr [rsp+68h+pszDest], xmm0
0x18001949f  lea     edx, [rax+12h]; cchDest
0x1800194a2  movups  [rsp+68h+var_28], xmm0
0x1800194a7  call    StringCchCopyW
0x1800194ac  mov     ebx, eax
0x1800194ae  test    eax, eax
0x1800194b0  js      short loc_180019510
0x1800194b2  mov     edx, 2Dh ; '-'; Ch
0x1800194b7  lea     rcx, [rsp+68h+pszDest]; Str
0x1800194bc  call    cs:__imp_wcschr
0x1800194c2  mov     rdi, rax
0x1800194c5  mov     ebx, 80004005h
0x1800194ca  test    rax, rax
0x1800194cd  jz      short loc_180019510
0x1800194cf  xor     ecx, ecx
0x1800194d1  lea     r8, [rsp+68h+pszDest]; lpString1
0x1800194d6  mov     [rax], cx
0x1800194d9  xor     edx, edx; dwCmpFlags
0x1800194db  or      r9d, 0FFFFFFFFh; cchCount1
0x1800194df  lea     rax, aTzresDll; "@tzres.dll,"
0x1800194e6  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x1800194eb  mov     [rsp+68h+lpString2], rax; lpString2
0x1800194f0  lea     ecx, [rdx+7Fh]; Locale
0x1800194f3  call    cs:__imp_CompareStringW
0x1800194f9  cmp     eax, 2
0x1800194fc  jnz     short loc_180019510
0x1800194fe  lea     rcx, [rdi+2]; String
0x180019502  call    cs:__imp__wtoi
0x180019508  test    eax, eax
0x18001950a  jz      short loc_180019510
0x18001950c  mov     [rsi], eax
0x18001950e  xor     ebx, ebx
0x180019510  mov     eax, ebx
0x180019512  mov     rcx, [rsp+68h+var_10]
0x180019517  xor     rcx, rsp; StackCookie
0x18001951a  call    __security_check_cookie
0x18001951f  lea     r11, [rsp+68h+var_8]
0x180019524  mov     rbx, [r11+20h]
0x180019528  mov     rsi, [r11+28h]
0x18001952c  mov     rsp, r11
0x18001952f  pop     rdi
0x180019530  retn
```
