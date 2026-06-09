# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180008700`
- end: `0x180008897`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007534`
- `0x180008ce8`
- `0x18000902c`
- `0x1800098b4`

## callees

- `0x180008700`

## import_xrefs

- `USER32!CharNextW` at `0x180008735`
- `USER32!CharNextW` at `0x180008763`
- `USER32!CharNextW` at `0x180008783`
- `USER32!CharNextW` at `0x18000879b`
- `USER32!CharNextW` at `0x1800087aa`
- `USER32!CharNextW` at `0x180008815`
- `USER32!CharNextW` at `0x18000883a`
- `USER32!CharNextW` at `0x180008735`
- `USER32!CharNextW` at `0x180008763`
- `USER32!CharNextW` at `0x180008783`
- `USER32!CharNextW` at `0x18000879b`
- `USER32!CharNextW` at `0x1800087aa`
- `USER32!CharNextW` at `0x180008815`
- `USER32!CharNextW` at `0x18000883a`

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
0x180008700  push    rbx
0x180008702  push    rbp
0x180008703  push    rsi
0x180008704  push    rdi
0x180008705  push    r14
0x180008707  sub     rsp, 20h
0x18000870b  mov     rbx, rdx
0x18000870e  mov     rdi, rcx
0x180008711  mov     rsi, [rdi]
0x180008714  movzx   ecx, word ptr [rsi]
0x180008717  mov     r8d, ecx
0x18000871a  sub     r8d, 9
0x18000871e  jz      short loc_180008732
0x180008720  sub     r8d, 1
0x180008724  jz      short loc_180008732
0x180008726  sub     r8d, 3
0x18000872a  jz      short loc_180008732
0x18000872c  cmp     r8d, 13h
0x180008730  jnz     short loc_180008740
0x180008732  mov     rcx, rsi; lpsz
0x180008735  call    cs:__imp_CharNextW
0x18000873b  mov     [rdi], rax
0x18000873e  jmp     short loc_180008711
0x180008740  xor     eax, eax
0x180008742  cmp     ax, cx
0x180008745  jz      loc_1800087F0
0x18000874b  lea     r14d, [rax+27h]
0x18000874f  lea     rbp, [rbx+2000h]
0x180008756  cmp     r14w, cx
0x18000875a  jnz     loc_180008820
0x180008760  mov     rcx, rsi; lpsz
0x180008763  call    cs:__imp_CharNextW
0x180008769  mov     [rdi], rax
0x18000876c  mov     rcx, rax; lpsz
0x18000876f  movzx   edx, word ptr [rax]
0x180008772  xor     eax, eax
0x180008774  cmp     ax, dx
0x180008777  jz      loc_180008800
0x18000877d  cmp     r14w, dx
0x180008781  jnz     short loc_18000878F
0x180008783  call    cs:__imp_CharNextW
0x180008789  cmp     r14w, [rax]
0x18000878d  jnz     short loc_180008800
0x18000878f  mov     rsi, [rdi]
0x180008792  cmp     r14w, [rsi]
0x180008796  jnz     short loc_1800087A7
0x180008798  mov     rcx, rsi; lpsz
0x18000879b  call    cs:__imp_CharNextW
0x1800087a1  mov     rsi, rax
0x1800087a4  mov     [rdi], rax
0x1800087a7  mov     rcx, rsi; lpsz
0x1800087aa  call    cs:__imp_CharNextW
0x1800087b0  mov     rdx, rax
0x1800087b3  mov     [rdi], rax
0x1800087b6  sub     rdx, rsi
0x1800087b9  sar     rdx, 1
0x1800087bc  lea     rcx, [rdx+1]
0x1800087c0  lea     rcx, [rbx+rcx*2]
0x1800087c4  cmp     rcx, rbp
0x1800087c7  jnb     short loc_1800087F0
0x1800087c9  xor     ecx, ecx
0x1800087cb  test    edx, edx
0x1800087cd  jle     short loc_1800087E3
0x1800087cf  movzx   eax, word ptr [rsi]
0x1800087d2  inc     ecx
0x1800087d4  mov     [rbx], ax
0x1800087d7  lea     rsi, [rsi+2]
0x1800087db  add     rbx, 2
0x1800087df  cmp     ecx, edx
0x1800087e1  jl      short loc_1800087CF
0x1800087e3  mov     rcx, [rdi]
0x1800087e6  xor     eax, eax
0x1800087e8  movzx   edx, word ptr [rcx]
0x1800087eb  cmp     ax, dx
0x1800087ee  jnz     short loc_18000877D
0x1800087f0  mov     eax, 80020009h
0x1800087f5  add     rsp, 20h
0x1800087f9  pop     r14
0x1800087fb  pop     rdi
0x1800087fc  pop     rsi
0x1800087fd  pop     rbp
0x1800087fe  pop     rbx
0x1800087ff  retn
0x180008800  mov     rcx, [rdi]
0x180008803  xor     eax, eax
0x180008805  cmp     ax, [rcx]
0x180008808  jz      short loc_1800087F0
0x18000880a  cmp     rbx, rbp
0x18000880d  jnb     short loc_1800087F0
0x18000880f  mov     [rbx], ax
0x180008812  mov     rcx, [rdi]; lpsz
0x180008815  call    cs:__imp_CharNextW
0x18000881b  mov     [rdi], rax
0x18000881e  jmp     short loc_180008890
0x180008820  movzx   ecx, cx
0x180008823  sub     ecx, 9
0x180008826  jz      short loc_180008882
0x180008828  sub     ecx, 1
0x18000882b  jz      short loc_180008882
0x18000882d  sub     ecx, 3
0x180008830  jz      short loc_180008882
0x180008832  cmp     ecx, 13h
0x180008835  jz      short loc_180008882
0x180008837  mov     rcx, rsi; lpsz
0x18000883a  call    cs:__imp_CharNextW
0x180008840  mov     rdx, rax
0x180008843  mov     [rdi], rax
0x180008846  sub     rdx, rsi
0x180008849  sar     rdx, 1
0x18000884c  lea     rcx, [rdx+1]
0x180008850  lea     rcx, [rbx+rcx*2]
0x180008854  cmp     rcx, rbp
0x180008857  jnb     short loc_1800087F0
0x180008859  xor     ecx, ecx
0x18000885b  test    edx, edx
0x18000885d  jle     short loc_180008873
0x18000885f  movzx   eax, word ptr [rsi]
0x180008862  inc     ecx
0x180008864  mov     [rbx], ax
0x180008867  lea     rsi, [rsi+2]
0x18000886b  add     rbx, 2
0x18000886f  cmp     ecx, edx
0x180008871  jl      short loc_18000885F
0x180008873  mov     rsi, [rdi]
0x180008876  xor     eax, eax
0x180008878  cmp     ax, [rsi]
0x18000887b  jz      short loc_180008882
0x18000887d  movzx   ecx, word ptr [rsi]
0x180008880  jmp     short loc_180008820
0x180008882  cmp     rbx, rbp
0x180008885  jnb     loc_1800087F0
0x18000888b  xor     eax, eax
0x18000888d  mov     [rbx], ax
0x180008890  xor     eax, eax
0x180008892  jmp     loc_1800087F5
```
