# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180019370`
- end: `0x1800194c7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180016224`
- `0x180019cfc`
- `0x18001a0e0`
- `0x18001ab28`

## callees

- `0x180019370`
- `0x18001abbc`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193c2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193e9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019441`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019470`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193c2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800193e9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019441`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019470`

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
0x180019370  push    rbx
0x180019372  push    rbp
0x180019373  push    rsi
0x180019374  push    rdi
0x180019375  push    r14
0x180019377  sub     rsp, 20h
0x18001937b  mov     rbx, rdx
0x18001937e  mov     rdi, rcx
0x180019381  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180019386  mov     rcx, [rdi]; lpsz
0x180019389  xor     eax, eax
0x18001938b  cmp     ax, [rcx]
0x18001938e  jz      loc_1800194B7
0x180019394  lea     r14d, [rax+27h]
0x180019398  lea     rbp, [rbx+2000h]
0x18001939f  cmp     r14w, [rcx]
0x1800193a3  jnz     loc_18001944C
0x1800193a9  call    cs:__imp_CharNextW
0x1800193af  mov     [rdi], rax
0x1800193b2  mov     rcx, [rdi]; lpsz
0x1800193b5  xor     eax, eax
0x1800193b7  cmp     ax, [rcx]
0x1800193ba  jz      short loc_180019428
0x1800193bc  cmp     r14w, [rcx]
0x1800193c0  jnz     short loc_1800193CE
0x1800193c2  call    cs:__imp_CharNextW
0x1800193c8  cmp     r14w, [rax]
0x1800193cc  jnz     short loc_180019428
0x1800193ce  mov     rsi, [rdi]
0x1800193d1  cmp     r14w, [rsi]
0x1800193d5  jnz     short loc_1800193E6
0x1800193d7  mov     rcx, rsi; lpsz
0x1800193da  call    cs:__imp_CharNextW
0x1800193e0  mov     rsi, rax
0x1800193e3  mov     [rdi], rax
0x1800193e6  mov     rcx, rsi; lpsz
0x1800193e9  call    cs:__imp_CharNextW
0x1800193ef  mov     rdx, rax
0x1800193f2  mov     [rdi], rax
0x1800193f5  sub     rdx, rsi
0x1800193f8  sar     rdx, 1
0x1800193fb  lea     rcx, [rdx+1]
0x1800193ff  lea     rcx, [rbx+rcx*2]
0x180019403  cmp     rcx, rbp
0x180019406  jnb     loc_1800194B7
0x18001940c  xor     ecx, ecx
0x18001940e  test    edx, edx
0x180019410  jle     short loc_1800193B2
0x180019412  movzx   eax, word ptr [rsi]
0x180019415  inc     ecx
0x180019417  mov     [rbx], ax
0x18001941a  lea     rsi, [rsi+2]
0x18001941e  add     rbx, 2
0x180019422  cmp     ecx, edx
0x180019424  jl      short loc_180019412
0x180019426  jmp     short loc_1800193B2
0x180019428  mov     rcx, [rdi]
0x18001942b  xor     eax, eax
0x18001942d  cmp     ax, [rcx]
0x180019430  jz      loc_1800194B7
0x180019436  cmp     rbx, rbp
0x180019439  jnb     short loc_1800194B7
0x18001943b  mov     [rbx], ax
0x18001943e  mov     rcx, [rdi]; lpsz
0x180019441  call    cs:__imp_CharNextW
0x180019447  mov     [rdi], rax
0x18001944a  jmp     short loc_1800194B3
0x18001944c  mov     rsi, [rdi]
0x18001944f  xor     eax, eax
0x180019451  cmp     ax, [rsi]
0x180019454  jz      short loc_1800194AB
0x180019456  movzx   ecx, word ptr [rsi]
0x180019459  sub     ecx, 9
0x18001945c  jz      short loc_1800194AB
0x18001945e  sub     ecx, 1
0x180019461  jz      short loc_1800194AB
0x180019463  sub     ecx, 3
0x180019466  jz      short loc_1800194AB
0x180019468  cmp     ecx, 13h
0x18001946b  jz      short loc_1800194AB
0x18001946d  mov     rcx, rsi; lpsz
0x180019470  call    cs:__imp_CharNextW
0x180019476  mov     rdx, rax
0x180019479  mov     [rdi], rax
0x18001947c  sub     rdx, rsi
0x18001947f  sar     rdx, 1
0x180019482  lea     rcx, [rdx+1]
0x180019486  lea     rcx, [rbx+rcx*2]
0x18001948a  cmp     rcx, rbp
0x18001948d  jnb     short loc_1800194B7
0x18001948f  xor     ecx, ecx
0x180019491  test    edx, edx
0x180019493  jle     short loc_18001944C
0x180019495  movzx   eax, word ptr [rsi]
0x180019498  inc     ecx
0x18001949a  mov     [rbx], ax
0x18001949d  lea     rsi, [rsi+2]
0x1800194a1  add     rbx, 2
0x1800194a5  cmp     ecx, edx
0x1800194a7  jl      short loc_180019495
0x1800194a9  jmp     short loc_18001944C
0x1800194ab  cmp     rbx, rbp
0x1800194ae  jnb     short loc_1800194B7
0x1800194b0  mov     [rbx], ax
0x1800194b3  xor     eax, eax
0x1800194b5  jmp     short loc_1800194BC
0x1800194b7  mov     eax, 80020009h
0x1800194bc  add     rsp, 20h
0x1800194c0  pop     r14
0x1800194c2  pop     rdi
0x1800194c3  pop     rsi
0x1800194c4  pop     rbp
0x1800194c5  pop     rbx
0x1800194c6  retn
```
