# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180003a70`
- end: `0x180003c66`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `502`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c98`
- `0x18000420c`
- `0x18000459c`
- `0x180004fe0`

## callees

- `0x180003a70`

## import_xrefs

- `USER32!CharNextW` at `0x180003ab2`
- `USER32!CharNextW` at `0x180003aeb`
- `USER32!CharNextW` at `0x180003b10`
- `USER32!CharNextW` at `0x180003b32`
- `USER32!CharNextW` at `0x180003b47`
- `USER32!CharNextW` at `0x180003bd4`
- `USER32!CharNextW` at `0x180003bff`
- `USER32!CharNextW` at `0x180003ab2`
- `USER32!CharNextW` at `0x180003aeb`
- `USER32!CharNextW` at `0x180003b10`
- `USER32!CharNextW` at `0x180003b32`
- `USER32!CharNextW` at `0x180003b47`
- `USER32!CharNextW` at `0x180003bd4`
- `USER32!CharNextW` at `0x180003bff`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rbp
  LPWSTR v8; // rax
  WCHAR v9; // cx
  const WCHAR *v10; // rsi
  LPWSTR v11; // rax
  __int64 v12; // rax
  signed __int64 v13; // rsi
  __int64 v14; // rcx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  LPWSTR v19; // rax
  __int64 v20; // rax
  signed __int64 v21; // rsi
  __int64 v22; // rcx

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
  v7 = a2 + 4096;
  if ( v5 != 39 )
  {
    do
    {
      v16 = v5 - 9;
      if ( !v16 )
        break;
      v17 = v16 - 1;
      if ( !v17 )
        break;
      v18 = v17 - 3;
      if ( !v18 || v18 == 19 )
        break;
      v19 = CharNextW(v4);
      *this = v19;
      v20 = v19 - v4;
      if ( &a2[v20 + 1] >= v6 + 4096 )
        return 2147614729LL;
      if ( (int)v20 > 0 )
      {
        v21 = (char *)v4 - (char *)a2;
        v22 = (unsigned int)v20;
        do
        {
          *a2 = *(unsigned __int16 *)((char *)a2 + v21);
          ++a2;
          --v22;
        }
        while ( v22 );
      }
      v4 = *this;
      v5 = **this;
    }
    while ( v5 );
    if ( a2 < v7 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v8 = CharNextW(*this);
  *this = v8;
  v9 = *v8;
  if ( *v8 )
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
      if ( &a2[v12 + 1] < v6 + 4096 )
      {
        if ( (int)v12 > 0 )
        {
          v13 = (char *)v10 - (char *)a2;
          v14 = (unsigned int)v12;
          do
          {
            *a2 = *(unsigned __int16 *)((char *)a2 + v13);
            ++a2;
            --v14;
          }
          while ( v14 );
        }
        v8 = (LPWSTR)*this;
        v9 = **this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this || a2 >= v7 )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x180003a70  mov     rax, rsp
0x180003a73  mov     [rax+8], rbx
0x180003a77  mov     [rax+10h], rbp
0x180003a7b  mov     [rax+18h], rsi
0x180003a7f  mov     [rax+20h], rdi
0x180003a83  push    r12
0x180003a85  push    r14
0x180003a87  push    r15
0x180003a89  sub     rsp, 20h
0x180003a8d  mov     rbx, rdx
0x180003a90  mov     rdi, rcx
0x180003a93  mov     rsi, [rdi]
0x180003a96  movzx   ecx, word ptr [rsi]
0x180003a99  mov     edx, ecx
0x180003a9b  sub     edx, 9
0x180003a9e  jz      short loc_180003AAF
0x180003aa0  sub     edx, 1
0x180003aa3  jz      short loc_180003AAF
0x180003aa5  sub     edx, 3
0x180003aa8  jz      short loc_180003AAF
0x180003aaa  cmp     edx, 13h
0x180003aad  jnz     short loc_180003AC3
0x180003aaf  mov     rcx, rsi; lpsz
0x180003ab2  call    cs:__imp_CharNextW
0x180003ab9  nop     dword ptr [rax+rax+00h]
0x180003abe  mov     [rdi], rax
0x180003ac1  jmp     short loc_180003A93
0x180003ac3  xor     r15d, r15d
0x180003ac6  cmp     r15w, cx
0x180003aca  jz      loc_180003B9A
0x180003ad0  lea     r12d, [r15+27h]
0x180003ad4  mov     r14, rbx
0x180003ad7  lea     rbp, [rbx+2000h]
0x180003ade  cmp     r12w, cx
0x180003ae2  jnz     loc_180003BE5
0x180003ae8  mov     rcx, rsi; lpsz
0x180003aeb  call    cs:__imp_CharNextW
0x180003af2  nop     dword ptr [rax+rax+00h]
0x180003af7  mov     [rdi], rax
0x180003afa  movzx   ecx, word ptr [rax]
0x180003afd  cmp     r15w, cx
0x180003b01  jz      loc_180003BBF
0x180003b07  cmp     r12w, cx
0x180003b0b  jnz     short loc_180003B26
0x180003b0d  mov     rcx, rax; lpsz
0x180003b10  call    cs:__imp_CharNextW
0x180003b17  nop     dword ptr [rax+rax+00h]
0x180003b1c  cmp     r12w, [rax]
0x180003b20  jnz     loc_180003BBF
0x180003b26  mov     rsi, [rdi]
0x180003b29  cmp     r12w, [rsi]
0x180003b2d  jnz     short loc_180003B44
0x180003b2f  mov     rcx, rsi; lpsz
0x180003b32  call    cs:__imp_CharNextW
0x180003b39  nop     dword ptr [rax+rax+00h]
0x180003b3e  mov     rsi, rax
0x180003b41  mov     [rdi], rax
0x180003b44  mov     rcx, rsi; lpsz
0x180003b47  call    cs:__imp_CharNextW
0x180003b4e  nop     dword ptr [rax+rax+00h]
0x180003b53  mov     [rdi], rax
0x180003b56  lea     rcx, [r14+2000h]
0x180003b5d  sub     rax, rsi
0x180003b60  sar     rax, 1
0x180003b63  lea     rdx, [rax+1]
0x180003b67  lea     rdx, [rbx+rdx*2]
0x180003b6b  cmp     rdx, rcx
0x180003b6e  jnb     short loc_180003B9A
0x180003b70  test    eax, eax
0x180003b72  jle     short loc_180003B8A
0x180003b74  sub     rsi, rbx
0x180003b77  mov     ecx, eax
0x180003b79  movzx   eax, word ptr [rsi+rbx]
0x180003b7d  mov     [rbx], ax
0x180003b80  add     rbx, 2
0x180003b84  sub     rcx, 1
0x180003b88  jnz     short loc_180003B79
0x180003b8a  mov     rax, [rdi]
0x180003b8d  movzx   ecx, word ptr [rax]
0x180003b90  cmp     r15w, cx
0x180003b94  jnz     loc_180003B07
0x180003b9a  mov     eax, 80020009h
0x180003b9f  mov     rbx, [rsp+38h+arg_0]
0x180003ba4  mov     rbp, [rsp+38h+arg_8]
0x180003ba9  mov     rsi, [rsp+38h+arg_10]
0x180003bae  mov     rdi, [rsp+38h+arg_18]
0x180003bb3  add     rsp, 20h
0x180003bb7  pop     r15
0x180003bb9  pop     r14
0x180003bbb  pop     r12
0x180003bbd  retn
0x180003bbf  mov     rax, [rdi]
0x180003bc2  cmp     r15w, [rax]
0x180003bc6  jz      short loc_180003B9A
0x180003bc8  cmp     rbx, rbp
0x180003bcb  jnb     short loc_180003B9A
0x180003bcd  mov     [rbx], r15w
0x180003bd1  mov     rcx, [rdi]; lpsz
0x180003bd4  call    cs:__imp_CharNextW
0x180003bdb  nop     dword ptr [rax+rax+00h]
0x180003be0  mov     [rdi], rax
0x180003be3  jmp     short loc_180003C5F
0x180003be5  movzx   ecx, cx
0x180003be8  sub     ecx, 9
0x180003beb  jz      short loc_180003C52
0x180003bed  sub     ecx, 1
0x180003bf0  jz      short loc_180003C52
0x180003bf2  sub     ecx, 3
0x180003bf5  jz      short loc_180003C52
0x180003bf7  cmp     ecx, 13h
0x180003bfa  jz      short loc_180003C52
0x180003bfc  mov     rcx, rsi; lpsz
0x180003bff  call    cs:__imp_CharNextW
0x180003c06  nop     dword ptr [rax+rax+00h]
0x180003c0b  mov     [rdi], rax
0x180003c0e  lea     rcx, [r14+2000h]
0x180003c15  sub     rax, rsi
0x180003c18  sar     rax, 1
0x180003c1b  lea     rdx, [rax+1]
0x180003c1f  lea     rdx, [rbx+rdx*2]
0x180003c23  cmp     rdx, rcx
0x180003c26  jnb     loc_180003B9A
0x180003c2c  test    eax, eax
0x180003c2e  jle     short loc_180003C46
0x180003c30  sub     rsi, rbx
0x180003c33  mov     ecx, eax
0x180003c35  movzx   eax, word ptr [rsi+rbx]
0x180003c39  mov     [rbx], ax
0x180003c3c  add     rbx, 2
0x180003c40  sub     rcx, 1
0x180003c44  jnz     short loc_180003C35
0x180003c46  mov     rsi, [rdi]
0x180003c49  movzx   ecx, word ptr [rsi]
0x180003c4c  cmp     r15w, cx
0x180003c50  jnz     short loc_180003BE5
0x180003c52  cmp     rbx, rbp
0x180003c55  jnb     loc_180003B9A
0x180003c5b  mov     [rbx], r15w
0x180003c5f  xor     eax, eax
0x180003c61  jmp     loc_180003B9F
```
