# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800031f4`
- end: `0x18000338b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000271c`
- `0x1800037e8`
- `0x180003b5c`
- `0x18000430c`

## callees

- `0x1800031f4`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003229`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003257`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003277`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000328f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000329e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003309`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000332e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003229`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003257`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003277`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000328f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000329e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003309`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000332e`

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
0x1800031f4  push    rbx
0x1800031f6  push    rbp
0x1800031f7  push    rsi
0x1800031f8  push    rdi
0x1800031f9  push    r14
0x1800031fb  sub     rsp, 20h
0x1800031ff  mov     rbx, rdx
0x180003202  mov     rdi, rcx
0x180003205  mov     rsi, [rdi]
0x180003208  movzx   ecx, word ptr [rsi]
0x18000320b  mov     r8d, ecx
0x18000320e  sub     r8d, 9
0x180003212  jz      short loc_180003226
0x180003214  sub     r8d, 1
0x180003218  jz      short loc_180003226
0x18000321a  sub     r8d, 3
0x18000321e  jz      short loc_180003226
0x180003220  cmp     r8d, 13h
0x180003224  jnz     short loc_180003234
0x180003226  mov     rcx, rsi; lpsz
0x180003229  call    cs:__imp_CharNextW
0x18000322f  mov     [rdi], rax
0x180003232  jmp     short loc_180003205
0x180003234  xor     eax, eax
0x180003236  cmp     ax, cx
0x180003239  jz      loc_1800032E4
0x18000323f  lea     r14d, [rax+27h]
0x180003243  lea     rbp, [rbx+2000h]
0x18000324a  cmp     r14w, cx
0x18000324e  jnz     loc_180003314
0x180003254  mov     rcx, rsi; lpsz
0x180003257  call    cs:__imp_CharNextW
0x18000325d  mov     [rdi], rax
0x180003260  mov     rcx, rax; lpsz
0x180003263  movzx   edx, word ptr [rax]
0x180003266  xor     eax, eax
0x180003268  cmp     ax, dx
0x18000326b  jz      loc_1800032F4
0x180003271  cmp     r14w, dx
0x180003275  jnz     short loc_180003283
0x180003277  call    cs:__imp_CharNextW
0x18000327d  cmp     r14w, [rax]
0x180003281  jnz     short loc_1800032F4
0x180003283  mov     rsi, [rdi]
0x180003286  cmp     r14w, [rsi]
0x18000328a  jnz     short loc_18000329B
0x18000328c  mov     rcx, rsi; lpsz
0x18000328f  call    cs:__imp_CharNextW
0x180003295  mov     rsi, rax
0x180003298  mov     [rdi], rax
0x18000329b  mov     rcx, rsi; lpsz
0x18000329e  call    cs:__imp_CharNextW
0x1800032a4  mov     rdx, rax
0x1800032a7  mov     [rdi], rax
0x1800032aa  sub     rdx, rsi
0x1800032ad  sar     rdx, 1
0x1800032b0  lea     rcx, [rdx+1]
0x1800032b4  lea     rcx, [rbx+rcx*2]
0x1800032b8  cmp     rcx, rbp
0x1800032bb  jnb     short loc_1800032E4
0x1800032bd  xor     ecx, ecx
0x1800032bf  test    edx, edx
0x1800032c1  jle     short loc_1800032D7
0x1800032c3  movzx   eax, word ptr [rsi]
0x1800032c6  inc     ecx
0x1800032c8  mov     [rbx], ax
0x1800032cb  lea     rsi, [rsi+2]
0x1800032cf  add     rbx, 2
0x1800032d3  cmp     ecx, edx
0x1800032d5  jl      short loc_1800032C3
0x1800032d7  mov     rcx, [rdi]
0x1800032da  xor     eax, eax
0x1800032dc  movzx   edx, word ptr [rcx]
0x1800032df  cmp     ax, dx
0x1800032e2  jnz     short loc_180003271
0x1800032e4  mov     eax, 80020009h
0x1800032e9  add     rsp, 20h
0x1800032ed  pop     r14
0x1800032ef  pop     rdi
0x1800032f0  pop     rsi
0x1800032f1  pop     rbp
0x1800032f2  pop     rbx
0x1800032f3  retn
0x1800032f4  mov     rcx, [rdi]
0x1800032f7  xor     eax, eax
0x1800032f9  cmp     ax, [rcx]
0x1800032fc  jz      short loc_1800032E4
0x1800032fe  cmp     rbx, rbp
0x180003301  jnb     short loc_1800032E4
0x180003303  mov     [rbx], ax
0x180003306  mov     rcx, [rdi]; lpsz
0x180003309  call    cs:__imp_CharNextW
0x18000330f  mov     [rdi], rax
0x180003312  jmp     short loc_180003384
0x180003314  movzx   ecx, cx
0x180003317  sub     ecx, 9
0x18000331a  jz      short loc_180003376
0x18000331c  sub     ecx, 1
0x18000331f  jz      short loc_180003376
0x180003321  sub     ecx, 3
0x180003324  jz      short loc_180003376
0x180003326  cmp     ecx, 13h
0x180003329  jz      short loc_180003376
0x18000332b  mov     rcx, rsi; lpsz
0x18000332e  call    cs:__imp_CharNextW
0x180003334  mov     rdx, rax
0x180003337  mov     [rdi], rax
0x18000333a  sub     rdx, rsi
0x18000333d  sar     rdx, 1
0x180003340  lea     rcx, [rdx+1]
0x180003344  lea     rcx, [rbx+rcx*2]
0x180003348  cmp     rcx, rbp
0x18000334b  jnb     short loc_1800032E4
0x18000334d  xor     ecx, ecx
0x18000334f  test    edx, edx
0x180003351  jle     short loc_180003367
0x180003353  movzx   eax, word ptr [rsi]
0x180003356  inc     ecx
0x180003358  mov     [rbx], ax
0x18000335b  lea     rsi, [rsi+2]
0x18000335f  add     rbx, 2
0x180003363  cmp     ecx, edx
0x180003365  jl      short loc_180003353
0x180003367  mov     rsi, [rdi]
0x18000336a  xor     eax, eax
0x18000336c  cmp     ax, [rsi]
0x18000336f  jz      short loc_180003376
0x180003371  movzx   ecx, word ptr [rsi]
0x180003374  jmp     short loc_180003314
0x180003376  cmp     rbx, rbp
0x180003379  jnb     loc_1800032E4
0x18000337f  xor     eax, eax
0x180003381  mov     [rbx], ax
0x180003384  xor     eax, eax
0x180003386  jmp     loc_1800032E9
```
