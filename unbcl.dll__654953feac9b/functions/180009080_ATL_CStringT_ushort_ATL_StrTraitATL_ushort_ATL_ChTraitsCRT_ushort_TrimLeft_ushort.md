# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(ushort)

- ea: `0x180009080`
- end: `0x180009159`
- name: `?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@G@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009000`

## callees

- `0x1800066cc`
- `0x180008310`
- `0x180009080`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800090ec`
- `msvcrt!memmove_s` at `0x1800090ec`

## pseudocode

```c
void *const *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(
        void *const *a1,
        __int16 a2,
        __int64 a3)
{
  char *v3; // rax
  char *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rbx
  int v8; // esi
  errno_t v9; // eax

  v3 = (char *)*a1;
  v5 = (char *)*a1;
  if ( a2 == **(_WORD **)a1 )
  {
    do
      v5 += 2;
    while ( a2 == *(_WORD *)v5 );
    if ( v5 != v3 )
    {
      v6 = *((unsigned int *)v3 - 4);
      v7 = (v5 - v3) >> 1;
      if ( (int)((*((_DWORD *)v3 - 3) - v6) | (1 - *((_DWORD *)v3 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v6, a3);
      v8 = *((_DWORD *)*a1 - 4) - v7;
      v9 = memmove_s(*a1, 2LL * (v8 + 1), (char *)*a1 + 2 * (int)v7, 2LL * (v8 + 1));
      if ( v9 )
      {
        if ( v9 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v9 == 22 || v9 == 34 )
          goto LABEL_15;
        if ( v9 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      if ( v8 >= 0 && v8 <= *((_DWORD *)*a1 - 3) )
      {
        *((_DWORD *)*a1 - 4) = v8;
        *((_WORD *)*a1 + v8) = 0;
        return a1;
      }
LABEL_15:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180009080  mov     [rsp+arg_0], rbx
0x180009085  mov     [rsp+arg_8], rsi
0x18000908a  push    rdi
0x18000908b  sub     rsp, 20h
0x18000908f  mov     rax, [rcx]
0x180009092  mov     rdi, rcx
0x180009095  mov     rbx, rax
0x180009098  cmp     dx, [rax]
0x18000909b  jnz     loc_180009125
0x1800090a1  add     rbx, 2
0x1800090a5  cmp     dx, [rbx]
0x1800090a8  jz      short loc_1800090A1
0x1800090aa  cmp     rbx, rax
0x1800090ad  jz      short loc_180009125
0x1800090af  mov     edx, [rax-10h]
0x1800090b2  sub     rbx, rax
0x1800090b5  mov     ecx, 1
0x1800090ba  sar     rbx, 1
0x1800090bd  sub     ecx, [rax-8]
0x1800090c0  mov     eax, [rax-0Ch]
0x1800090c3  sub     eax, edx
0x1800090c5  or      ecx, eax
0x1800090c7  jge     short loc_1800090D1
0x1800090c9  mov     rcx, rdi
0x1800090cc  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800090d1  mov     rcx, [rdi]; Destination
0x1800090d4  mov     esi, [rcx-10h]
0x1800090d7  sub     esi, ebx
0x1800090d9  lea     eax, [rsi+1]
0x1800090dc  movsxd  rdx, eax
0x1800090df  movsxd  rax, ebx
0x1800090e2  add     rdx, rdx; DestinationSize
0x1800090e5  mov     r9, rdx; SourceSize
0x1800090e8  lea     r8, [rcx+rax*2]; Source
0x1800090ec  call    cs:__imp_memmove_s
0x1800090f2  test    eax, eax
0x1800090f4  jz      short loc_18000910A
0x1800090f6  cmp     eax, 0Ch
0x1800090f9  jz      short loc_18000914E
0x1800090fb  cmp     eax, 16h
0x1800090fe  jz      short loc_180009138
0x180009100  cmp     eax, 22h ; '"'
0x180009103  jz      short loc_180009138
0x180009105  cmp     eax, 50h ; 'P'
0x180009108  jnz     short loc_180009143
0x18000910a  test    esi, esi
0x18000910c  js      short loc_180009138
0x18000910e  mov     rax, [rdi]
0x180009111  cmp     esi, [rax-0Ch]
0x180009114  jg      short loc_180009138
0x180009116  mov     [rax-10h], esi
0x180009119  xor     eax, eax
0x18000911b  mov     rcx, [rdi]
0x18000911e  movsxd  rdx, esi
0x180009121  mov     [rcx+rdx*2], ax
0x180009125  mov     rbx, [rsp+28h+arg_0]
0x18000912a  mov     rax, rdi
0x18000912d  mov     rsi, [rsp+28h+arg_8]
0x180009132  add     rsp, 20h
0x180009136  pop     rdi
0x180009137  retn
0x180009138  mov     ecx, 80070057h; int
0x18000913d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009143  mov     ecx, 80004005h; int
0x180009148  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000914e  mov     ecx, 8007000Eh; int
0x180009153  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
