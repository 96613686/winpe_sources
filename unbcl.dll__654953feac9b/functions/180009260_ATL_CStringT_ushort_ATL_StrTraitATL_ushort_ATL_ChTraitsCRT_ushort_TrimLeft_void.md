# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(void)

- ea: `0x180009260`
- end: `0x18000933a`
- name: `?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ`
- size: `218`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800080a0`
- `0x180009060`
- `0x180009340`
- `0x18005df90`
- `0x18005e090`

## callees

- `0x1800066cc`
- `0x180008310`
- `0x180009260`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800092cd`
- `msvcrt!memmove_s` at `0x1800092cd`
- `msvcrt!iswspace` at `0x18000927e`
- `msvcrt!iswspace` at `0x18000927e`

## pseudocode

```c
void *const *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(
        void *const *a1)
{
  wint_t *i; // rbx
  __int64 v3; // r8
  _BYTE *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rbx
  int v7; // esi
  errno_t v8; // eax

  for ( i = (wint_t *)*a1; iswspace(*i); ++i )
    ;
  v4 = *a1;
  if ( i != *(wint_t **)a1 )
  {
    v5 = *((unsigned int *)v4 - 4);
    v6 = ((char *)i - v4) >> 1;
    if ( (int)((*((_DWORD *)v4 - 3) - v5) | (1 - *((_DWORD *)v4 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v5, v3);
    v7 = *((_DWORD *)*a1 - 4) - v6;
    v8 = memmove_s(*a1, 2LL * (v7 + 1), (char *)*a1 + 2 * (int)v6, 2LL * (v7 + 1));
    if ( v8 )
    {
      if ( v8 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v8 == 22 || v8 == 34 )
        goto LABEL_16;
      if ( v8 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    if ( v7 >= 0 && v7 <= *((_DWORD *)*a1 - 3) )
    {
      *((_DWORD *)*a1 - 4) = v7;
      *((_WORD *)*a1 + v7) = 0;
      return a1;
    }
LABEL_16:
    ATL::AtlThrowImpl(-2147024809);
  }
  return a1;
}

```

## disassembly

```asm
0x180009260  mov     [rsp+arg_0], rbx
0x180009265  mov     [rsp+arg_8], rsi
0x18000926a  push    rdi
0x18000926b  sub     rsp, 20h
0x18000926f  mov     rbx, [rcx]
0x180009272  mov     rdi, rcx
0x180009275  jmp     short loc_18000927B
0x180009277  add     rbx, 2
0x18000927b  movzx   ecx, word ptr [rbx]; C
0x18000927e  call    cs:__imp_iswspace
0x180009284  test    eax, eax
0x180009286  jnz     short loc_180009277
0x180009288  mov     rax, [rdi]
0x18000928b  cmp     rbx, rax
0x18000928e  jz      short loc_180009306
0x180009290  mov     edx, [rax-10h]
0x180009293  sub     rbx, rax
0x180009296  mov     ecx, 1
0x18000929b  sar     rbx, 1
0x18000929e  sub     ecx, [rax-8]
0x1800092a1  mov     eax, [rax-0Ch]
0x1800092a4  sub     eax, edx
0x1800092a6  or      ecx, eax
0x1800092a8  jge     short loc_1800092B2
0x1800092aa  mov     rcx, rdi
0x1800092ad  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800092b2  mov     rcx, [rdi]; Destination
0x1800092b5  mov     esi, [rcx-10h]
0x1800092b8  sub     esi, ebx
0x1800092ba  lea     eax, [rsi+1]
0x1800092bd  movsxd  rdx, eax
0x1800092c0  movsxd  rax, ebx
0x1800092c3  add     rdx, rdx; DestinationSize
0x1800092c6  mov     r9, rdx; SourceSize
0x1800092c9  lea     r8, [rcx+rax*2]; Source
0x1800092cd  call    cs:__imp_memmove_s
0x1800092d3  test    eax, eax
0x1800092d5  jz      short loc_1800092EB
0x1800092d7  cmp     eax, 0Ch
0x1800092da  jz      short loc_18000932F
0x1800092dc  cmp     eax, 16h
0x1800092df  jz      short loc_180009319
0x1800092e1  cmp     eax, 22h ; '"'
0x1800092e4  jz      short loc_180009319
0x1800092e6  cmp     eax, 50h ; 'P'
0x1800092e9  jnz     short loc_180009324
0x1800092eb  test    esi, esi
0x1800092ed  js      short loc_180009319
0x1800092ef  mov     rax, [rdi]
0x1800092f2  cmp     esi, [rax-0Ch]
0x1800092f5  jg      short loc_180009319
0x1800092f7  mov     [rax-10h], esi
0x1800092fa  xor     eax, eax
0x1800092fc  mov     rcx, [rdi]
0x1800092ff  movsxd  rdx, esi
0x180009302  mov     [rcx+rdx*2], ax
0x180009306  mov     rbx, [rsp+28h+arg_0]
0x18000930b  mov     rax, rdi
0x18000930e  mov     rsi, [rsp+28h+arg_8]
0x180009313  add     rsp, 20h
0x180009317  pop     rdi
0x180009318  retn
0x180009319  mov     ecx, 80070057h; int
0x18000931e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009324  mov     ecx, 80004005h; int
0x180009329  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000932f  mov     ecx, 8007000Eh; int
0x180009334  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
