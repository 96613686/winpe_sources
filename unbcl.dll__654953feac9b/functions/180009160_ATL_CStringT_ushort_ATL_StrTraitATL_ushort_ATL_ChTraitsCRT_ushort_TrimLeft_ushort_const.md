# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(ushort const *)

- ea: `0x180009160`
- end: `0x18000924e`
- name: `?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z`
- size: `238`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800080a0`
- `0x180009030`
- `0x180009340`
- `0x18005df90`
- `0x18005e090`

## callees

- `0x1800066cc`
- `0x180008310`
- `0x180009160`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800091ea`
- `msvcrt!memmove_s` at `0x1800091ea`
- `msvcrt!wcschr` at `0x18000918e`
- `msvcrt!wcschr` at `0x18000918e`

## pseudocode

```c
void *const *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(
        void *const *a1,
        const wchar_t *a2,
        __int64 a3)
{
  wchar_t *i; // rbx
  _BYTE *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rbx
  int v9; // esi
  errno_t v10; // eax

  if ( a2 && *a2 )
  {
    for ( i = (wchar_t *)*a1; *i && wcschr(a2, *i); ++i )
      ;
    v6 = *a1;
    if ( i != *(wchar_t **)a1 )
    {
      v7 = *((unsigned int *)v6 - 4);
      v8 = ((char *)i - v6) >> 1;
      if ( (int)((*((_DWORD *)v6 - 3) - v7) | (1 - *((_DWORD *)v6 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v7, a3);
      v9 = *((_DWORD *)*a1 - 4) - v8;
      v10 = memmove_s(*a1, 2LL * (v9 + 1), (char *)*a1 + 2 * (int)v8, 2LL * (v9 + 1));
      if ( v10 )
      {
        if ( v10 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v10 == 22 || v10 == 34 )
          goto LABEL_19;
        if ( v10 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      if ( v9 >= 0 && v9 <= *((_DWORD *)*a1 - 3) )
      {
        *((_DWORD *)*a1 - 4) = v9;
        *((_WORD *)*a1 + v9) = 0;
        return a1;
      }
LABEL_19:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180009160  push    rbx
0x180009162  push    rbp
0x180009163  push    rsi
0x180009164  push    rdi
0x180009165  sub     rsp, 28h
0x180009169  xor     ebp, ebp
0x18000916b  mov     rsi, rdx
0x18000916e  mov     rdi, rcx
0x180009171  test    rdx, rdx
0x180009174  jz      loc_180009221
0x18000917a  cmp     [rdx], bp
0x18000917d  jz      loc_180009221
0x180009183  mov     rbx, [rcx]
0x180009186  jmp     short loc_18000919D
0x180009188  movzx   edx, ax; Ch
0x18000918b  mov     rcx, rsi; Str
0x18000918e  call    cs:__imp_wcschr
0x180009194  test    rax, rax
0x180009197  jz      short loc_1800091A5
0x180009199  add     rbx, 2
0x18000919d  movzx   eax, word ptr [rbx]
0x1800091a0  test    ax, ax
0x1800091a3  jnz     short loc_180009188
0x1800091a5  mov     rax, [rdi]
0x1800091a8  cmp     rbx, rax
0x1800091ab  jz      short loc_180009221
0x1800091ad  mov     edx, [rax-10h]
0x1800091b0  sub     rbx, rax
0x1800091b3  mov     ecx, 1
0x1800091b8  sar     rbx, 1
0x1800091bb  sub     ecx, [rax-8]
0x1800091be  mov     eax, [rax-0Ch]
0x1800091c1  sub     eax, edx
0x1800091c3  or      ecx, eax
0x1800091c5  jge     short loc_1800091CF
0x1800091c7  mov     rcx, rdi
0x1800091ca  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800091cf  mov     rcx, [rdi]; Destination
0x1800091d2  mov     esi, [rcx-10h]
0x1800091d5  sub     esi, ebx
0x1800091d7  lea     eax, [rsi+1]
0x1800091da  movsxd  rdx, eax
0x1800091dd  movsxd  rax, ebx
0x1800091e0  add     rdx, rdx; DestinationSize
0x1800091e3  mov     r9, rdx; SourceSize
0x1800091e6  lea     r8, [rcx+rax*2]; Source
0x1800091ea  call    cs:__imp_memmove_s
0x1800091f0  test    eax, eax
0x1800091f2  jz      short loc_180009208
0x1800091f4  cmp     eax, 0Ch
0x1800091f7  jz      short loc_180009243
0x1800091f9  cmp     eax, 16h
0x1800091fc  jz      short loc_18000922D
0x1800091fe  cmp     eax, 22h ; '"'
0x180009201  jz      short loc_18000922D
0x180009203  cmp     eax, 50h ; 'P'
0x180009206  jnz     short loc_180009238
0x180009208  test    esi, esi
0x18000920a  js      short loc_18000922D
0x18000920c  mov     rax, [rdi]
0x18000920f  cmp     esi, [rax-0Ch]
0x180009212  jg      short loc_18000922D
0x180009214  mov     [rax-10h], esi
0x180009217  mov     rcx, [rdi]
0x18000921a  movsxd  rdx, esi
0x18000921d  mov     [rcx+rdx*2], bp
0x180009221  mov     rax, rdi
0x180009224  add     rsp, 28h
0x180009228  pop     rdi
0x180009229  pop     rsi
0x18000922a  pop     rbp
0x18000922b  pop     rbx
0x18000922c  retn
0x18000922d  mov     ecx, 80070057h; int
0x180009232  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009238  mov     ecx, 80004005h; int
0x18000923d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009243  mov     ecx, 8007000Eh; int
0x180009248  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
