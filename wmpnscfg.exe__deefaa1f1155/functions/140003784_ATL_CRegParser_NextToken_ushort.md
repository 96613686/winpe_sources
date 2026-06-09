# ATL::CRegParser::NextToken(ushort *)

- ea: `0x140003784`
- end: `0x14000391b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400028bc`
- `0x140003e1c`
- `0x140004190`
- `0x1400049f8`

## callees

- `0x140003784`

## import_xrefs

- `USER32!CharNextW` at `0x1400037b9`
- `USER32!CharNextW` at `0x1400037e7`
- `USER32!CharNextW` at `0x140003807`
- `USER32!CharNextW` at `0x14000381f`
- `USER32!CharNextW` at `0x14000382e`
- `USER32!CharNextW` at `0x140003899`
- `USER32!CharNextW` at `0x1400038be`
- `USER32!CharNextW` at `0x1400037b9`
- `USER32!CharNextW` at `0x1400037e7`
- `USER32!CharNextW` at `0x140003807`
- `USER32!CharNextW` at `0x14000381f`
- `USER32!CharNextW` at `0x14000382e`
- `USER32!CharNextW` at `0x140003899`
- `USER32!CharNextW` at `0x1400038be`

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
0x140003784  push    rbx
0x140003786  push    rbp
0x140003787  push    rsi
0x140003788  push    rdi
0x140003789  push    r14
0x14000378b  sub     rsp, 20h
0x14000378f  mov     rbx, rdx
0x140003792  mov     rdi, rcx
0x140003795  mov     rsi, [rdi]
0x140003798  movzx   ecx, word ptr [rsi]
0x14000379b  mov     r8d, ecx
0x14000379e  sub     r8d, 9
0x1400037a2  jz      short loc_1400037B6
0x1400037a4  sub     r8d, 1
0x1400037a8  jz      short loc_1400037B6
0x1400037aa  sub     r8d, 3
0x1400037ae  jz      short loc_1400037B6
0x1400037b0  cmp     r8d, 13h
0x1400037b4  jnz     short loc_1400037C4
0x1400037b6  mov     rcx, rsi; lpsz
0x1400037b9  call    cs:__imp_CharNextW
0x1400037bf  mov     [rdi], rax
0x1400037c2  jmp     short loc_140003795
0x1400037c4  xor     eax, eax
0x1400037c6  cmp     ax, cx
0x1400037c9  jz      loc_140003874
0x1400037cf  lea     r14d, [rax+27h]
0x1400037d3  lea     rbp, [rbx+2000h]
0x1400037da  cmp     r14w, cx
0x1400037de  jnz     loc_1400038A4
0x1400037e4  mov     rcx, rsi; lpsz
0x1400037e7  call    cs:__imp_CharNextW
0x1400037ed  mov     [rdi], rax
0x1400037f0  mov     rcx, rax; lpsz
0x1400037f3  movzx   edx, word ptr [rax]
0x1400037f6  xor     eax, eax
0x1400037f8  cmp     ax, dx
0x1400037fb  jz      loc_140003884
0x140003801  cmp     r14w, dx
0x140003805  jnz     short loc_140003813
0x140003807  call    cs:__imp_CharNextW
0x14000380d  cmp     r14w, [rax]
0x140003811  jnz     short loc_140003884
0x140003813  mov     rsi, [rdi]
0x140003816  cmp     r14w, [rsi]
0x14000381a  jnz     short loc_14000382B
0x14000381c  mov     rcx, rsi; lpsz
0x14000381f  call    cs:__imp_CharNextW
0x140003825  mov     rsi, rax
0x140003828  mov     [rdi], rax
0x14000382b  mov     rcx, rsi; lpsz
0x14000382e  call    cs:__imp_CharNextW
0x140003834  mov     rdx, rax
0x140003837  mov     [rdi], rax
0x14000383a  sub     rdx, rsi
0x14000383d  sar     rdx, 1
0x140003840  lea     rcx, [rdx+1]
0x140003844  lea     rcx, [rbx+rcx*2]
0x140003848  cmp     rcx, rbp
0x14000384b  jnb     short loc_140003874
0x14000384d  xor     ecx, ecx
0x14000384f  test    edx, edx
0x140003851  jle     short loc_140003867
0x140003853  movzx   eax, word ptr [rsi]
0x140003856  inc     ecx
0x140003858  mov     [rbx], ax
0x14000385b  lea     rsi, [rsi+2]
0x14000385f  add     rbx, 2
0x140003863  cmp     ecx, edx
0x140003865  jl      short loc_140003853
0x140003867  mov     rcx, [rdi]
0x14000386a  xor     eax, eax
0x14000386c  movzx   edx, word ptr [rcx]
0x14000386f  cmp     ax, dx
0x140003872  jnz     short loc_140003801
0x140003874  mov     eax, 80020009h
0x140003879  add     rsp, 20h
0x14000387d  pop     r14
0x14000387f  pop     rdi
0x140003880  pop     rsi
0x140003881  pop     rbp
0x140003882  pop     rbx
0x140003883  retn
0x140003884  mov     rcx, [rdi]
0x140003887  xor     eax, eax
0x140003889  cmp     ax, [rcx]
0x14000388c  jz      short loc_140003874
0x14000388e  cmp     rbx, rbp
0x140003891  jnb     short loc_140003874
0x140003893  mov     [rbx], ax
0x140003896  mov     rcx, [rdi]; lpsz
0x140003899  call    cs:__imp_CharNextW
0x14000389f  mov     [rdi], rax
0x1400038a2  jmp     short loc_140003914
0x1400038a4  movzx   ecx, cx
0x1400038a7  sub     ecx, 9
0x1400038aa  jz      short loc_140003906
0x1400038ac  sub     ecx, 1
0x1400038af  jz      short loc_140003906
0x1400038b1  sub     ecx, 3
0x1400038b4  jz      short loc_140003906
0x1400038b6  cmp     ecx, 13h
0x1400038b9  jz      short loc_140003906
0x1400038bb  mov     rcx, rsi; lpsz
0x1400038be  call    cs:__imp_CharNextW
0x1400038c4  mov     rdx, rax
0x1400038c7  mov     [rdi], rax
0x1400038ca  sub     rdx, rsi
0x1400038cd  sar     rdx, 1
0x1400038d0  lea     rcx, [rdx+1]
0x1400038d4  lea     rcx, [rbx+rcx*2]
0x1400038d8  cmp     rcx, rbp
0x1400038db  jnb     short loc_140003874
0x1400038dd  xor     ecx, ecx
0x1400038df  test    edx, edx
0x1400038e1  jle     short loc_1400038F7
0x1400038e3  movzx   eax, word ptr [rsi]
0x1400038e6  inc     ecx
0x1400038e8  mov     [rbx], ax
0x1400038eb  lea     rsi, [rsi+2]
0x1400038ef  add     rbx, 2
0x1400038f3  cmp     ecx, edx
0x1400038f5  jl      short loc_1400038E3
0x1400038f7  mov     rsi, [rdi]
0x1400038fa  xor     eax, eax
0x1400038fc  cmp     ax, [rsi]
0x1400038ff  jz      short loc_140003906
0x140003901  movzx   ecx, word ptr [rsi]
0x140003904  jmp     short loc_1400038A4
0x140003906  cmp     rbx, rbp
0x140003909  jnb     loc_140003874
0x14000390f  xor     eax, eax
0x140003911  mov     [rbx], ax
0x140003914  xor     eax, eax
0x140003916  jmp     loc_140003879
```
