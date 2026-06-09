# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180006f50`
- end: `0x1800070c1`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `369`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e28`
- `0x1800074dc`
- `0x1800078ec`
- `0x180007ff0`

## callees

- `0x180006f50`
- `0x180008084`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f8f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006faf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fc7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fd6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007041`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007066`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f8f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006faf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fc7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fd6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007041`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007066`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  unsigned __int16 v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  const WCHAR *v8; // rcx
  WCHAR v9; // dx
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

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  v5 = **(_WORD **)this;
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    do
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
      *(_QWORD *)this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < (int)v19; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *(const WCHAR **)this;
      v5 = **(_WORD **)this;
    }
    while ( v5 );
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextW(*(LPCWSTR *)this);
  *(_QWORD *)this = v7;
  v8 = v7;
  v9 = *v7;
  if ( *v7 )
  {
    while ( v9 != 39 || *CharNextW(v8) == 39 )
    {
      v10 = *(const WCHAR **)this;
      if ( **(_WORD **)this == 39 )
      {
        v10 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v10;
      }
      v11 = CharNextW(v10);
      *(_QWORD *)this = v11;
      v12 = v11 - v10;
      if ( &a2[v12 + 1] < v6 )
      {
        for ( j = 0; j < (int)v12; ++a2 )
        {
          ++j;
          *a2 = *v10++;
        }
        v8 = *(const WCHAR **)this;
        v9 = **(_WORD **)this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**(_WORD **)this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  return 0;
}

```

## disassembly

```asm
0x180006f50  push    rbx
0x180006f52  push    rbp
0x180006f53  push    rsi
0x180006f54  push    rdi
0x180006f55  push    r14
0x180006f57  sub     rsp, 20h
0x180006f5b  mov     rbx, rdx
0x180006f5e  mov     rdi, rcx
0x180006f61  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180006f66  mov     rsi, [rdi]
0x180006f69  xor     eax, eax
0x180006f6b  movzx   ecx, word ptr [rsi]
0x180006f6e  cmp     ax, cx
0x180006f71  jz      loc_18000701C
0x180006f77  lea     r14d, [rax+27h]
0x180006f7b  lea     rbp, [rbx+2000h]
0x180006f82  cmp     r14w, cx
0x180006f86  jnz     loc_18000704C
0x180006f8c  mov     rcx, rsi; lpsz
0x180006f8f  call    cs:__imp_CharNextW
0x180006f95  mov     [rdi], rax
0x180006f98  mov     rcx, rax; lpsz
0x180006f9b  movzx   edx, word ptr [rax]
0x180006f9e  xor     eax, eax
0x180006fa0  cmp     ax, dx
0x180006fa3  jz      loc_18000702C
0x180006fa9  cmp     r14w, dx
0x180006fad  jnz     short loc_180006FBB
0x180006faf  call    cs:__imp_CharNextW
0x180006fb5  cmp     r14w, [rax]
0x180006fb9  jnz     short loc_18000702C
0x180006fbb  mov     rsi, [rdi]
0x180006fbe  cmp     r14w, [rsi]
0x180006fc2  jnz     short loc_180006FD3
0x180006fc4  mov     rcx, rsi; lpsz
0x180006fc7  call    cs:__imp_CharNextW
0x180006fcd  mov     rsi, rax
0x180006fd0  mov     [rdi], rax
0x180006fd3  mov     rcx, rsi; lpsz
0x180006fd6  call    cs:__imp_CharNextW
0x180006fdc  mov     rdx, rax
0x180006fdf  mov     [rdi], rax
0x180006fe2  sub     rdx, rsi
0x180006fe5  sar     rdx, 1
0x180006fe8  lea     rcx, [rdx+1]
0x180006fec  lea     rcx, [rbx+rcx*2]
0x180006ff0  cmp     rcx, rbp
0x180006ff3  jnb     short loc_18000701C
0x180006ff5  xor     ecx, ecx
0x180006ff7  test    edx, edx
0x180006ff9  jle     short loc_18000700F
0x180006ffb  movzx   eax, word ptr [rsi]
0x180006ffe  inc     ecx
0x180007000  mov     [rbx], ax
0x180007003  lea     rsi, [rsi+2]
0x180007007  add     rbx, 2
0x18000700b  cmp     ecx, edx
0x18000700d  jl      short loc_180006FFB
0x18000700f  mov     rcx, [rdi]
0x180007012  xor     eax, eax
0x180007014  movzx   edx, word ptr [rcx]
0x180007017  cmp     ax, dx
0x18000701a  jnz     short loc_180006FA9
0x18000701c  mov     eax, 80020009h
0x180007021  add     rsp, 20h
0x180007025  pop     r14
0x180007027  pop     rdi
0x180007028  pop     rsi
0x180007029  pop     rbp
0x18000702a  pop     rbx
0x18000702b  retn
0x18000702c  mov     rcx, [rdi]
0x18000702f  xor     eax, eax
0x180007031  cmp     ax, [rcx]
0x180007034  jz      short loc_18000701C
0x180007036  cmp     rbx, rbp
0x180007039  jnb     short loc_18000701C
0x18000703b  mov     [rbx], ax
0x18000703e  mov     rcx, [rdi]; lpsz
0x180007041  call    cs:__imp_CharNextW
0x180007047  mov     [rdi], rax
0x18000704a  jmp     short loc_1800070BA
0x18000704c  movzx   ecx, cx
0x18000704f  sub     ecx, 9
0x180007052  jz      short loc_1800070AC
0x180007054  sub     ecx, 1
0x180007057  jz      short loc_1800070AC
0x180007059  sub     ecx, 3
0x18000705c  jz      short loc_1800070AC
0x18000705e  cmp     ecx, 13h
0x180007061  jz      short loc_1800070AC
0x180007063  mov     rcx, rsi; lpsz
0x180007066  call    cs:__imp_CharNextW
0x18000706c  mov     rdx, rax
0x18000706f  mov     [rdi], rax
0x180007072  sub     rdx, rsi
0x180007075  sar     rdx, 1
0x180007078  lea     rcx, [rdx+1]
0x18000707c  lea     rcx, [rbx+rcx*2]
0x180007080  cmp     rcx, rbp
0x180007083  jnb     short loc_18000701C
0x180007085  xor     ecx, ecx
0x180007087  test    edx, edx
0x180007089  jle     short loc_18000709F
0x18000708b  movzx   eax, word ptr [rsi]
0x18000708e  inc     ecx
0x180007090  mov     [rbx], ax
0x180007093  lea     rsi, [rsi+2]
0x180007097  add     rbx, 2
0x18000709b  cmp     ecx, edx
0x18000709d  jl      short loc_18000708B
0x18000709f  mov     rsi, [rdi]
0x1800070a2  xor     eax, eax
0x1800070a4  movzx   ecx, word ptr [rsi]
0x1800070a7  cmp     ax, cx
0x1800070aa  jnz     short loc_18000704C
0x1800070ac  cmp     rbx, rbp
0x1800070af  jnb     loc_18000701C
0x1800070b5  xor     eax, eax
0x1800070b7  mov     [rbx], ax
0x1800070ba  xor     eax, eax
0x1800070bc  jmp     loc_180007021
```
