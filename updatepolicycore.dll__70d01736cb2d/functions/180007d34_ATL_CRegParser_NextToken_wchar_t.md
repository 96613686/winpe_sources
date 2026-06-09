# ATL::CRegParser::NextToken(wchar_t *)

- ea: `0x180007d34`
- end: `0x180007ed7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z`
- size: `419`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000728c`
- `0x1800078f0`
- `0x180007ee0`
- `0x18000862c`

## callees

- `0x180007d34`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007d71`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007d9d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007dbc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007dd8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007de7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007e5e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007e83`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007d71`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007d9d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007dbc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007dd8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007de7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007e5e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007e83`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, wchar_t *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  wchar_t *v6; // rbp
  LPWSTR v7; // rax
  WCHAR v8; // cx
  const WCHAR *v9; // rsi
  LPWSTR v10; // rax
  __int64 v11; // rax
  signed __int64 v12; // rsi
  __int64 v13; // rcx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  LPWSTR v18; // rax
  __int64 v19; // rax
  signed __int64 v20; // rsi
  __int64 v21; // rcx

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
  v6 = a2;
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
      *this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 + 4096 )
        return 2147614729LL;
      if ( (int)v19 > 0 )
      {
        v20 = (char *)v4 - (char *)a2;
        v21 = (unsigned int)v19;
        do
        {
          *a2 = *(wchar_t *)((char *)a2 + v20);
          ++a2;
          --v21;
        }
        while ( v21 );
      }
      v4 = *this;
      v5 = **this;
    }
    while ( v5 );
    *a2 = 0;
    return 0;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = *v7;
  if ( *v7 )
  {
    while ( v8 != 39 || *CharNextW(v7) == 39 )
    {
      v9 = *this;
      if ( **this == 39 )
      {
        v9 = CharNextW(*this);
        *this = v9;
      }
      v10 = CharNextW(v9);
      *this = v10;
      v11 = v10 - v9;
      if ( &a2[v11 + 1] < v6 + 4096 )
      {
        if ( (int)v11 > 0 )
        {
          v12 = (char *)v9 - (char *)a2;
          v13 = (unsigned int)v11;
          do
          {
            *a2 = *(wchar_t *)((char *)a2 + v12);
            ++a2;
            --v13;
          }
          while ( v13 );
        }
        v7 = (LPWSTR)*this;
        v8 = **this;
        if ( v8 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x180007d34  mov     [rsp+arg_0], rbx
0x180007d39  mov     [rsp+arg_8], rbp
0x180007d3e  mov     [rsp+arg_10], rsi
0x180007d43  push    rdi
0x180007d44  push    r14
0x180007d46  push    r15
0x180007d48  sub     rsp, 20h
0x180007d4c  mov     rbx, rdx
0x180007d4f  mov     rdi, rcx
0x180007d52  mov     rsi, [rdi]
0x180007d55  movzx   ecx, word ptr [rsi]
0x180007d58  mov     edx, ecx
0x180007d5a  sub     edx, 9
0x180007d5d  jz      short loc_180007D6E
0x180007d5f  sub     edx, 1
0x180007d62  jz      short loc_180007D6E
0x180007d64  sub     edx, 3
0x180007d67  jz      short loc_180007D6E
0x180007d69  cmp     edx, 13h
0x180007d6c  jnz     short loc_180007D7C
0x180007d6e  mov     rcx, rsi; lpsz
0x180007d71  call    cs:__imp_CharNextW
0x180007d77  mov     [rdi], rax
0x180007d7a  jmp     short loc_180007D52
0x180007d7c  xor     r14d, r14d
0x180007d7f  cmp     r14w, cx
0x180007d83  jz      loc_180007E30
0x180007d89  lea     r15d, [r14+27h]
0x180007d8d  mov     rbp, rbx
0x180007d90  cmp     r15w, cx
0x180007d94  jnz     loc_180007E69
0x180007d9a  mov     rcx, rsi; lpsz
0x180007d9d  call    cs:__imp_CharNextW
0x180007da3  mov     [rdi], rax
0x180007da6  movzx   ecx, word ptr [rax]
0x180007da9  cmp     r14w, cx
0x180007dad  jz      loc_180007E4E
0x180007db3  cmp     r15w, cx
0x180007db7  jnz     short loc_180007DCC
0x180007db9  mov     rcx, rax; lpsz
0x180007dbc  call    cs:__imp_CharNextW
0x180007dc2  cmp     r15w, [rax]
0x180007dc6  jnz     loc_180007E4E
0x180007dcc  mov     rsi, [rdi]
0x180007dcf  cmp     r15w, [rsi]
0x180007dd3  jnz     short loc_180007DE4
0x180007dd5  mov     rcx, rsi; lpsz
0x180007dd8  call    cs:__imp_CharNextW
0x180007dde  mov     rsi, rax
0x180007de1  mov     [rdi], rax
0x180007de4  mov     rcx, rsi; lpsz
0x180007de7  call    cs:__imp_CharNextW
0x180007ded  mov     [rdi], rax
0x180007df0  lea     rcx, [rbp+2000h]
0x180007df7  sub     rax, rsi
0x180007dfa  sar     rax, 1
0x180007dfd  lea     rdx, [rax+1]
0x180007e01  lea     rdx, [rbx+rdx*2]
0x180007e05  cmp     rdx, rcx
0x180007e08  jnb     short loc_180007E30
0x180007e0a  test    eax, eax
0x180007e0c  jle     short loc_180007E24
0x180007e0e  sub     rsi, rbx
0x180007e11  mov     ecx, eax
0x180007e13  movzx   eax, word ptr [rsi+rbx]
0x180007e17  mov     [rbx], ax
0x180007e1a  add     rbx, 2
0x180007e1e  sub     rcx, 1
0x180007e22  jnz     short loc_180007E13
0x180007e24  mov     rax, [rdi]
0x180007e27  movzx   ecx, word ptr [rax]
0x180007e2a  cmp     r14w, cx
0x180007e2e  jnz     short loc_180007DB3
0x180007e30  mov     eax, 80020009h
0x180007e35  mov     rbx, [rsp+38h+arg_0]
0x180007e3a  mov     rbp, [rsp+38h+arg_8]
0x180007e3f  mov     rsi, [rsp+38h+arg_10]
0x180007e44  add     rsp, 20h
0x180007e48  pop     r15
0x180007e4a  pop     r14
0x180007e4c  pop     rdi
0x180007e4d  retn
0x180007e4e  mov     rax, [rdi]
0x180007e51  cmp     r14w, [rax]
0x180007e55  jz      short loc_180007E30
0x180007e57  mov     [rbx], r14w
0x180007e5b  mov     rcx, [rdi]; lpsz
0x180007e5e  call    cs:__imp_CharNextW
0x180007e64  mov     [rdi], rax
0x180007e67  jmp     short loc_180007ED0
0x180007e69  movzx   ecx, cx
0x180007e6c  sub     ecx, 9
0x180007e6f  jz      short loc_180007ECC
0x180007e71  sub     ecx, 1
0x180007e74  jz      short loc_180007ECC
0x180007e76  sub     ecx, 3
0x180007e79  jz      short loc_180007ECC
0x180007e7b  cmp     ecx, 13h
0x180007e7e  jz      short loc_180007ECC
0x180007e80  mov     rcx, rsi; lpsz
0x180007e83  call    cs:__imp_CharNextW
0x180007e89  mov     [rdi], rax
0x180007e8c  lea     rcx, [rbp+2000h]
0x180007e93  sub     rax, rsi
0x180007e96  sar     rax, 1
0x180007e99  lea     rdx, [rax+1]
0x180007e9d  lea     rdx, [rbx+rdx*2]
0x180007ea1  cmp     rdx, rcx
0x180007ea4  jnb     short loc_180007E30
0x180007ea6  test    eax, eax
0x180007ea8  jle     short loc_180007EC0
0x180007eaa  sub     rsi, rbx
0x180007ead  mov     ecx, eax
0x180007eaf  movzx   eax, word ptr [rsi+rbx]
0x180007eb3  mov     [rbx], ax
0x180007eb6  add     rbx, 2
0x180007eba  sub     rcx, 1
0x180007ebe  jnz     short loc_180007EAF
0x180007ec0  mov     rsi, [rdi]
0x180007ec3  movzx   ecx, word ptr [rsi]
0x180007ec6  cmp     r14w, cx
0x180007eca  jnz     short loc_180007E69
0x180007ecc  mov     [rbx], r14w
0x180007ed0  xor     eax, eax
0x180007ed2  jmp     loc_180007E35
```
