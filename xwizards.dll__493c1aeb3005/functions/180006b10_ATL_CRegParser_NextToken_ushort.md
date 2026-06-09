# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180006b10`
- end: `0x180006c67`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b8c`
- `0x18000758c`
- `0x1800078b0`
- `0x180008488`

## callees

- `0x180006b10`
- `0x18000851c`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b49`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b62`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b7a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b89`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006be1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006c10`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b49`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b62`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b7a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b89`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006be1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006c10`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  unsigned __int16 *v11; // rsi
  LPWSTR v12; // rax
  __int64 v13; // rdx
  int j; // ecx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v6 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v6 == 39 && *CharNextW(v6) != 39 )
          break;
        v7 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v7 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v7;
        }
        v8 = CharNextW(v7);
        *(_QWORD *)this = v8;
        v9 = v8 - v7;
        if ( &a2[v9 + 1] >= v5 )
          return 2147614729LL;
        for ( i = 0; i < (int)v9; ++a2 )
        {
          ++i;
          *a2 = *v7++;
        }
      }
      if ( **(_WORD **)this && a2 < v5 )
      {
        *a2 = 0;
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
        return 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v11 = *(unsigned __int16 **)this;
        if ( !**(_WORD **)this || *v11 == 9 || *v11 == 10 || *v11 == 13 || *v11 == 32 )
          break;
        v12 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v12;
        v13 = v12 - v11;
        if ( &a2[v13 + 1] >= v5 )
          return 2147614729LL;
        for ( j = 0; j < (int)v13; ++a2 )
        {
          ++j;
          *a2 = *v11++;
        }
      }
      if ( a2 < v5 )
      {
        *a2 = 0;
        return 0;
      }
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x180006b10  push    rbx
0x180006b12  push    rbp
0x180006b13  push    rsi
0x180006b14  push    rdi
0x180006b15  push    r14
0x180006b17  sub     rsp, 20h
0x180006b1b  mov     rbx, rdx
0x180006b1e  mov     rdi, rcx
0x180006b21  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180006b26  mov     rcx, [rdi]; lpsz
0x180006b29  xor     eax, eax
0x180006b2b  cmp     ax, [rcx]
0x180006b2e  jz      loc_180006C57
0x180006b34  lea     r14d, [rax+27h]
0x180006b38  lea     rbp, [rbx+2000h]
0x180006b3f  cmp     r14w, [rcx]
0x180006b43  jnz     loc_180006BEC
0x180006b49  call    cs:__imp_CharNextW
0x180006b4f  mov     [rdi], rax
0x180006b52  mov     rcx, [rdi]; lpsz
0x180006b55  xor     eax, eax
0x180006b57  cmp     ax, [rcx]
0x180006b5a  jz      short loc_180006BC8
0x180006b5c  cmp     r14w, [rcx]
0x180006b60  jnz     short loc_180006B6E
0x180006b62  call    cs:__imp_CharNextW
0x180006b68  cmp     r14w, [rax]
0x180006b6c  jnz     short loc_180006BC8
0x180006b6e  mov     rsi, [rdi]
0x180006b71  cmp     r14w, [rsi]
0x180006b75  jnz     short loc_180006B86
0x180006b77  mov     rcx, rsi; lpsz
0x180006b7a  call    cs:__imp_CharNextW
0x180006b80  mov     rsi, rax
0x180006b83  mov     [rdi], rax
0x180006b86  mov     rcx, rsi; lpsz
0x180006b89  call    cs:__imp_CharNextW
0x180006b8f  mov     rdx, rax
0x180006b92  mov     [rdi], rax
0x180006b95  sub     rdx, rsi
0x180006b98  sar     rdx, 1
0x180006b9b  lea     rcx, [rdx+1]
0x180006b9f  lea     rcx, [rbx+rcx*2]
0x180006ba3  cmp     rcx, rbp
0x180006ba6  jnb     loc_180006C57
0x180006bac  xor     ecx, ecx
0x180006bae  test    edx, edx
0x180006bb0  jle     short loc_180006B52
0x180006bb2  movzx   eax, word ptr [rsi]
0x180006bb5  inc     ecx
0x180006bb7  mov     [rbx], ax
0x180006bba  lea     rsi, [rsi+2]
0x180006bbe  add     rbx, 2
0x180006bc2  cmp     ecx, edx
0x180006bc4  jl      short loc_180006BB2
0x180006bc6  jmp     short loc_180006B52
0x180006bc8  mov     rcx, [rdi]
0x180006bcb  xor     eax, eax
0x180006bcd  cmp     ax, [rcx]
0x180006bd0  jz      loc_180006C57
0x180006bd6  cmp     rbx, rbp
0x180006bd9  jnb     short loc_180006C57
0x180006bdb  mov     [rbx], ax
0x180006bde  mov     rcx, [rdi]; lpsz
0x180006be1  call    cs:__imp_CharNextW
0x180006be7  mov     [rdi], rax
0x180006bea  jmp     short loc_180006C53
0x180006bec  mov     rsi, [rdi]
0x180006bef  xor     eax, eax
0x180006bf1  cmp     ax, [rsi]
0x180006bf4  jz      short loc_180006C4B
0x180006bf6  movzx   ecx, word ptr [rsi]
0x180006bf9  sub     ecx, 9
0x180006bfc  jz      short loc_180006C4B
0x180006bfe  sub     ecx, 1
0x180006c01  jz      short loc_180006C4B
0x180006c03  sub     ecx, 3
0x180006c06  jz      short loc_180006C4B
0x180006c08  cmp     ecx, 13h
0x180006c0b  jz      short loc_180006C4B
0x180006c0d  mov     rcx, rsi; lpsz
0x180006c10  call    cs:__imp_CharNextW
0x180006c16  mov     rdx, rax
0x180006c19  mov     [rdi], rax
0x180006c1c  sub     rdx, rsi
0x180006c1f  sar     rdx, 1
0x180006c22  lea     rcx, [rdx+1]
0x180006c26  lea     rcx, [rbx+rcx*2]
0x180006c2a  cmp     rcx, rbp
0x180006c2d  jnb     short loc_180006C57
0x180006c2f  xor     ecx, ecx
0x180006c31  test    edx, edx
0x180006c33  jle     short loc_180006BEC
0x180006c35  movzx   eax, word ptr [rsi]
0x180006c38  inc     ecx
0x180006c3a  mov     [rbx], ax
0x180006c3d  lea     rsi, [rsi+2]
0x180006c41  add     rbx, 2
0x180006c45  cmp     ecx, edx
0x180006c47  jl      short loc_180006C35
0x180006c49  jmp     short loc_180006BEC
0x180006c4b  cmp     rbx, rbp
0x180006c4e  jnb     short loc_180006C57
0x180006c50  mov     [rbx], ax
0x180006c53  xor     eax, eax
0x180006c55  jmp     short loc_180006C5C
0x180006c57  mov     eax, 80020009h
0x180006c5c  add     rsp, 20h
0x180006c60  pop     r14
0x180006c62  pop     rdi
0x180006c63  pop     rsi
0x180006c64  pop     rbp
0x180006c65  pop     rbx
0x180006c66  retn
```
