# IsValidZipItemPath(ushort const *)

- ea: `0x1800106c0`
- end: `0x180010823`
- name: `?IsValidZipItemPath@@YAHPEBG@Z`
- size: `355`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x18000f990`
- `0x18003fde0`

## callees

- `0x1800106c0`
- `0x180036f50`

## import_xrefs

- `SHLWAPI!PathCanonicalizeW` at `0x1800107ff`
- `SHLWAPI!PathCanonicalizeW` at `0x1800107ff`
- `SHLWAPI!PathIsRelativeW` at `0x1800107e8`
- `SHLWAPI!PathIsRelativeW` at `0x1800107e8`
- `SHLWAPI!__imp_PathIsValidCharW` at `0x18001078c`
- `SHLWAPI!__imp_PathIsValidCharW` at `0x18001078c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001079e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001079e`
- `KERNEL32!lstrcmpW` at `0x180010816`
- `KERNEL32!lstrcmpW` at `0x180010816`

## pseudocode

```c
__int64 __fastcall IsValidZipItemPath(WCHAR *a1)
{
  unsigned int v1; // esi
  WCHAR *v2; // r9
  __int64 v3; // rax
  __int64 v4; // r8
  WCHAR *v5; // rcx
  __int64 result; // rax
  WCHAR v7; // cx
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  int v10; // ebx
  int IsValidCharW; // eax
  int v12; // edx
  WCHAR sz[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR pszBuf[264]; // [rsp+230h] [rbp-228h] BYREF

  v1 = 0;
  v2 = sz;
  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*a1 )
      break;
    *v2++ = *a1++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = v2 - 1;
  if ( v4 )
    v5 = v2;
  result = 0;
  *v5 = 0;
  if ( v4 )
  {
    v7 = sz[0];
    if ( sz[0] )
    {
      v8 = sz;
      do
      {
        if ( v7 == 47 )
          *v8 = 92;
        v7 = v8[1];
        ++v8;
      }
      while ( v7 );
      v7 = sz[0];
    }
    v9 = sz;
    v10 = 1;
    if ( v7 )
    {
      while ( v10 )
      {
        IsValidCharW = PathIsValidCharW(*v9, 1020);
        v12 = 0;
        if ( IsValidCharW )
          v12 = v10;
        v10 = v12;
        v9 = CharNextW(v9);
        if ( !*v9 )
        {
          if ( v10 )
            goto LABEL_22;
          return v1;
        }
      }
    }
    else
    {
LABEL_22:
      if ( PathIsRelativeW(sz) && PathCanonicalizeW(pszBuf, sz) && !lstrcmpW(pszBuf, sz) )
        return 1;
    }
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800106c0  push    rsi
0x1800106c2  sub     rsp, 450h
0x1800106c9  mov     rax, cs:__security_cookie
0x1800106d0  xor     rax, rsp
0x1800106d3  mov     [rsp+458h+var_18], rax
0x1800106db  xor     esi, esi
0x1800106dd  lea     r9, [rsp+458h+sz]
0x1800106e2  mov     eax, 7FFFFFFEh
0x1800106e7  mov     r8d, 104h
0x1800106ed  nop     dword ptr [rax]
0x1800106f0  test    rax, rax
0x1800106f3  jz      short loc_180010712
0x1800106f5  movzx   edx, word ptr [rcx]
0x1800106f8  test    dx, dx
0x1800106fb  jz      short loc_180010712
0x1800106fd  mov     [r9], dx
0x180010701  add     rcx, 2
0x180010705  add     r9, 2
0x180010709  dec     rax
0x18001070c  sub     r8, 1
0x180010710  jnz     short loc_1800106F0
0x180010712  test    r8, r8
0x180010715  lea     rcx, [r9-2]
0x180010719  cmovnz  rcx, r9
0x18001071d  xor     eax, eax
0x18001071f  mov     [rcx], ax
0x180010722  test    r8, r8
0x180010725  jz      loc_1800107CA
0x18001072b  movzx   ecx, [rsp+458h+sz]
0x180010730  mov     [rsp+458h+arg_0], rbx
0x180010738  mov     [rsp+458h+arg_8], rbp
0x180010740  mov     [rsp+458h+arg_10], rdi
0x180010748  test    cx, cx
0x18001074b  jz      short loc_18001076F
0x18001074d  lea     rax, [rsp+458h+sz]
0x180010752  cmp     cx, 2Fh ; '/'
0x180010756  jnz     short loc_18001075D
0x180010758  mov     word ptr [rax], 5Ch ; '\'
0x18001075d  movzx   ecx, word ptr [rax+2]
0x180010761  add     rax, 2
0x180010765  test    cx, cx
0x180010768  jnz     short loc_180010752
0x18001076a  movzx   ecx, [rsp+458h+sz]
0x18001076f  lea     rdi, [rsp+458h+sz]
0x180010774  mov     ebp, 1
0x180010779  mov     ebx, ebp
0x18001077b  test    cx, cx
0x18001077e  jz      short loc_1800107E3
0x180010780  test    ebx, ebx
0x180010782  jz      short loc_1800107B0
0x180010784  movzx   ecx, word ptr [rdi]
0x180010787  mov     edx, 3FCh
0x18001078c  call    cs:__imp_PathIsValidCharW
0x180010792  xor     edx, edx
0x180010794  mov     rcx, rdi; lpsz
0x180010797  test    eax, eax
0x180010799  cmovnz  edx, ebx
0x18001079c  mov     ebx, edx
0x18001079e  call    cs:__imp_CharNextW
0x1800107a4  mov     rdi, rax
0x1800107a7  cmp     [rax], si
0x1800107aa  jnz     short loc_180010780
0x1800107ac  test    ebx, ebx
0x1800107ae  jnz     short loc_1800107E3
0x1800107b0  mov     rbp, [rsp+458h+arg_8]
0x1800107b8  mov     eax, esi
0x1800107ba  mov     rbx, [rsp+458h+arg_0]
0x1800107c2  mov     rdi, [rsp+458h+arg_10]
0x1800107ca  mov     rcx, [rsp+458h+var_18]
0x1800107d2  xor     rcx, rsp; StackCookie
0x1800107d5  call    __security_check_cookie
0x1800107da  add     rsp, 450h
0x1800107e1  pop     rsi
0x1800107e2  retn
0x1800107e3  lea     rcx, [rsp+458h+sz]; pszPath
0x1800107e8  call    cs:__imp_PathIsRelativeW
0x1800107ee  test    eax, eax
0x1800107f0  jz      short loc_1800107B0
0x1800107f2  lea     rdx, [rsp+458h+sz]; pszPath
0x1800107f7  lea     rcx, [rsp+458h+pszBuf]; pszBuf
0x1800107ff  call    cs:__imp_PathCanonicalizeW
0x180010805  test    eax, eax
0x180010807  jz      short loc_1800107B0
0x180010809  lea     rdx, [rsp+458h+sz]; lpString2
0x18001080e  lea     rcx, [rsp+458h+pszBuf]; lpString1
0x180010816  call    cs:__imp_lstrcmpW
0x18001081c  test    eax, eax
0x18001081e  cmovz   esi, ebp
0x180010821  jmp     short loc_1800107B0
```
