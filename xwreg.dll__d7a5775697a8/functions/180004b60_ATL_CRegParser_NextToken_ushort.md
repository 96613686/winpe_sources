# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004b60`
- end: `0x180004cb7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800033ac`
- `0x18000527c`
- `0x1800055a0`
- `0x180005e5c`

## callees

- `0x180004b60`
- `0x180005ef0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004b99`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bb2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bca`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bd9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004c31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004c60`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004b99`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bb2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bca`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bd9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004c31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004c60`

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
0x180004b60  push    rbx
0x180004b62  push    rbp
0x180004b63  push    rsi
0x180004b64  push    rdi
0x180004b65  push    r14
0x180004b67  sub     rsp, 20h
0x180004b6b  mov     rbx, rdx
0x180004b6e  mov     rdi, rcx
0x180004b71  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180004b76  mov     rcx, [rdi]; lpsz
0x180004b79  xor     eax, eax
0x180004b7b  cmp     ax, [rcx]
0x180004b7e  jz      loc_180004CA7
0x180004b84  lea     r14d, [rax+27h]
0x180004b88  lea     rbp, [rbx+2000h]
0x180004b8f  cmp     r14w, [rcx]
0x180004b93  jnz     loc_180004C3C
0x180004b99  call    cs:__imp_CharNextW
0x180004b9f  mov     [rdi], rax
0x180004ba2  mov     rcx, [rdi]; lpsz
0x180004ba5  xor     eax, eax
0x180004ba7  cmp     ax, [rcx]
0x180004baa  jz      short loc_180004C18
0x180004bac  cmp     r14w, [rcx]
0x180004bb0  jnz     short loc_180004BBE
0x180004bb2  call    cs:__imp_CharNextW
0x180004bb8  cmp     r14w, [rax]
0x180004bbc  jnz     short loc_180004C18
0x180004bbe  mov     rsi, [rdi]
0x180004bc1  cmp     r14w, [rsi]
0x180004bc5  jnz     short loc_180004BD6
0x180004bc7  mov     rcx, rsi; lpsz
0x180004bca  call    cs:__imp_CharNextW
0x180004bd0  mov     rsi, rax
0x180004bd3  mov     [rdi], rax
0x180004bd6  mov     rcx, rsi; lpsz
0x180004bd9  call    cs:__imp_CharNextW
0x180004bdf  mov     rdx, rax
0x180004be2  mov     [rdi], rax
0x180004be5  sub     rdx, rsi
0x180004be8  sar     rdx, 1
0x180004beb  lea     rcx, [rdx+1]
0x180004bef  lea     rcx, [rbx+rcx*2]
0x180004bf3  cmp     rcx, rbp
0x180004bf6  jnb     loc_180004CA7
0x180004bfc  xor     ecx, ecx
0x180004bfe  test    edx, edx
0x180004c00  jle     short loc_180004BA2
0x180004c02  movzx   eax, word ptr [rsi]
0x180004c05  inc     ecx
0x180004c07  mov     [rbx], ax
0x180004c0a  lea     rsi, [rsi+2]
0x180004c0e  add     rbx, 2
0x180004c12  cmp     ecx, edx
0x180004c14  jl      short loc_180004C02
0x180004c16  jmp     short loc_180004BA2
0x180004c18  mov     rcx, [rdi]
0x180004c1b  xor     eax, eax
0x180004c1d  cmp     ax, [rcx]
0x180004c20  jz      loc_180004CA7
0x180004c26  cmp     rbx, rbp
0x180004c29  jnb     short loc_180004CA7
0x180004c2b  mov     [rbx], ax
0x180004c2e  mov     rcx, [rdi]; lpsz
0x180004c31  call    cs:__imp_CharNextW
0x180004c37  mov     [rdi], rax
0x180004c3a  jmp     short loc_180004CA3
0x180004c3c  mov     rsi, [rdi]
0x180004c3f  xor     eax, eax
0x180004c41  cmp     ax, [rsi]
0x180004c44  jz      short loc_180004C9B
0x180004c46  movzx   ecx, word ptr [rsi]
0x180004c49  sub     ecx, 9
0x180004c4c  jz      short loc_180004C9B
0x180004c4e  sub     ecx, 1
0x180004c51  jz      short loc_180004C9B
0x180004c53  sub     ecx, 3
0x180004c56  jz      short loc_180004C9B
0x180004c58  cmp     ecx, 13h
0x180004c5b  jz      short loc_180004C9B
0x180004c5d  mov     rcx, rsi; lpsz
0x180004c60  call    cs:__imp_CharNextW
0x180004c66  mov     rdx, rax
0x180004c69  mov     [rdi], rax
0x180004c6c  sub     rdx, rsi
0x180004c6f  sar     rdx, 1
0x180004c72  lea     rcx, [rdx+1]
0x180004c76  lea     rcx, [rbx+rcx*2]
0x180004c7a  cmp     rcx, rbp
0x180004c7d  jnb     short loc_180004CA7
0x180004c7f  xor     ecx, ecx
0x180004c81  test    edx, edx
0x180004c83  jle     short loc_180004C3C
0x180004c85  movzx   eax, word ptr [rsi]
0x180004c88  inc     ecx
0x180004c8a  mov     [rbx], ax
0x180004c8d  lea     rsi, [rsi+2]
0x180004c91  add     rbx, 2
0x180004c95  cmp     ecx, edx
0x180004c97  jl      short loc_180004C85
0x180004c99  jmp     short loc_180004C3C
0x180004c9b  cmp     rbx, rbp
0x180004c9e  jnb     short loc_180004CA7
0x180004ca0  mov     [rbx], ax
0x180004ca3  xor     eax, eax
0x180004ca5  jmp     short loc_180004CAC
0x180004ca7  mov     eax, 80020009h
0x180004cac  add     rsp, 20h
0x180004cb0  pop     r14
0x180004cb2  pop     rdi
0x180004cb3  pop     rsi
0x180004cb4  pop     rbp
0x180004cb5  pop     rbx
0x180004cb6  retn
```
