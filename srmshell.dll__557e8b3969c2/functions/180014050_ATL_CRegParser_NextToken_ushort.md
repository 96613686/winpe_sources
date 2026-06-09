# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180014050`
- end: `0x1800141e7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800126ec`
- `0x1800147c0`
- `0x180014b28`
- `0x180015580`

## callees

- `0x180014050`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014085`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140d3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140eb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140fa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014165`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001418a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014085`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140d3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140eb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800140fa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014165`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001418a`

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
0x180014050  push    rbx
0x180014052  push    rbp
0x180014053  push    rsi
0x180014054  push    rdi
0x180014055  push    r14
0x180014057  sub     rsp, 20h
0x18001405b  mov     rbx, rdx
0x18001405e  mov     rdi, rcx
0x180014061  mov     rsi, [rdi]
0x180014064  movzx   ecx, word ptr [rsi]
0x180014067  mov     r8d, ecx
0x18001406a  sub     r8d, 9
0x18001406e  jz      short loc_180014082
0x180014070  sub     r8d, 1
0x180014074  jz      short loc_180014082
0x180014076  sub     r8d, 3
0x18001407a  jz      short loc_180014082
0x18001407c  cmp     r8d, 13h
0x180014080  jnz     short loc_180014090
0x180014082  mov     rcx, rsi; lpsz
0x180014085  call    cs:__imp_CharNextW
0x18001408b  mov     [rdi], rax
0x18001408e  jmp     short loc_180014061
0x180014090  xor     eax, eax
0x180014092  cmp     ax, cx
0x180014095  jz      loc_180014140
0x18001409b  lea     r14d, [rax+27h]
0x18001409f  lea     rbp, [rbx+2000h]
0x1800140a6  cmp     r14w, cx
0x1800140aa  jnz     loc_180014170
0x1800140b0  mov     rcx, rsi; lpsz
0x1800140b3  call    cs:__imp_CharNextW
0x1800140b9  mov     [rdi], rax
0x1800140bc  mov     rcx, rax; lpsz
0x1800140bf  movzx   edx, word ptr [rax]
0x1800140c2  xor     eax, eax
0x1800140c4  cmp     ax, dx
0x1800140c7  jz      loc_180014150
0x1800140cd  cmp     r14w, dx
0x1800140d1  jnz     short loc_1800140DF
0x1800140d3  call    cs:__imp_CharNextW
0x1800140d9  cmp     r14w, [rax]
0x1800140dd  jnz     short loc_180014150
0x1800140df  mov     rsi, [rdi]
0x1800140e2  cmp     r14w, [rsi]
0x1800140e6  jnz     short loc_1800140F7
0x1800140e8  mov     rcx, rsi; lpsz
0x1800140eb  call    cs:__imp_CharNextW
0x1800140f1  mov     rsi, rax
0x1800140f4  mov     [rdi], rax
0x1800140f7  mov     rcx, rsi; lpsz
0x1800140fa  call    cs:__imp_CharNextW
0x180014100  mov     rdx, rax
0x180014103  mov     [rdi], rax
0x180014106  sub     rdx, rsi
0x180014109  sar     rdx, 1
0x18001410c  lea     rcx, [rdx+1]
0x180014110  lea     rcx, [rbx+rcx*2]
0x180014114  cmp     rcx, rbp
0x180014117  jnb     short loc_180014140
0x180014119  xor     ecx, ecx
0x18001411b  test    edx, edx
0x18001411d  jle     short loc_180014133
0x18001411f  movzx   eax, word ptr [rsi]
0x180014122  inc     ecx
0x180014124  mov     [rbx], ax
0x180014127  lea     rsi, [rsi+2]
0x18001412b  add     rbx, 2
0x18001412f  cmp     ecx, edx
0x180014131  jl      short loc_18001411F
0x180014133  mov     rcx, [rdi]
0x180014136  xor     eax, eax
0x180014138  movzx   edx, word ptr [rcx]
0x18001413b  cmp     ax, dx
0x18001413e  jnz     short loc_1800140CD
0x180014140  mov     eax, 80020009h
0x180014145  add     rsp, 20h
0x180014149  pop     r14
0x18001414b  pop     rdi
0x18001414c  pop     rsi
0x18001414d  pop     rbp
0x18001414e  pop     rbx
0x18001414f  retn
0x180014150  mov     rcx, [rdi]
0x180014153  xor     eax, eax
0x180014155  cmp     ax, [rcx]
0x180014158  jz      short loc_180014140
0x18001415a  cmp     rbx, rbp
0x18001415d  jnb     short loc_180014140
0x18001415f  mov     [rbx], ax
0x180014162  mov     rcx, [rdi]; lpsz
0x180014165  call    cs:__imp_CharNextW
0x18001416b  mov     [rdi], rax
0x18001416e  jmp     short loc_1800141E0
0x180014170  movzx   ecx, cx
0x180014173  sub     ecx, 9
0x180014176  jz      short loc_1800141D2
0x180014178  sub     ecx, 1
0x18001417b  jz      short loc_1800141D2
0x18001417d  sub     ecx, 3
0x180014180  jz      short loc_1800141D2
0x180014182  cmp     ecx, 13h
0x180014185  jz      short loc_1800141D2
0x180014187  mov     rcx, rsi; lpsz
0x18001418a  call    cs:__imp_CharNextW
0x180014190  mov     rdx, rax
0x180014193  mov     [rdi], rax
0x180014196  sub     rdx, rsi
0x180014199  sar     rdx, 1
0x18001419c  lea     rcx, [rdx+1]
0x1800141a0  lea     rcx, [rbx+rcx*2]
0x1800141a4  cmp     rcx, rbp
0x1800141a7  jnb     short loc_180014140
0x1800141a9  xor     ecx, ecx
0x1800141ab  test    edx, edx
0x1800141ad  jle     short loc_1800141C3
0x1800141af  movzx   eax, word ptr [rsi]
0x1800141b2  inc     ecx
0x1800141b4  mov     [rbx], ax
0x1800141b7  lea     rsi, [rsi+2]
0x1800141bb  add     rbx, 2
0x1800141bf  cmp     ecx, edx
0x1800141c1  jl      short loc_1800141AF
0x1800141c3  mov     rsi, [rdi]
0x1800141c6  xor     eax, eax
0x1800141c8  cmp     ax, [rsi]
0x1800141cb  jz      short loc_1800141D2
0x1800141cd  movzx   ecx, word ptr [rsi]
0x1800141d0  jmp     short loc_180014170
0x1800141d2  cmp     rbx, rbp
0x1800141d5  jnb     loc_180014140
0x1800141db  xor     eax, eax
0x1800141dd  mov     [rbx], ax
0x1800141e0  xor     eax, eax
0x1800141e2  jmp     loc_180014145
```
