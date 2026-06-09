# DropInRenCallback

- ea: `0x180010da0`
- end: `0x180010f7f`
- name: `DropInRenCallback`
- size: `479`
- prototype: `__int64 __fastcall(PSTR pszDst, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callees

- `0x180010d20`
- `0x180010da0`
- `0x180036f50`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x180010ea1`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180010ea1`
- `SHLWAPI!PathSkipRootW` at `0x180010e2d`
- `SHLWAPI!PathSkipRootW` at `0x180010e49`
- `SHLWAPI!PathSkipRootW` at `0x180010e2d`
- `SHLWAPI!PathSkipRootW` at `0x180010e49`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180010deb`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180010deb`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180010f4d`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180010f4d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180010f0c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180010f0c`

## pseudocode

```c
__int64 __fastcall DropInRenCallback(PSTR pszDst, unsigned __int16 *a2)
{
  WCHAR v4; // cx
  WCHAR *v5; // rax
  LPWSTR v6; // rax
  unsigned __int16 *v7; // rbx
  WCHAR *v8; // r15
  LPWSTR v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  WCHAR *v13; // rax
  WCHAR *v14; // rcx
  __int64 v15; // rdx
  WCHAR *v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rax
  WCHAR v19; // cx
  WCHAR *v20; // rax
  WCHAR pwszDst[264]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pwszSrc[264]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR pszPath[264]; // [rsp+440h] [rbp+340h] BYREF

  SHAnsiToUnicode(pszDst + 272, pwszDst, 260);
  v4 = pwszDst[0];
  if ( pwszDst[0] )
  {
    v5 = pwszDst;
    do
    {
      if ( v4 == 47 )
        *v5 = 92;
      v4 = *++v5;
    }
    while ( *v5 );
  }
  PathFixSeparators(a2);
  v6 = PathSkipRootW(pwszDst);
  v7 = a2 + 260;
  v8 = pwszDst;
  if ( v6 )
    v8 = v6;
  v9 = PathSkipRootW(a2 + 260);
  v10 = 2147483646;
  v11 = 260;
  v12 = 2147483646;
  if ( v9 )
    v7 = v9;
  v13 = pszPath;
  do
  {
    if ( !v12 )
      break;
    if ( !*v7 )
      break;
    *v13++ = *v7++;
    --v12;
    --v11;
  }
  while ( v11 );
  v14 = v13 - 1;
  if ( v11 )
    v14 = v13;
  *v14 = 0;
  if ( PathRemoveFileSpecW(pszPath) )
  {
    v15 = 260;
    v16 = pwszSrc;
    do
    {
      if ( !v10 )
        break;
      if ( !*a2 )
        break;
      *v16++ = *a2++;
      --v10;
      --v15;
    }
    while ( v15 );
    v17 = v16 - 1;
    if ( v15 )
      v17 = v16;
    v18 = -1;
    *v17 = 0;
    do
      ++v18;
    while ( pszPath[v18] );
    PathCchAppend(pwszSrc, 0x104u, &v8[v18]);
    v19 = pwszSrc[0];
    if ( pwszSrc[0] )
    {
      v20 = pwszSrc;
      do
      {
        if ( v19 == 92 )
          *v20 = 47;
        v19 = *++v20;
      }
      while ( *v20 );
    }
    SHUnicodeToAnsi(pwszSrc, pszDst, 260);
  }
  return 0;
}

