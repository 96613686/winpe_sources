# ATL::CRegParser::NextToken(ushort *)

- ea: `0x14000b134`
- end: `0x14000b2bc`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140009ec8`
- `0x14000b808`
- `0x14000bbf0`
- `0x14000c774`

## callees

- `0x14000b134`

## import_xrefs

- `USER32!CharNextW` at `0x14000b169`
- `USER32!CharNextW` at `0x14000b18f`
- `USER32!CharNextW` at `0x14000b1a9`
- `USER32!CharNextW` at `0x14000b1c1`
- `USER32!CharNextW` at `0x14000b1d0`
- `USER32!CharNextW` at `0x14000b236`
- `USER32!CharNextW` at `0x14000b25b`
- `USER32!CharNextW` at `0x14000b169`
- `USER32!CharNextW` at `0x14000b18f`
- `USER32!CharNextW` at `0x14000b1a9`
- `USER32!CharNextW` at `0x14000b1c1`
- `USER32!CharNextW` at `0x14000b1d0`
- `USER32!CharNextW` at `0x14000b236`
- `USER32!CharNextW` at `0x14000b25b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rbx
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  LPWSTR v8; // rdx
  WCHAR i; // cx
  const WCHAR *v10; // rbx
  unsigned __int16 v12; // ax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  LPWSTR v16; // rax
  const WCHAR *v17; // rcx
  unsigned __int16 v18; // ax

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
    while ( 1 )
    {
      v13 = v5 - 9;
      if ( !v13 )
        break;
      v14 = v13 - 1;
      if ( !v14 )
        break;
      v15 = v14 - 3;
      if ( !v15 || v15 == 19 )
        break;
      v16 = CharNextW(v4);
      *this = v16;
      if ( &a2[v16 - v4] >= v6 + 4096 )
        return 2147614729LL;
      v17 = v4;
      if ( v4 >= v16 )
      {
        v4 = v16;
      }
      else
      {
        do
        {
          v18 = *v17++;
          *a2++ = v18;
          v4 = *this;
        }
        while ( v17 < *this );
      }
      if ( !*v4 )
        break;
      v5 = *v4;
    }
    *a2 = 0;
    return 0;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  for ( i = *v7; i && (i != 39 || *CharNextW(v8) == 39); i = *v8 )
  {
    v10 = *this;
    if ( **this == 39 )
    {
      v10 = CharNextW(*this);
      *this = v10;
    }
    v8 = CharNextW(v10);
    *this = v8;
    if ( &a2[v8 - v10] >= v6 + 4096 )
      return 2147614729LL;
    while ( v10 < v8 )
    {
      v12 = *v10++;
      *a2++ = v12;
      v8 = (LPWSTR)*this;
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
0x14000b134  push    rbx
0x14000b136  push    rbp
0x14000b137  push    rsi
0x14000b138  push    rdi
0x14000b139  push    r14
0x14000b13b  sub     rsp, 20h
0x14000b13f  mov     rsi, rdx
0x14000b142  mov     rdi, rcx
0x14000b145  mov     rbx, [rdi]
0x14000b148  movzx   ecx, word ptr [rbx]
0x14000b14b  mov     r8d, ecx
0x14000b14e  sub     r8d, 9
0x14000b152  jz      short loc_14000B166
0x14000b154  sub     r8d, 1
0x14000b158  jz      short loc_14000B166
0x14000b15a  sub     r8d, 3
0x14000b15e  jz      short loc_14000B166
0x14000b160  cmp     r8d, 13h
0x14000b164  jnz     short loc_14000B174
0x14000b166  mov     rcx, rbx; lpsz
0x14000b169  call    cs:__imp_CharNextW
0x14000b16f  mov     [rdi], rax
0x14000b172  jmp     short loc_14000B145
0x14000b174  xor     eax, eax
0x14000b176  cmp     ax, cx
0x14000b179  jz      short loc_14000B1F2
0x14000b17b  lea     r14d, [rax+27h]
0x14000b17f  mov     rbp, rsi
0x14000b182  cmp     r14w, cx
0x14000b186  jnz     loc_14000B241
0x14000b18c  mov     rcx, rbx; lpsz
0x14000b18f  call    cs:__imp_CharNextW
0x14000b195  mov     [rdi], rax
0x14000b198  mov     rdx, rax
0x14000b19b  movzx   ecx, word ptr [rax]
0x14000b19e  jmp     short loc_14000B21B
0x14000b1a0  cmp     r14w, cx
0x14000b1a4  jnz     short loc_14000B1B5
0x14000b1a6  mov     rcx, rdx; lpsz
0x14000b1a9  call    cs:__imp_CharNextW
0x14000b1af  cmp     r14w, [rax]
0x14000b1b3  jnz     short loc_14000B226
0x14000b1b5  mov     rbx, [rdi]
0x14000b1b8  cmp     r14w, [rbx]
0x14000b1bc  jnz     short loc_14000B1CD
0x14000b1be  mov     rcx, rbx; lpsz
0x14000b1c1  call    cs:__imp_CharNextW
0x14000b1c7  mov     rbx, rax
0x14000b1ca  mov     [rdi], rax
0x14000b1cd  mov     rcx, rbx; lpsz
0x14000b1d0  call    cs:__imp_CharNextW
0x14000b1d6  mov     rdx, rax
0x14000b1d9  mov     [rdi], rax
0x14000b1dc  sub     rax, rbx
0x14000b1df  sar     rax, 1
0x14000b1e2  lea     rcx, [rsi+rax*2]
0x14000b1e6  lea     rax, [rbp+2000h]
0x14000b1ed  cmp     rcx, rax
0x14000b1f0  jb      short loc_14000B213
0x14000b1f2  mov     eax, 80020009h
0x14000b1f7  add     rsp, 20h
0x14000b1fb  pop     r14
0x14000b1fd  pop     rdi
0x14000b1fe  pop     rsi
0x14000b1ff  pop     rbp
0x14000b200  pop     rbx
0x14000b201  retn
0x14000b202  movzx   eax, word ptr [rbx]
0x14000b205  add     rbx, 2
0x14000b209  mov     [rsi], ax
0x14000b20c  add     rsi, 2
0x14000b210  mov     rdx, [rdi]
0x14000b213  cmp     rbx, rdx
0x14000b216  jb      short loc_14000B202
0x14000b218  movzx   ecx, word ptr [rdx]
0x14000b21b  xor     eax, eax
0x14000b21d  cmp     ax, cx
0x14000b220  jnz     loc_14000B1A0
0x14000b226  mov     rcx, [rdi]
0x14000b229  xor     eax, eax
0x14000b22b  cmp     ax, [rcx]
0x14000b22e  jz      short loc_14000B1F2
0x14000b230  mov     [rsi], ax
0x14000b233  mov     rcx, [rdi]; lpsz
0x14000b236  call    cs:__imp_CharNextW
0x14000b23c  mov     [rdi], rax
0x14000b23f  jmp     short loc_14000B2B5
0x14000b241  movzx   ecx, cx
0x14000b244  sub     ecx, 9
0x14000b247  jz      short loc_14000B2B0
0x14000b249  sub     ecx, 1
0x14000b24c  jz      short loc_14000B2B0
0x14000b24e  sub     ecx, 3
0x14000b251  jz      short loc_14000B2B0
0x14000b253  cmp     ecx, 13h
0x14000b256  jz      short loc_14000B2B0
0x14000b258  mov     rcx, rbx; lpsz
0x14000b25b  call    cs:__imp_CharNextW
0x14000b261  mov     rcx, rax
0x14000b264  mov     [rdi], rax
0x14000b267  sub     rcx, rbx
0x14000b26a  sar     rcx, 1
0x14000b26d  lea     rdx, [rsi+rcx*2]
0x14000b271  lea     rcx, [rbp+2000h]
0x14000b278  cmp     rdx, rcx
0x14000b27b  jnb     loc_14000B1F2
0x14000b281  mov     rcx, rbx
0x14000b284  cmp     rbx, rax
0x14000b287  jnb     short loc_14000B2A1
0x14000b289  movzx   eax, word ptr [rcx]
0x14000b28c  add     rcx, 2
0x14000b290  mov     [rsi], ax
0x14000b293  add     rsi, 2
0x14000b297  mov     rbx, [rdi]
0x14000b29a  cmp     rcx, rbx
0x14000b29d  jb      short loc_14000B289
0x14000b29f  jmp     short loc_14000B2A4
0x14000b2a1  mov     rbx, rax
0x14000b2a4  xor     eax, eax
0x14000b2a6  cmp     ax, [rbx]
0x14000b2a9  jz      short loc_14000B2B0
0x14000b2ab  movzx   ecx, word ptr [rbx]
0x14000b2ae  jmp     short loc_14000B241
0x14000b2b0  xor     eax, eax
0x14000b2b2  mov     [rsi], ax
0x14000b2b5  xor     eax, eax
0x14000b2b7  jmp     loc_14000B1F7
```
