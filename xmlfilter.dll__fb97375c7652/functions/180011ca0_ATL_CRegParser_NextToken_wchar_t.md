# ATL::CRegParser::NextToken(wchar_t *)

- ea: `0x180011ca0`
- end: `0x180011e37`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010410`
- `0x180012378`
- `0x1800126ec`
- `0x1800130bc`

## callees

- `0x180011ca0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011cd5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d03`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d23`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d3b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d4a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011db5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011dda`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011cd5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d03`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d23`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d3b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d4a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011db5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011dda`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, wchar_t *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  wchar_t *v6; // rbp
  LPWSTR v7; // rax
  const WCHAR *v8; // rcx
  __int16 v9; // dx
  const WCHAR *v10; // rsi
  LPWSTR v11; // rax
  __int64 v12; // rdx
  int j; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  LPWSTR v18; // rax
  __int64 v19; // rdx
  int i; // ecx

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextW(*this);
  }
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    while ( 1 )
    {
      v15 = v5 - 9;
      if ( !v15 )
        break;
      v16 = v15 - 1;
      if ( !v16 )
        break;
      v17 = v16 - 3;
      if ( !v17 || v17 == 19 )
        break;
      v18 = CharNextW(v4);
      *this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < (int)v19; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *this;
      if ( !**this )
        break;
      v5 = *v4;
    }
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  v9 = *v7;
  if ( *v7 )
  {
    while ( v9 != 39 || *CharNextW(v8) == 39 )
    {
      v10 = *this;
      if ( **this == 39 )
      {
        v10 = CharNextW(*this);
        *this = v10;
      }
      v11 = CharNextW(v10);
      *this = v11;
      v12 = v11 - v10;
      if ( &a2[v12 + 1] < v6 )
      {
        for ( j = 0; j < (int)v12; ++a2 )
        {
          ++j;
          *a2 = *v10++;
        }
        v8 = *this;
        v9 = **this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x180011ca0  push    rbx
0x180011ca2  push    rbp
0x180011ca3  push    rsi
0x180011ca4  push    rdi
0x180011ca5  push    r14
0x180011ca7  sub     rsp, 20h
0x180011cab  mov     rbx, rdx
0x180011cae  mov     rdi, rcx
0x180011cb1  mov     rsi, [rdi]
0x180011cb4  movzx   ecx, word ptr [rsi]
0x180011cb7  mov     r8d, ecx
0x180011cba  sub     r8d, 9
0x180011cbe  jz      short loc_180011CD2
0x180011cc0  sub     r8d, 1
0x180011cc4  jz      short loc_180011CD2
0x180011cc6  sub     r8d, 3
0x180011cca  jz      short loc_180011CD2
0x180011ccc  cmp     r8d, 13h
0x180011cd0  jnz     short loc_180011CE0
0x180011cd2  mov     rcx, rsi; lpsz
0x180011cd5  call    cs:__imp_CharNextW
0x180011cdb  mov     [rdi], rax
0x180011cde  jmp     short loc_180011CB1
0x180011ce0  xor     eax, eax
0x180011ce2  cmp     ax, cx
0x180011ce5  jz      loc_180011D90
0x180011ceb  lea     r14d, [rax+27h]
0x180011cef  lea     rbp, [rbx+2000h]
0x180011cf6  cmp     r14w, cx
0x180011cfa  jnz     loc_180011DC0
0x180011d00  mov     rcx, rsi; lpsz
0x180011d03  call    cs:__imp_CharNextW
0x180011d09  mov     [rdi], rax
0x180011d0c  mov     rcx, rax; lpsz
0x180011d0f  movzx   edx, word ptr [rax]
0x180011d12  xor     eax, eax
0x180011d14  cmp     ax, dx
0x180011d17  jz      loc_180011DA0
0x180011d1d  cmp     r14w, dx
0x180011d21  jnz     short loc_180011D2F
0x180011d23  call    cs:__imp_CharNextW
0x180011d29  cmp     r14w, [rax]
0x180011d2d  jnz     short loc_180011DA0
0x180011d2f  mov     rsi, [rdi]
0x180011d32  cmp     r14w, [rsi]
0x180011d36  jnz     short loc_180011D47
0x180011d38  mov     rcx, rsi; lpsz
0x180011d3b  call    cs:__imp_CharNextW
0x180011d41  mov     rsi, rax
0x180011d44  mov     [rdi], rax
0x180011d47  mov     rcx, rsi; lpsz
0x180011d4a  call    cs:__imp_CharNextW
0x180011d50  mov     rdx, rax
0x180011d53  mov     [rdi], rax
0x180011d56  sub     rdx, rsi
0x180011d59  sar     rdx, 1
0x180011d5c  lea     rcx, [rdx+1]
0x180011d60  lea     rcx, [rbx+rcx*2]
0x180011d64  cmp     rcx, rbp
0x180011d67  jnb     short loc_180011D90
0x180011d69  xor     ecx, ecx
0x180011d6b  test    edx, edx
0x180011d6d  jle     short loc_180011D83
0x180011d6f  movzx   eax, word ptr [rsi]
0x180011d72  inc     ecx
0x180011d74  mov     [rbx], ax
0x180011d77  lea     rsi, [rsi+2]
0x180011d7b  add     rbx, 2
0x180011d7f  cmp     ecx, edx
0x180011d81  jl      short loc_180011D6F
0x180011d83  mov     rcx, [rdi]
0x180011d86  xor     eax, eax
0x180011d88  movzx   edx, word ptr [rcx]
0x180011d8b  cmp     ax, dx
0x180011d8e  jnz     short loc_180011D1D
0x180011d90  mov     eax, 80020009h
0x180011d95  add     rsp, 20h
0x180011d99  pop     r14
0x180011d9b  pop     rdi
0x180011d9c  pop     rsi
0x180011d9d  pop     rbp
0x180011d9e  pop     rbx
0x180011d9f  retn
0x180011da0  mov     rcx, [rdi]
0x180011da3  xor     eax, eax
0x180011da5  cmp     ax, [rcx]
0x180011da8  jz      short loc_180011D90
0x180011daa  cmp     rbx, rbp
0x180011dad  jnb     short loc_180011D90
0x180011daf  mov     [rbx], ax
0x180011db2  mov     rcx, [rdi]; lpsz
0x180011db5  call    cs:__imp_CharNextW
0x180011dbb  mov     [rdi], rax
0x180011dbe  jmp     short loc_180011E30
0x180011dc0  movzx   ecx, cx
0x180011dc3  sub     ecx, 9
0x180011dc6  jz      short loc_180011E22
0x180011dc8  sub     ecx, 1
0x180011dcb  jz      short loc_180011E22
0x180011dcd  sub     ecx, 3
0x180011dd0  jz      short loc_180011E22
0x180011dd2  cmp     ecx, 13h
0x180011dd5  jz      short loc_180011E22
0x180011dd7  mov     rcx, rsi; lpsz
0x180011dda  call    cs:__imp_CharNextW
0x180011de0  mov     rdx, rax
0x180011de3  mov     [rdi], rax
0x180011de6  sub     rdx, rsi
0x180011de9  sar     rdx, 1
0x180011dec  lea     rcx, [rdx+1]
0x180011df0  lea     rcx, [rbx+rcx*2]
0x180011df4  cmp     rcx, rbp
0x180011df7  jnb     short loc_180011D90
0x180011df9  xor     ecx, ecx
0x180011dfb  test    edx, edx
0x180011dfd  jle     short loc_180011E13
0x180011dff  movzx   eax, word ptr [rsi]
0x180011e02  inc     ecx
0x180011e04  mov     [rbx], ax
0x180011e07  lea     rsi, [rsi+2]
0x180011e0b  add     rbx, 2
0x180011e0f  cmp     ecx, edx
0x180011e11  jl      short loc_180011DFF
0x180011e13  mov     rsi, [rdi]
0x180011e16  xor     eax, eax
0x180011e18  cmp     ax, [rsi]
0x180011e1b  jz      short loc_180011E22
0x180011e1d  movzx   ecx, word ptr [rsi]
0x180011e20  jmp     short loc_180011DC0
0x180011e22  cmp     rbx, rbp
0x180011e25  jnb     loc_180011D90
0x180011e2b  xor     eax, eax
0x180011e2d  mov     [rbx], ax
0x180011e30  xor     eax, eax
0x180011e32  jmp     loc_180011D95
```