```

## disassembly

```asm
0x180010da0  mov     [rsp-8+arg_10], rbx
0x180010da5  push    rbp
0x180010da6  push    rsi
0x180010da7  push    rdi
0x180010da8  push    r12
0x180010daa  push    r13
0x180010dac  push    r14
0x180010dae  push    r15
0x180010db0  lea     rbp, [rsp-560h]
0x180010db8  sub     rsp, 660h
0x180010dbf  mov     rax, cs:__security_cookie
0x180010dc6  xor     rax, rsp
0x180010dc9  mov     [rbp+590h+var_40], rax
0x180010dd0  mov     rdi, rdx
0x180010dd3  mov     r14, rcx
0x180010dd6  mov     r13d, 104h
0x180010ddc  lea     rdx, [rsp+690h+pwszDst]; pwszDst
0x180010de1  mov     r8d, r13d; cwchBuf
0x180010de4  add     rcx, 110h; pszSrc
0x180010deb  call    cs:__imp_SHAnsiToUnicode
0x180010df1  movzx   ecx, [rsp+690h+pwszDst]
0x180010df6  xor     r12d, r12d
0x180010df9  mov     r8d, 2Fh ; '/'
0x180010dff  test    cx, cx
0x180010e02  jz      short loc_180010E20
0x180010e04  lea     rax, [rsp+690h+pwszDst]
0x180010e09  cmp     cx, r8w
0x180010e0d  jnz     short loc_180010E14
0x180010e0f  mov     word ptr [rax], 5Ch ; '\'
0x180010e14  add     rax, 2
0x180010e18  movzx   ecx, word ptr [rax]
0x180010e1b  test    cx, cx
0x180010e1e  jnz     short loc_180010E09
0x180010e20  mov     rcx, rdi; unsigned __int16 *
0x180010e23  call    ?PathFixSeparators@@YAXPEAG@Z; PathFixSeparators(ushort *)
0x180010e28  lea     rcx, [rsp+690h+pwszDst]; pszPath
0x180010e2d  call    cs:__imp_PathSkipRootW
0x180010e33  test    rax, rax
0x180010e36  lea     rbx, [rdi+208h]
0x180010e3d  lea     r15, [rsp+690h+pwszDst]
0x180010e42  mov     rcx, rbx; pszPath
0x180010e45  cmovnz  r15, rax
0x180010e49  call    cs:__imp_PathSkipRootW
0x180010e4f  mov     esi, 7FFFFFFEh
0x180010e54  mov     rdx, r13
0x180010e57  test    rax, rax
0x180010e5a  mov     ecx, esi
0x180010e5c  cmovnz  rbx, rax
0x180010e60  lea     rax, [rbp+590h+pszPath]
0x180010e67  test    rcx, rcx
0x180010e6a  jz      short loc_180010E8B
0x180010e6c  movzx   r8d, word ptr [rbx]
0x180010e70  test    r8w, r8w
0x180010e74  jz      short loc_180010E8B
0x180010e76  mov     [rax], r8w
0x180010e7a  add     rbx, 2
0x180010e7e  add     rax, 2
0x180010e82  dec     rcx
0x180010e85  sub     rdx, 1
0x180010e89  jnz     short loc_180010E67
0x180010e8b  test    rdx, rdx
0x180010e8e  lea     rcx, [rax-2]
0x180010e92  cmovnz  rcx, rax
0x180010e96  mov     [rcx], r12w
0x180010e9a  lea     rcx, [rbp+590h+pszPath]; pszPath
0x180010ea1  call    cs:__imp_PathRemoveFileSpecW
0x180010ea7  test    eax, eax
0x180010ea9  jz      loc_180010F53
0x180010eaf  mov     rdx, r13
0x180010eb2  lea     rax, [rbp+590h+pwszSrc]
0x180010eb9  test    rsi, rsi
0x180010ebc  jz      short loc_180010EDA
0x180010ebe  movzx   ecx, word ptr [rdi]
0x180010ec1  test    cx, cx
0x180010ec4  jz      short loc_180010EDA
0x180010ec6  mov     [rax], cx
0x180010ec9  add     rdi, 2
0x180010ecd  add     rax, 2
0x180010ed1  dec     rsi
0x180010ed4  sub     rdx, 1
0x180010ed8  jnz     short loc_180010EB9
0x180010eda  test    rdx, rdx
0x180010edd  lea     rcx, [rax-2]
0x180010ee1  cmovnz  rcx, rax
0x180010ee5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010ee9  mov     [rcx], r12w
0x180010eed  lea     rcx, [rbp+590h+pszPath]
0x180010ef4  inc     rax
0x180010ef7  cmp     [rcx+rax*2], r12w
0x180010efc  jnz     short loc_180010EF4
0x180010efe  lea     r8, [r15+rax*2]; pszMore
0x180010f02  mov     rdx, r13; cchPath
0x180010f05  lea     rcx, [rbp+590h+pwszSrc]; pszPath
0x180010f0c  call    cs:__imp_PathCchAppend
0x180010f12  movzx   ecx, [rbp+590h+pwszSrc]
0x180010f19  test    cx, cx
0x180010f1c  jz      short loc_180010F40
0x180010f1e  lea     rax, [rbp+590h+pwszSrc]
0x180010f25  mov     edx, 5Ch ; '\'
0x180010f2a  cmp     cx, dx
0x180010f2d  jnz     short loc_180010F34
0x180010f2f  mov     word ptr [rax], 2Fh ; '/'
0x180010f34  add     rax, 2
0x180010f38  movzx   ecx, word ptr [rax]
0x180010f3b  test    cx, cx
0x180010f3e  jnz     short loc_180010F2A
0x180010f40  mov     r8d, r13d; cchBuf
0x180010f43  lea     rcx, [rbp+590h+pwszSrc]; pwszSrc
0x180010f4a  mov     rdx, r14; pszDst
0x180010f4d  call    cs:__imp_SHUnicodeToAnsi
0x180010f53  xor     eax, eax
0x180010f55  mov     rcx, [rbp+590h+var_40]
0x180010f5c  xor     rcx, rsp; StackCookie
0x180010f5f  call    __security_check_cookie
0x180010f64  mov     rbx, [rsp+690h+arg_10]
0x180010f6c  add     rsp, 660h
0x180010f73  pop     r15
0x180010f75  pop     r14
0x180010f77  pop     r13
0x180010f79  pop     r12
0x180010f7b  pop     rdi
0x180010f7c  pop     rsi
0x180010f7d  pop     rbp
0x180010f7e  retn
```
