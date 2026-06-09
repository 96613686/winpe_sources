# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180029ac0`
- end: `0x180029c17`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800257c8`
- `0x18002a25c`
- `0x18002a62c`
- `0x18002c110`

## callees

- `0x180029ac0`
- `0x18002c1a4`

## import_xrefs

- `USER32!CharNextW` at `0x180029af9`
- `USER32!CharNextW` at `0x180029b12`
- `USER32!CharNextW` at `0x180029b2a`
- `USER32!CharNextW` at `0x180029b39`
- `USER32!CharNextW` at `0x180029b91`
- `USER32!CharNextW` at `0x180029bc0`
- `USER32!CharNextW` at `0x180029af9`
- `USER32!CharNextW` at `0x180029b12`
- `USER32!CharNextW` at `0x180029b2a`
- `USER32!CharNextW` at `0x180029b39`
- `USER32!CharNextW` at `0x180029b91`
- `USER32!CharNextW` at `0x180029bc0`

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
0x180029ac0  push    rbx
0x180029ac2  push    rbp
0x180029ac3  push    rsi
0x180029ac4  push    rdi
0x180029ac5  push    r14
0x180029ac7  sub     rsp, 20h
0x180029acb  mov     rbx, rdx
0x180029ace  mov     rdi, rcx
0x180029ad1  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180029ad6  mov     rcx, [rdi]; lpsz
0x180029ad9  xor     eax, eax
0x180029adb  cmp     ax, [rcx]
0x180029ade  jz      loc_180029C07
0x180029ae4  lea     r14d, [rax+27h]
0x180029ae8  lea     rbp, [rbx+2000h]
0x180029aef  cmp     r14w, [rcx]
0x180029af3  jnz     loc_180029B9C
0x180029af9  call    cs:__imp_CharNextW
0x180029aff  mov     [rdi], rax
0x180029b02  mov     rcx, [rdi]; lpsz
0x180029b05  xor     eax, eax
0x180029b07  cmp     ax, [rcx]
0x180029b0a  jz      short loc_180029B78
0x180029b0c  cmp     r14w, [rcx]
0x180029b10  jnz     short loc_180029B1E
0x180029b12  call    cs:__imp_CharNextW
0x180029b18  cmp     r14w, [rax]
0x180029b1c  jnz     short loc_180029B78
0x180029b1e  mov     rsi, [rdi]
0x180029b21  cmp     r14w, [rsi]
0x180029b25  jnz     short loc_180029B36
0x180029b27  mov     rcx, rsi; lpsz
0x180029b2a  call    cs:__imp_CharNextW
0x180029b30  mov     rsi, rax
0x180029b33  mov     [rdi], rax
0x180029b36  mov     rcx, rsi; lpsz
0x180029b39  call    cs:__imp_CharNextW
0x180029b3f  mov     rdx, rax
0x180029b42  mov     [rdi], rax
0x180029b45  sub     rdx, rsi
0x180029b48  sar     rdx, 1
0x180029b4b  lea     rcx, [rdx+1]
0x180029b4f  lea     rcx, [rbx+rcx*2]
0x180029b53  cmp     rcx, rbp
0x180029b56  jnb     loc_180029C07
0x180029b5c  xor     ecx, ecx
0x180029b5e  test    edx, edx
0x180029b60  jle     short loc_180029B02
0x180029b62  movzx   eax, word ptr [rsi]
0x180029b65  inc     ecx
0x180029b67  mov     [rbx], ax
0x180029b6a  lea     rsi, [rsi+2]
0x180029b6e  add     rbx, 2
0x180029b72  cmp     ecx, edx
0x180029b74  jl      short loc_180029B62
0x180029b76  jmp     short loc_180029B02
0x180029b78  mov     rcx, [rdi]
0x180029b7b  xor     eax, eax
0x180029b7d  cmp     ax, [rcx]
0x180029b80  jz      loc_180029C07
0x180029b86  cmp     rbx, rbp
0x180029b89  jnb     short loc_180029C07
0x180029b8b  mov     [rbx], ax
0x180029b8e  mov     rcx, [rdi]; lpsz
0x180029b91  call    cs:__imp_CharNextW
0x180029b97  mov     [rdi], rax
0x180029b9a  jmp     short loc_180029C03
0x180029b9c  mov     rsi, [rdi]
0x180029b9f  xor     eax, eax
0x180029ba1  cmp     ax, [rsi]
0x180029ba4  jz      short loc_180029BFB
0x180029ba6  movzx   ecx, word ptr [rsi]
0x180029ba9  sub     ecx, 9
0x180029bac  jz      short loc_180029BFB
0x180029bae  sub     ecx, 1
0x180029bb1  jz      short loc_180029BFB
0x180029bb3  sub     ecx, 3
0x180029bb6  jz      short loc_180029BFB
0x180029bb8  cmp     ecx, 13h
0x180029bbb  jz      short loc_180029BFB
0x180029bbd  mov     rcx, rsi; lpsz
0x180029bc0  call    cs:__imp_CharNextW
0x180029bc6  mov     rdx, rax
0x180029bc9  mov     [rdi], rax
0x180029bcc  sub     rdx, rsi
0x180029bcf  sar     rdx, 1
0x180029bd2  lea     rcx, [rdx+1]
0x180029bd6  lea     rcx, [rbx+rcx*2]
0x180029bda  cmp     rcx, rbp
0x180029bdd  jnb     short loc_180029C07
0x180029bdf  xor     ecx, ecx
0x180029be1  test    edx, edx
0x180029be3  jle     short loc_180029B9C
0x180029be5  movzx   eax, word ptr [rsi]
0x180029be8  inc     ecx
0x180029bea  mov     [rbx], ax
0x180029bed  lea     rsi, [rsi+2]
0x180029bf1  add     rbx, 2
0x180029bf5  cmp     ecx, edx
0x180029bf7  jl      short loc_180029BE5
0x180029bf9  jmp     short loc_180029B9C
0x180029bfb  cmp     rbx, rbp
0x180029bfe  jnb     short loc_180029C07
0x180029c00  mov     [rbx], ax
0x180029c03  xor     eax, eax
0x180029c05  jmp     short loc_180029C0C
0x180029c07  mov     eax, 80020009h
0x180029c0c  add     rsp, 20h
0x180029c10  pop     r14
0x180029c12  pop     rdi
0x180029c13  pop     rsi
0x180029c14  pop     rbp
0x180029c15  pop     rbx
0x180029c16  retn
```
