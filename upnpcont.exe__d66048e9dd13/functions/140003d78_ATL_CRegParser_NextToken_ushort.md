# ATL::CRegParser::NextToken(ushort *)

- ea: `0x140003d78`
- end: `0x140003f0f`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002424`
- `0x1400043a8`
- `0x140004954`
- `0x1400051e0`

## callees

- `0x140003d78`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003dad`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003ddb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003dfb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003e13`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003e22`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003e8d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003eb2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003dad`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003ddb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003dfb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003e13`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003e22`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003e8d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003eb2`

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
0x140003d78  push    rbx
0x140003d7a  push    rbp
0x140003d7b  push    rsi
0x140003d7c  push    rdi
0x140003d7d  push    r14
0x140003d7f  sub     rsp, 20h
0x140003d83  mov     rbx, rdx
0x140003d86  mov     rdi, rcx
0x140003d89  mov     rsi, [rdi]
0x140003d8c  movzx   ecx, word ptr [rsi]
0x140003d8f  mov     r8d, ecx
0x140003d92  sub     r8d, 9
0x140003d96  jz      short loc_140003DAA
0x140003d98  sub     r8d, 1
0x140003d9c  jz      short loc_140003DAA
0x140003d9e  sub     r8d, 3
0x140003da2  jz      short loc_140003DAA
0x140003da4  cmp     r8d, 13h
0x140003da8  jnz     short loc_140003DB8
0x140003daa  mov     rcx, rsi; lpsz
0x140003dad  call    cs:__imp_CharNextW
0x140003db3  mov     [rdi], rax
0x140003db6  jmp     short loc_140003D89
0x140003db8  xor     eax, eax
0x140003dba  cmp     ax, cx
0x140003dbd  jz      loc_140003E68
0x140003dc3  lea     r14d, [rax+27h]
0x140003dc7  lea     rbp, [rbx+2000h]
0x140003dce  cmp     r14w, cx
0x140003dd2  jnz     loc_140003E98
0x140003dd8  mov     rcx, rsi; lpsz
0x140003ddb  call    cs:__imp_CharNextW
0x140003de1  mov     [rdi], rax
0x140003de4  mov     rcx, rax; lpsz
0x140003de7  movzx   edx, word ptr [rax]
0x140003dea  xor     eax, eax
0x140003dec  cmp     ax, dx
0x140003def  jz      loc_140003E78
0x140003df5  cmp     r14w, dx
0x140003df9  jnz     short loc_140003E07
0x140003dfb  call    cs:__imp_CharNextW
0x140003e01  cmp     r14w, [rax]
0x140003e05  jnz     short loc_140003E78
0x140003e07  mov     rsi, [rdi]
0x140003e0a  cmp     r14w, [rsi]
0x140003e0e  jnz     short loc_140003E1F
0x140003e10  mov     rcx, rsi; lpsz
0x140003e13  call    cs:__imp_CharNextW
0x140003e19  mov     rsi, rax
0x140003e1c  mov     [rdi], rax
0x140003e1f  mov     rcx, rsi; lpsz
0x140003e22  call    cs:__imp_CharNextW
0x140003e28  mov     rdx, rax
0x140003e2b  mov     [rdi], rax
0x140003e2e  sub     rdx, rsi
0x140003e31  sar     rdx, 1
0x140003e34  lea     rcx, [rdx+1]
0x140003e38  lea     rcx, [rbx+rcx*2]
0x140003e3c  cmp     rcx, rbp
0x140003e3f  jnb     short loc_140003E68
0x140003e41  xor     ecx, ecx
0x140003e43  test    edx, edx
0x140003e45  jle     short loc_140003E5B
0x140003e47  movzx   eax, word ptr [rsi]
0x140003e4a  inc     ecx
0x140003e4c  mov     [rbx], ax
0x140003e4f  lea     rsi, [rsi+2]
0x140003e53  add     rbx, 2
0x140003e57  cmp     ecx, edx
0x140003e59  jl      short loc_140003E47
0x140003e5b  mov     rcx, [rdi]
0x140003e5e  xor     eax, eax
0x140003e60  movzx   edx, word ptr [rcx]
0x140003e63  cmp     ax, dx
0x140003e66  jnz     short loc_140003DF5
0x140003e68  mov     eax, 80020009h
0x140003e6d  add     rsp, 20h
0x140003e71  pop     r14
0x140003e73  pop     rdi
0x140003e74  pop     rsi
0x140003e75  pop     rbp
0x140003e76  pop     rbx
0x140003e77  retn
0x140003e78  mov     rcx, [rdi]
0x140003e7b  xor     eax, eax
0x140003e7d  cmp     ax, [rcx]
0x140003e80  jz      short loc_140003E68
0x140003e82  cmp     rbx, rbp
0x140003e85  jnb     short loc_140003E68
0x140003e87  mov     [rbx], ax
0x140003e8a  mov     rcx, [rdi]; lpsz
0x140003e8d  call    cs:__imp_CharNextW
0x140003e93  mov     [rdi], rax
0x140003e96  jmp     short loc_140003F08
0x140003e98  movzx   ecx, cx
0x140003e9b  sub     ecx, 9
0x140003e9e  jz      short loc_140003EFA
0x140003ea0  sub     ecx, 1
0x140003ea3  jz      short loc_140003EFA
0x140003ea5  sub     ecx, 3
0x140003ea8  jz      short loc_140003EFA
0x140003eaa  cmp     ecx, 13h
0x140003ead  jz      short loc_140003EFA
0x140003eaf  mov     rcx, rsi; lpsz
0x140003eb2  call    cs:__imp_CharNextW
0x140003eb8  mov     rdx, rax
0x140003ebb  mov     [rdi], rax
0x140003ebe  sub     rdx, rsi
0x140003ec1  sar     rdx, 1
0x140003ec4  lea     rcx, [rdx+1]
0x140003ec8  lea     rcx, [rbx+rcx*2]
0x140003ecc  cmp     rcx, rbp
0x140003ecf  jnb     short loc_140003E68
0x140003ed1  xor     ecx, ecx
0x140003ed3  test    edx, edx
0x140003ed5  jle     short loc_140003EEB
0x140003ed7  movzx   eax, word ptr [rsi]
0x140003eda  inc     ecx
0x140003edc  mov     [rbx], ax
0x140003edf  lea     rsi, [rsi+2]
0x140003ee3  add     rbx, 2
0x140003ee7  cmp     ecx, edx
0x140003ee9  jl      short loc_140003ED7
0x140003eeb  mov     rsi, [rdi]
0x140003eee  xor     eax, eax
0x140003ef0  cmp     ax, [rsi]
0x140003ef3  jz      short loc_140003EFA
0x140003ef5  movzx   ecx, word ptr [rsi]
0x140003ef8  jmp     short loc_140003E98
0x140003efa  cmp     rbx, rbp
0x140003efd  jnb     loc_140003E68
0x140003f03  xor     eax, eax
0x140003f05  mov     [rbx], ax
0x140003f08  xor     eax, eax
0x140003f0a  jmp     loc_140003E6D
```
