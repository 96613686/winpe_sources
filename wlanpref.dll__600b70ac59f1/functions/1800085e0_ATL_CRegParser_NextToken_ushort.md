# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800085e0`
- end: `0x180008737`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000434c`
- `0x18000ab4c`
- `0x18000af10`
- `0x18000b9cc`

## callees

- `0x1800085e0`
- `0x18000ba60`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008619`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008632`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000864a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008659`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086b1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086e0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008619`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008632`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000864a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008659`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086b1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086e0`

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
0x1800085e0  push    rbx
0x1800085e2  push    rbp
0x1800085e3  push    rsi
0x1800085e4  push    rdi
0x1800085e5  push    r14
0x1800085e7  sub     rsp, 20h
0x1800085eb  mov     rbx, rdx
0x1800085ee  mov     rdi, rcx
0x1800085f1  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800085f6  mov     rcx, [rdi]; lpsz
0x1800085f9  xor     eax, eax
0x1800085fb  cmp     ax, [rcx]
0x1800085fe  jz      loc_180008727
0x180008604  lea     r14d, [rax+27h]
0x180008608  lea     rbp, [rbx+2000h]
0x18000860f  cmp     r14w, [rcx]
0x180008613  jnz     loc_1800086BC
0x180008619  call    cs:__imp_CharNextW
0x18000861f  mov     [rdi], rax
0x180008622  mov     rcx, [rdi]; lpsz
0x180008625  xor     eax, eax
0x180008627  cmp     ax, [rcx]
0x18000862a  jz      short loc_180008698
0x18000862c  cmp     r14w, [rcx]
0x180008630  jnz     short loc_18000863E
0x180008632  call    cs:__imp_CharNextW
0x180008638  cmp     r14w, [rax]
0x18000863c  jnz     short loc_180008698
0x18000863e  mov     rsi, [rdi]
0x180008641  cmp     r14w, [rsi]
0x180008645  jnz     short loc_180008656
0x180008647  mov     rcx, rsi; lpsz
0x18000864a  call    cs:__imp_CharNextW
0x180008650  mov     rsi, rax
0x180008653  mov     [rdi], rax
0x180008656  mov     rcx, rsi; lpsz
0x180008659  call    cs:__imp_CharNextW
0x18000865f  mov     rdx, rax
0x180008662  mov     [rdi], rax
0x180008665  sub     rdx, rsi
0x180008668  sar     rdx, 1
0x18000866b  lea     rcx, [rdx+1]
0x18000866f  lea     rcx, [rbx+rcx*2]
0x180008673  cmp     rcx, rbp
0x180008676  jnb     loc_180008727
0x18000867c  xor     ecx, ecx
0x18000867e  test    edx, edx
0x180008680  jle     short loc_180008622
0x180008682  movzx   eax, word ptr [rsi]
0x180008685  inc     ecx
0x180008687  mov     [rbx], ax
0x18000868a  lea     rsi, [rsi+2]
0x18000868e  add     rbx, 2
0x180008692  cmp     ecx, edx
0x180008694  jl      short loc_180008682
0x180008696  jmp     short loc_180008622
0x180008698  mov     rcx, [rdi]
0x18000869b  xor     eax, eax
0x18000869d  cmp     ax, [rcx]
0x1800086a0  jz      loc_180008727
0x1800086a6  cmp     rbx, rbp
0x1800086a9  jnb     short loc_180008727
0x1800086ab  mov     [rbx], ax
0x1800086ae  mov     rcx, [rdi]; lpsz
0x1800086b1  call    cs:__imp_CharNextW
0x1800086b7  mov     [rdi], rax
0x1800086ba  jmp     short loc_180008723
0x1800086bc  mov     rsi, [rdi]
0x1800086bf  xor     eax, eax
0x1800086c1  cmp     ax, [rsi]
0x1800086c4  jz      short loc_18000871B
0x1800086c6  movzx   ecx, word ptr [rsi]
0x1800086c9  sub     ecx, 9
0x1800086cc  jz      short loc_18000871B
0x1800086ce  sub     ecx, 1
0x1800086d1  jz      short loc_18000871B
0x1800086d3  sub     ecx, 3
0x1800086d6  jz      short loc_18000871B
0x1800086d8  cmp     ecx, 13h
0x1800086db  jz      short loc_18000871B
0x1800086dd  mov     rcx, rsi; lpsz
0x1800086e0  call    cs:__imp_CharNextW
0x1800086e6  mov     rdx, rax
0x1800086e9  mov     [rdi], rax
0x1800086ec  sub     rdx, rsi
0x1800086ef  sar     rdx, 1
0x1800086f2  lea     rcx, [rdx+1]
0x1800086f6  lea     rcx, [rbx+rcx*2]
0x1800086fa  cmp     rcx, rbp
0x1800086fd  jnb     short loc_180008727
0x1800086ff  xor     ecx, ecx
0x180008701  test    edx, edx
0x180008703  jle     short loc_1800086BC
0x180008705  movzx   eax, word ptr [rsi]
0x180008708  inc     ecx
0x18000870a  mov     [rbx], ax
0x18000870d  lea     rsi, [rsi+2]
0x180008711  add     rbx, 2
0x180008715  cmp     ecx, edx
0x180008717  jl      short loc_180008705
0x180008719  jmp     short loc_1800086BC
0x18000871b  cmp     rbx, rbp
0x18000871e  jnb     short loc_180008727
0x180008720  mov     [rbx], ax
0x180008723  xor     eax, eax
0x180008725  jmp     short loc_18000872C
0x180008727  mov     eax, 80020009h
0x18000872c  add     rsp, 20h
0x180008730  pop     r14
0x180008732  pop     rdi
0x180008733  pop     rsi
0x180008734  pop     rbp
0x180008735  pop     rbx
0x180008736  retn
```
