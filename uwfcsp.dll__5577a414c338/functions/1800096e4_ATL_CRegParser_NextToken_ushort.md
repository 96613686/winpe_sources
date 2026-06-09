# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800096e4`
- end: `0x18000987b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008624`
- `0x18000a1b8`
- `0x18000a50c`
- `0x18000b568`

## callees

- `0x1800096e4`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009719`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009747`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009767`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000977f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000978e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800097f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000981e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009719`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009747`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009767`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000977f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000978e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800097f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000981e`

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
0x1800096e4  push    rbx
0x1800096e6  push    rbp
0x1800096e7  push    rsi
0x1800096e8  push    rdi
0x1800096e9  push    r14
0x1800096eb  sub     rsp, 20h
0x1800096ef  mov     rbx, rdx
0x1800096f2  mov     rdi, rcx
0x1800096f5  mov     rsi, [rdi]
0x1800096f8  movzx   ecx, word ptr [rsi]
0x1800096fb  mov     r8d, ecx
0x1800096fe  sub     r8d, 9
0x180009702  jz      short loc_180009716
0x180009704  sub     r8d, 1
0x180009708  jz      short loc_180009716
0x18000970a  sub     r8d, 3
0x18000970e  jz      short loc_180009716
0x180009710  cmp     r8d, 13h
0x180009714  jnz     short loc_180009724
0x180009716  mov     rcx, rsi; lpsz
0x180009719  call    cs:__imp_CharNextW
0x18000971f  mov     [rdi], rax
0x180009722  jmp     short loc_1800096F5
0x180009724  xor     eax, eax
0x180009726  cmp     ax, cx
0x180009729  jz      loc_1800097D4
0x18000972f  lea     r14d, [rax+27h]
0x180009733  lea     rbp, [rbx+2000h]
0x18000973a  cmp     r14w, cx
0x18000973e  jnz     loc_180009804
0x180009744  mov     rcx, rsi; lpsz
0x180009747  call    cs:__imp_CharNextW
0x18000974d  mov     [rdi], rax
0x180009750  mov     rcx, rax; lpsz
0x180009753  movzx   edx, word ptr [rax]
0x180009756  xor     eax, eax
0x180009758  cmp     ax, dx
0x18000975b  jz      loc_1800097E4
0x180009761  cmp     r14w, dx
0x180009765  jnz     short loc_180009773
0x180009767  call    cs:__imp_CharNextW
0x18000976d  cmp     r14w, [rax]
0x180009771  jnz     short loc_1800097E4
0x180009773  mov     rsi, [rdi]
0x180009776  cmp     r14w, [rsi]
0x18000977a  jnz     short loc_18000978B
0x18000977c  mov     rcx, rsi; lpsz
0x18000977f  call    cs:__imp_CharNextW
0x180009785  mov     rsi, rax
0x180009788  mov     [rdi], rax
0x18000978b  mov     rcx, rsi; lpsz
0x18000978e  call    cs:__imp_CharNextW
0x180009794  mov     rdx, rax
0x180009797  mov     [rdi], rax
0x18000979a  sub     rdx, rsi
0x18000979d  sar     rdx, 1
0x1800097a0  lea     rcx, [rdx+1]
0x1800097a4  lea     rcx, [rbx+rcx*2]
0x1800097a8  cmp     rcx, rbp
0x1800097ab  jnb     short loc_1800097D4
0x1800097ad  xor     ecx, ecx
0x1800097af  test    edx, edx
0x1800097b1  jle     short loc_1800097C7
0x1800097b3  movzx   eax, word ptr [rsi]
0x1800097b6  inc     ecx
0x1800097b8  mov     [rbx], ax
0x1800097bb  lea     rsi, [rsi+2]
0x1800097bf  add     rbx, 2
0x1800097c3  cmp     ecx, edx
0x1800097c5  jl      short loc_1800097B3
0x1800097c7  mov     rcx, [rdi]
0x1800097ca  xor     eax, eax
0x1800097cc  movzx   edx, word ptr [rcx]
0x1800097cf  cmp     ax, dx
0x1800097d2  jnz     short loc_180009761
0x1800097d4  mov     eax, 80020009h
0x1800097d9  add     rsp, 20h
0x1800097dd  pop     r14
0x1800097df  pop     rdi
0x1800097e0  pop     rsi
0x1800097e1  pop     rbp
0x1800097e2  pop     rbx
0x1800097e3  retn
0x1800097e4  mov     rcx, [rdi]
0x1800097e7  xor     eax, eax
0x1800097e9  cmp     ax, [rcx]
0x1800097ec  jz      short loc_1800097D4
0x1800097ee  cmp     rbx, rbp
0x1800097f1  jnb     short loc_1800097D4
0x1800097f3  mov     [rbx], ax
0x1800097f6  mov     rcx, [rdi]; lpsz
0x1800097f9  call    cs:__imp_CharNextW
0x1800097ff  mov     [rdi], rax
0x180009802  jmp     short loc_180009874
0x180009804  movzx   ecx, cx
0x180009807  sub     ecx, 9
0x18000980a  jz      short loc_180009866
0x18000980c  sub     ecx, 1
0x18000980f  jz      short loc_180009866
0x180009811  sub     ecx, 3
0x180009814  jz      short loc_180009866
0x180009816  cmp     ecx, 13h
0x180009819  jz      short loc_180009866
0x18000981b  mov     rcx, rsi; lpsz
0x18000981e  call    cs:__imp_CharNextW
0x180009824  mov     rdx, rax
0x180009827  mov     [rdi], rax
0x18000982a  sub     rdx, rsi
0x18000982d  sar     rdx, 1
0x180009830  lea     rcx, [rdx+1]
0x180009834  lea     rcx, [rbx+rcx*2]
0x180009838  cmp     rcx, rbp
0x18000983b  jnb     short loc_1800097D4
0x18000983d  xor     ecx, ecx
0x18000983f  test    edx, edx
0x180009841  jle     short loc_180009857
0x180009843  movzx   eax, word ptr [rsi]
0x180009846  inc     ecx
0x180009848  mov     [rbx], ax
0x18000984b  lea     rsi, [rsi+2]
0x18000984f  add     rbx, 2
0x180009853  cmp     ecx, edx
0x180009855  jl      short loc_180009843
0x180009857  mov     rsi, [rdi]
0x18000985a  xor     eax, eax
0x18000985c  cmp     ax, [rsi]
0x18000985f  jz      short loc_180009866
0x180009861  movzx   ecx, word ptr [rsi]
0x180009864  jmp     short loc_180009804
0x180009866  cmp     rbx, rbp
0x180009869  jnb     loc_1800097D4
0x18000986f  xor     eax, eax
0x180009871  mov     [rbx], ax
0x180009874  xor     eax, eax
0x180009876  jmp     loc_1800097D9
```
