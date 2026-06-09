# ATL::CAtlArray<ushort,ATL::CElementTraits<ushort>>::GrowBuffer(unsigned __int64)

- ea: `0x18001967c`
- end: `0x180019775`
- name: `?GrowBuffer@?$CAtlArray@GV?$CElementTraits@G@ATL@@@ATL@@AEAA_N_K@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014050`
- `0x18001ee5c`

## callees

- `0x1800066cc`
- `0x18001967c`

## import_xrefs

- `msvcrt!calloc` at `0x1800196b7`
- `msvcrt!calloc` at `0x1800196f2`
- `msvcrt!calloc` at `0x1800196b7`
- `msvcrt!calloc` at `0x1800196f2`
- `msvcrt!memmove_s` at `0x180019714`
- `msvcrt!memmove_s` at `0x180019714`
- `msvcrt!free` at `0x180019735`
- `msvcrt!free` at `0x180019735`

## pseudocode

```c
char __fastcall ATL::CAtlArray<unsigned short,ATL::CElementTraits<unsigned short>>::GrowBuffer(__int64 a1, size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( *(_QWORD *)a1 )
  {
    if ( !v5 )
    {
      v5 = v4 >> 1;
      if ( a2 - v4 > v4 >> 1 )
        v5 = a2 - v4;
    }
    if ( a2 < v4 + v5 )
      a2 = v4 + v5;
    v7 = calloc(a2, 2u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 2LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 2LL * *(_QWORD *)(a1 + 8));
      if ( v10 )
      {
        if ( v10 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v10 == 22 || v10 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v10 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
      goto LABEL_20;
    }
    return 0;
  }
  if ( v5 > a2 )
    a2 = v5;
  v6 = calloc(a2, 2u);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 0;
LABEL_20:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x18001967c  mov     [rsp+arg_0], rbx
0x180019681  mov     [rsp+arg_8], rsi
0x180019686  push    rdi
0x180019687  sub     rsp, 20h
0x18001968b  mov     rdi, rdx
0x18001968e  mov     rbx, rcx
0x180019691  mov     rdx, [rcx+10h]
0x180019695  cmp     rdi, rdx
0x180019698  jbe     loc_180019742
0x18001969e  cmp     qword ptr [rbx], 0
0x1800196a2  movsxd  rcx, dword ptr [rcx+18h]
0x1800196a6  jnz     short loc_1800196C7
0x1800196a8  cmp     rcx, rdi
0x1800196ab  mov     edx, 2; Size
0x1800196b0  cmova   rdi, rcx
0x1800196b4  mov     rcx, rdi; Count
0x1800196b7  call    cs:__imp_calloc
0x1800196bd  mov     [rbx], rax
0x1800196c0  test    rax, rax
0x1800196c3  jz      short loc_180019700
0x1800196c5  jmp     short loc_18001973E
0x1800196c7  test    rcx, rcx
0x1800196ca  jnz     short loc_1800196DF
0x1800196cc  mov     rcx, rdx
0x1800196cf  mov     rax, rdi
0x1800196d2  shr     rcx, 1
0x1800196d5  sub     rax, rdx
0x1800196d8  cmp     rax, rcx
0x1800196db  cmova   rcx, rax
0x1800196df  lea     rax, [rdx+rcx]
0x1800196e3  mov     edx, 2; Size
0x1800196e8  cmp     rdi, rax
0x1800196eb  cmovb   rdi, rax
0x1800196ef  mov     rcx, rdi; Count
0x1800196f2  call    cs:__imp_calloc
0x1800196f8  mov     rsi, rax
0x1800196fb  test    rax, rax
0x1800196fe  jnz     short loc_180019704
0x180019700  xor     al, al
0x180019702  jmp     short loc_180019744
0x180019704  mov     rdx, [rbx+8]
0x180019708  mov     rcx, rsi; Destination
0x18001970b  mov     r8, [rbx]; Source
0x18001970e  add     rdx, rdx; DestinationSize
0x180019711  mov     r9, rdx; SourceSize
0x180019714  call    cs:__imp_memmove_s
0x18001971a  test    eax, eax
0x18001971c  jz      short loc_180019732
0x18001971e  cmp     eax, 0Ch
0x180019721  jz      short loc_18001976A
0x180019723  cmp     eax, 16h
0x180019726  jz      short loc_18001975F
0x180019728  cmp     eax, 22h ; '"'
0x18001972b  jz      short loc_18001975F
0x18001972d  cmp     eax, 50h ; 'P'
0x180019730  jnz     short loc_180019754
0x180019732  mov     rcx, [rbx]; Block
0x180019735  call    cs:__imp_free
0x18001973b  mov     [rbx], rsi
0x18001973e  mov     [rbx+10h], rdi
0x180019742  mov     al, 1
0x180019744  mov     rbx, [rsp+28h+arg_0]
0x180019749  mov     rsi, [rsp+28h+arg_8]
0x18001974e  add     rsp, 20h
0x180019752  pop     rdi
0x180019753  retn
0x180019754  mov     ecx, 80004005h; int
0x180019759  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001975f  mov     ecx, 80070057h; int
0x180019764  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001976a  mov     ecx, 8007000Eh; int
0x18001976f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
