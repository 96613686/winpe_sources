# ATL::CRegParser::NextToken(ushort *)

- ea: `0x18000b130`
- end: `0x18000b2c7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009234`
- `0x18000bcbc`
- `0x18000c254`
- `0x18000d3c4`

## callees

- `0x18000b130`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b165`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b193`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b1b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b1cb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b1da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b245`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b26a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b165`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b193`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b1b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b1cb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b1da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b245`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b26a`

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
0x18000b130  push    rbx
0x18000b132  push    rbp
0x18000b133  push    rsi
0x18000b134  push    rdi
0x18000b135  push    r14
0x18000b137  sub     rsp, 20h
0x18000b13b  mov     rbx, rdx
0x18000b13e  mov     rdi, rcx
0x18000b141  mov     rsi, [rdi]
0x18000b144  movzx   ecx, word ptr [rsi]
0x18000b147  mov     r8d, ecx
0x18000b14a  sub     r8d, 9
0x18000b14e  jz      short loc_18000B162
0x18000b150  sub     r8d, 1
0x18000b154  jz      short loc_18000B162
0x18000b156  sub     r8d, 3
0x18000b15a  jz      short loc_18000B162
0x18000b15c  cmp     r8d, 13h
0x18000b160  jnz     short loc_18000B170
0x18000b162  mov     rcx, rsi; lpsz
0x18000b165  call    cs:__imp_CharNextW
0x18000b16b  mov     [rdi], rax
0x18000b16e  jmp     short loc_18000B141
0x18000b170  xor     eax, eax
0x18000b172  cmp     ax, cx
0x18000b175  jz      loc_18000B220
0x18000b17b  lea     r14d, [rax+27h]
0x18000b17f  lea     rbp, [rbx+2000h]
0x18000b186  cmp     r14w, cx
0x18000b18a  jnz     loc_18000B250
0x18000b190  mov     rcx, rsi; lpsz
0x18000b193  call    cs:__imp_CharNextW
0x18000b199  mov     [rdi], rax
0x18000b19c  mov     rcx, rax; lpsz
0x18000b19f  movzx   edx, word ptr [rax]
0x18000b1a2  xor     eax, eax
0x18000b1a4  cmp     ax, dx
0x18000b1a7  jz      loc_18000B230
0x18000b1ad  cmp     r14w, dx
0x18000b1b1  jnz     short loc_18000B1BF
0x18000b1b3  call    cs:__imp_CharNextW
0x18000b1b9  cmp     r14w, [rax]
0x18000b1bd  jnz     short loc_18000B230
0x18000b1bf  mov     rsi, [rdi]
0x18000b1c2  cmp     r14w, [rsi]
0x18000b1c6  jnz     short loc_18000B1D7
0x18000b1c8  mov     rcx, rsi; lpsz
0x18000b1cb  call    cs:__imp_CharNextW
0x18000b1d1  mov     rsi, rax
0x18000b1d4  mov     [rdi], rax
0x18000b1d7  mov     rcx, rsi; lpsz
0x18000b1da  call    cs:__imp_CharNextW
0x18000b1e0  mov     rdx, rax
0x18000b1e3  mov     [rdi], rax
0x18000b1e6  sub     rdx, rsi
0x18000b1e9  sar     rdx, 1
0x18000b1ec  lea     rcx, [rdx+1]
0x18000b1f0  lea     rcx, [rbx+rcx*2]
0x18000b1f4  cmp     rcx, rbp
0x18000b1f7  jnb     short loc_18000B220
0x18000b1f9  xor     ecx, ecx
0x18000b1fb  test    edx, edx
0x18000b1fd  jle     short loc_18000B213
0x18000b1ff  movzx   eax, word ptr [rsi]
0x18000b202  inc     ecx
0x18000b204  mov     [rbx], ax
0x18000b207  lea     rsi, [rsi+2]
0x18000b20b  add     rbx, 2
0x18000b20f  cmp     ecx, edx
0x18000b211  jl      short loc_18000B1FF
0x18000b213  mov     rcx, [rdi]
0x18000b216  xor     eax, eax
0x18000b218  movzx   edx, word ptr [rcx]
0x18000b21b  cmp     ax, dx
0x18000b21e  jnz     short loc_18000B1AD
0x18000b220  mov     eax, 80020009h
0x18000b225  add     rsp, 20h
0x18000b229  pop     r14
0x18000b22b  pop     rdi
0x18000b22c  pop     rsi
0x18000b22d  pop     rbp
0x18000b22e  pop     rbx
0x18000b22f  retn
0x18000b230  mov     rcx, [rdi]
0x18000b233  xor     eax, eax
0x18000b235  cmp     ax, [rcx]
0x18000b238  jz      short loc_18000B220
0x18000b23a  cmp     rbx, rbp
0x18000b23d  jnb     short loc_18000B220
0x18000b23f  mov     [rbx], ax
0x18000b242  mov     rcx, [rdi]; lpsz
0x18000b245  call    cs:__imp_CharNextW
0x18000b24b  mov     [rdi], rax
0x18000b24e  jmp     short loc_18000B2C0
0x18000b250  movzx   ecx, cx
0x18000b253  sub     ecx, 9
0x18000b256  jz      short loc_18000B2B2
0x18000b258  sub     ecx, 1
0x18000b25b  jz      short loc_18000B2B2
0x18000b25d  sub     ecx, 3
0x18000b260  jz      short loc_18000B2B2
0x18000b262  cmp     ecx, 13h
0x18000b265  jz      short loc_18000B2B2
0x18000b267  mov     rcx, rsi; lpsz
0x18000b26a  call    cs:__imp_CharNextW
0x18000b270  mov     rdx, rax
0x18000b273  mov     [rdi], rax
0x18000b276  sub     rdx, rsi
0x18000b279  sar     rdx, 1
0x18000b27c  lea     rcx, [rdx+1]
0x18000b280  lea     rcx, [rbx+rcx*2]
0x18000b284  cmp     rcx, rbp
0x18000b287  jnb     short loc_18000B220
0x18000b289  xor     ecx, ecx
0x18000b28b  test    edx, edx
0x18000b28d  jle     short loc_18000B2A3
0x18000b28f  movzx   eax, word ptr [rsi]
0x18000b292  inc     ecx
0x18000b294  mov     [rbx], ax
0x18000b297  lea     rsi, [rsi+2]
0x18000b29b  add     rbx, 2
0x18000b29f  cmp     ecx, edx
0x18000b2a1  jl      short loc_18000B28F
0x18000b2a3  mov     rsi, [rdi]
0x18000b2a6  xor     eax, eax
0x18000b2a8  cmp     ax, [rsi]
0x18000b2ab  jz      short loc_18000B2B2
0x18000b2ad  movzx   ecx, word ptr [rsi]
0x18000b2b0  jmp     short loc_18000B250
0x18000b2b2  cmp     rbx, rbp
0x18000b2b5  jnb     loc_18000B220
0x18000b2bb  xor     eax, eax
0x18000b2bd  mov     [rbx], ax
0x18000b2c0  xor     eax, eax
0x18000b2c2  jmp     loc_18000B225
```
