# ATL::CRegParser::NextToken(char *)

- ea: `0x180011060`
- end: `0x1800111c2`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAD@Z`
- size: `354`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f804`
- `0x18001167c`
- `0x180011b0c`
- `0x180012af8`

## callees

- `0x180011060`

## import_xrefs

- `USER32!CharNextA` at `0x180011093`
- `USER32!CharNextA` at `0x1800110b9`
- `USER32!CharNextA` at `0x1800110d0`
- `USER32!CharNextA` at `0x1800110e6`
- `USER32!CharNextA` at `0x1800110f5`
- `USER32!CharNextA` at `0x180011150`
- `USER32!CharNextA` at `0x180011175`
- `USER32!CharNextA` at `0x180011093`
- `USER32!CharNextA` at `0x1800110b9`
- `USER32!CharNextA` at `0x1800110d0`
- `USER32!CharNextA` at `0x1800110e6`
- `USER32!CharNextA` at `0x1800110f5`
- `USER32!CharNextA` at `0x180011150`
- `USER32!CharNextA` at `0x180011175`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCSTR *this, char *a2)
{
  const CHAR *v4; // rsi
  CHAR v5; // cl
  char *v6; // rbp
  LPSTR v7; // rax
  CHAR v8; // cl
  const CHAR *v9; // rsi
  LPSTR v10; // rax
  int v11; // edx
  int j; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  LPSTR v17; // rax
  int v18; // edx
  int i; // ecx

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextA(*this);
  }
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    do
    {
      v14 = v5 - 9;
      if ( !v14 )
        break;
      v15 = v14 - 1;
      if ( !v15 )
        break;
      v16 = v15 - 3;
      if ( !v16 || v16 == 19 )
        break;
      v17 = CharNextA(v4);
      *this = v17;
      v18 = (_DWORD)v17 - (_DWORD)v4;
      if ( &a2[v17 - v4 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < v18; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *this;
      v5 = **this;
    }
    while ( v5 );
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextA(*this);
  *this = v7;
  v8 = *v7;
  if ( *v7 )
  {
    while ( v8 != 39 || *CharNextA(v7) == 39 )
    {
      v9 = *this;
      if ( **this == 39 )
      {
        v9 = CharNextA(*this);
        *this = v9;
      }
      v10 = CharNextA(v9);
      *this = v10;
      v11 = (_DWORD)v10 - (_DWORD)v9;
      if ( &a2[v10 - v9 + 1] < v6 )
      {
        for ( j = 0; j < v11; ++a2 )
        {
          ++j;
          *a2 = *v9++;
        }
        v7 = (LPSTR)*this;
        v8 = **this;
        if ( v8 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextA(*this);
  return 0;
}

```

## disassembly

```asm
0x180011060  push    rbx
0x180011062  push    rbp
0x180011063  push    rsi
0x180011064  push    rdi
0x180011065  sub     rsp, 28h
0x180011069  mov     rbx, rdx
0x18001106c  mov     rdi, rcx
0x18001106f  mov     rsi, [rdi]
0x180011072  movsx   ecx, byte ptr [rsi]
0x180011075  mov     r8d, ecx
0x180011078  sub     r8d, 9
0x18001107c  jz      short loc_180011090
0x18001107e  sub     r8d, 1
0x180011082  jz      short loc_180011090
0x180011084  sub     r8d, 3
0x180011088  jz      short loc_180011090
0x18001108a  cmp     r8d, 13h
0x18001108e  jnz     short loc_18001109E
0x180011090  mov     rcx, rsi; lpsz
0x180011093  call    cs:__imp_CharNextA
0x180011099  mov     [rdi], rax
0x18001109c  jmp     short loc_18001106F
0x18001109e  test    cl, cl
0x1800110a0  jz      loc_18001112F
0x1800110a6  lea     rbp, [rbx+1000h]
0x1800110ad  cmp     cl, 27h ; '''
0x1800110b0  jnz     loc_18001115B
0x1800110b6  mov     rcx, rsi; lpsz
0x1800110b9  call    cs:__imp_CharNextA
0x1800110bf  mov     [rdi], rax
0x1800110c2  mov     cl, [rax]
0x1800110c4  test    cl, cl
0x1800110c6  jz      short loc_18001113D
0x1800110c8  cmp     cl, 27h ; '''
0x1800110cb  jnz     short loc_1800110DB
0x1800110cd  mov     rcx, rax; lpsz
0x1800110d0  call    cs:__imp_CharNextA
0x1800110d6  cmp     byte ptr [rax], 27h ; '''
0x1800110d9  jnz     short loc_18001113D
0x1800110db  mov     rsi, [rdi]
0x1800110de  cmp     byte ptr [rsi], 27h ; '''
0x1800110e1  jnz     short loc_1800110F2
0x1800110e3  mov     rcx, rsi; lpsz
0x1800110e6  call    cs:__imp_CharNextA
0x1800110ec  mov     rsi, rax
0x1800110ef  mov     [rdi], rax
0x1800110f2  mov     rcx, rsi; lpsz
0x1800110f5  call    cs:__imp_CharNextA
0x1800110fb  mov     rdx, rax
0x1800110fe  mov     [rdi], rax
0x180011101  sub     rdx, rsi
0x180011104  lea     rcx, [rdx+1]
0x180011108  add     rcx, rbx
0x18001110b  cmp     rcx, rbp
0x18001110e  jnb     short loc_18001112F
0x180011110  xor     ecx, ecx
0x180011112  test    edx, edx
0x180011114  jle     short loc_180011126
0x180011116  mov     al, [rsi]
0x180011118  inc     ecx
0x18001111a  mov     [rbx], al
0x18001111c  inc     rsi
0x18001111f  inc     rbx
0x180011122  cmp     ecx, edx
0x180011124  jl      short loc_180011116
0x180011126  mov     rax, [rdi]
0x180011129  mov     cl, [rax]
0x18001112b  test    cl, cl
0x18001112d  jnz     short loc_1800110C8
0x18001112f  mov     eax, 80020009h
0x180011134  add     rsp, 28h
0x180011138  pop     rdi
0x180011139  pop     rsi
0x18001113a  pop     rbp
0x18001113b  pop     rbx
0x18001113c  retn
0x18001113d  mov     rax, [rdi]
0x180011140  cmp     byte ptr [rax], 0
0x180011143  jz      short loc_18001112F
0x180011145  cmp     rbx, rbp
0x180011148  jnb     short loc_18001112F
0x18001114a  mov     byte ptr [rbx], 0
0x18001114d  mov     rcx, [rdi]; lpsz
0x180011150  call    cs:__imp_CharNextA
0x180011156  mov     [rdi], rax
0x180011159  jmp     short loc_1800111BB
0x18001115b  movsx   ecx, cl
0x18001115e  sub     ecx, 9
0x180011161  jz      short loc_1800111AF
0x180011163  sub     ecx, 1
0x180011166  jz      short loc_1800111AF
0x180011168  sub     ecx, 3
0x18001116b  jz      short loc_1800111AF
0x18001116d  cmp     ecx, 13h
0x180011170  jz      short loc_1800111AF
0x180011172  mov     rcx, rsi; lpsz
0x180011175  call    cs:__imp_CharNextA
0x18001117b  mov     rdx, rax
0x18001117e  mov     [rdi], rax
0x180011181  sub     rdx, rsi
0x180011184  lea     rcx, [rdx+1]
0x180011188  add     rcx, rbx
0x18001118b  cmp     rcx, rbp
0x18001118e  jnb     short loc_18001112F
0x180011190  xor     ecx, ecx
0x180011192  test    edx, edx
0x180011194  jle     short loc_1800111A6
0x180011196  mov     al, [rsi]
0x180011198  inc     ecx
0x18001119a  mov     [rbx], al
0x18001119c  inc     rsi
0x18001119f  inc     rbx
0x1800111a2  cmp     ecx, edx
0x1800111a4  jl      short loc_180011196
0x1800111a6  mov     rsi, [rdi]
0x1800111a9  mov     cl, [rsi]
0x1800111ab  test    cl, cl
0x1800111ad  jnz     short loc_18001115B
0x1800111af  cmp     rbx, rbp
0x1800111b2  jnb     loc_18001112F
0x1800111b8  mov     byte ptr [rbx], 0
0x1800111bb  xor     eax, eax
0x1800111bd  jmp     loc_180011134
```
