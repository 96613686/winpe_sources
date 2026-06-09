# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180003fe0`
- end: `0x180004177`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030f4`
- `0x180004698`
- `0x1800049ec`
- `0x180005364`

## callees

- `0x180003fe0`

## import_xrefs

- `USER32!CharNextW` at `0x180004015`
- `USER32!CharNextW` at `0x180004043`
- `USER32!CharNextW` at `0x180004063`
- `USER32!CharNextW` at `0x18000407b`
- `USER32!CharNextW` at `0x18000408a`
- `USER32!CharNextW` at `0x1800040f5`
- `USER32!CharNextW` at `0x18000411a`
- `USER32!CharNextW` at `0x180004015`
- `USER32!CharNextW` at `0x180004043`
- `USER32!CharNextW` at `0x180004063`
- `USER32!CharNextW` at `0x18000407b`
- `USER32!CharNextW` at `0x18000408a`
- `USER32!CharNextW` at `0x1800040f5`
- `USER32!CharNextW` at `0x18000411a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
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
0x180003fe0  push    rbx
0x180003fe2  push    rbp
0x180003fe3  push    rsi
0x180003fe4  push    rdi
0x180003fe5  push    r14
0x180003fe7  sub     rsp, 20h
0x180003feb  mov     rbx, rdx
0x180003fee  mov     rdi, rcx
0x180003ff1  mov     rsi, [rdi]
0x180003ff4  movzx   ecx, word ptr [rsi]
0x180003ff7  mov     r8d, ecx
0x180003ffa  sub     r8d, 9
0x180003ffe  jz      short loc_180004012
0x180004000  sub     r8d, 1
0x180004004  jz      short loc_180004012
0x180004006  sub     r8d, 3
0x18000400a  jz      short loc_180004012
0x18000400c  cmp     r8d, 13h
0x180004010  jnz     short loc_180004020
0x180004012  mov     rcx, rsi; lpsz
0x180004015  call    cs:__imp_CharNextW
0x18000401b  mov     [rdi], rax
0x18000401e  jmp     short loc_180003FF1
0x180004020  xor     eax, eax
0x180004022  cmp     ax, cx
0x180004025  jz      loc_1800040D0
0x18000402b  lea     r14d, [rax+27h]
0x18000402f  lea     rbp, [rbx+2000h]
0x180004036  cmp     r14w, cx
0x18000403a  jnz     loc_180004100
0x180004040  mov     rcx, rsi; lpsz
0x180004043  call    cs:__imp_CharNextW
0x180004049  mov     [rdi], rax
0x18000404c  mov     rcx, rax; lpsz
0x18000404f  movzx   edx, word ptr [rax]
0x180004052  xor     eax, eax
0x180004054  cmp     ax, dx
0x180004057  jz      loc_1800040E0
0x18000405d  cmp     r14w, dx
0x180004061  jnz     short loc_18000406F
0x180004063  call    cs:__imp_CharNextW
0x180004069  cmp     r14w, [rax]
0x18000406d  jnz     short loc_1800040E0
0x18000406f  mov     rsi, [rdi]
0x180004072  cmp     r14w, [rsi]
0x180004076  jnz     short loc_180004087
0x180004078  mov     rcx, rsi; lpsz
0x18000407b  call    cs:__imp_CharNextW
0x180004081  mov     rsi, rax
0x180004084  mov     [rdi], rax
0x180004087  mov     rcx, rsi; lpsz
0x18000408a  call    cs:__imp_CharNextW
0x180004090  mov     rdx, rax
0x180004093  mov     [rdi], rax
0x180004096  sub     rdx, rsi
0x180004099  sar     rdx, 1
0x18000409c  lea     rcx, [rdx+1]
0x1800040a0  lea     rcx, [rbx+rcx*2]
0x1800040a4  cmp     rcx, rbp
0x1800040a7  jnb     short loc_1800040D0
0x1800040a9  xor     ecx, ecx
0x1800040ab  test    edx, edx
0x1800040ad  jle     short loc_1800040C3
0x1800040af  movzx   eax, word ptr [rsi]
0x1800040b2  inc     ecx
0x1800040b4  mov     [rbx], ax
0x1800040b7  lea     rsi, [rsi+2]
0x1800040bb  add     rbx, 2
0x1800040bf  cmp     ecx, edx
0x1800040c1  jl      short loc_1800040AF
0x1800040c3  mov     rcx, [rdi]
0x1800040c6  xor     eax, eax
0x1800040c8  movzx   edx, word ptr [rcx]
0x1800040cb  cmp     ax, dx
0x1800040ce  jnz     short loc_18000405D
0x1800040d0  mov     eax, 80020009h
0x1800040d5  add     rsp, 20h
0x1800040d9  pop     r14
0x1800040db  pop     rdi
0x1800040dc  pop     rsi
0x1800040dd  pop     rbp
0x1800040de  pop     rbx
0x1800040df  retn
0x1800040e0  mov     rcx, [rdi]
0x1800040e3  xor     eax, eax
0x1800040e5  cmp     ax, [rcx]
0x1800040e8  jz      short loc_1800040D0
0x1800040ea  cmp     rbx, rbp
0x1800040ed  jnb     short loc_1800040D0
0x1800040ef  mov     [rbx], ax
0x1800040f2  mov     rcx, [rdi]; lpsz
0x1800040f5  call    cs:__imp_CharNextW
0x1800040fb  mov     [rdi], rax
0x1800040fe  jmp     short loc_180004170
0x180004100  movzx   ecx, cx
0x180004103  sub     ecx, 9
0x180004106  jz      short loc_180004162
0x180004108  sub     ecx, 1
0x18000410b  jz      short loc_180004162
0x18000410d  sub     ecx, 3
0x180004110  jz      short loc_180004162
0x180004112  cmp     ecx, 13h
0x180004115  jz      short loc_180004162
0x180004117  mov     rcx, rsi; lpsz
0x18000411a  call    cs:__imp_CharNextW
0x180004120  mov     rdx, rax
0x180004123  mov     [rdi], rax
0x180004126  sub     rdx, rsi
0x180004129  sar     rdx, 1
0x18000412c  lea     rcx, [rdx+1]
0x180004130  lea     rcx, [rbx+rcx*2]
0x180004134  cmp     rcx, rbp
0x180004137  jnb     short loc_1800040D0
0x180004139  xor     ecx, ecx
0x18000413b  test    edx, edx
0x18000413d  jle     short loc_180004153
0x18000413f  movzx   eax, word ptr [rsi]
0x180004142  inc     ecx
0x180004144  mov     [rbx], ax
0x180004147  lea     rsi, [rsi+2]
0x18000414b  add     rbx, 2
0x18000414f  cmp     ecx, edx
0x180004151  jl      short loc_18000413F
0x180004153  mov     rsi, [rdi]
0x180004156  xor     eax, eax
0x180004158  cmp     ax, [rsi]
0x18000415b  jz      short loc_180004162
0x18000415d  movzx   ecx, word ptr [rsi]
0x180004160  jmp     short loc_180004100
0x180004162  cmp     rbx, rbp
0x180004165  jnb     loc_1800040D0
0x18000416b  xor     eax, eax
0x18000416d  mov     [rbx], ax
0x180004170  xor     eax, eax
0x180004172  jmp     loc_1800040D5
```
