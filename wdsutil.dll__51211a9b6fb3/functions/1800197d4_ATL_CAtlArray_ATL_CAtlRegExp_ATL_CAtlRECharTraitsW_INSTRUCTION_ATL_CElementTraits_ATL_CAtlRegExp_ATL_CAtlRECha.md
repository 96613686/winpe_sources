# ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(unsigned __int64)

- ea: `0x1800197d4`
- end: `0x1800198ea`
- name: `?GrowBuffer@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@AEAA_N_K@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c960`

## callees

- `0x1800085b8`
- `0x1800197d4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001987c`
- `msvcrt!memmove_s` at `0x18001987c`
- `msvcrt!free` at `0x1800198a3`
- `msvcrt!free` at `0x1800198a3`
- `msvcrt!calloc` at `0x18001980f`
- `msvcrt!calloc` at `0x180019853`
- `msvcrt!calloc` at `0x18001980f`
- `msvcrt!calloc` at `0x180019853`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(
        __int64 a1,
        size_t a2)
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
    v7 = calloc(a2, 0x10u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 16LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 16LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 0x10u);
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
0x1800197d4  mov     [rsp+arg_0], rbx
0x1800197d9  mov     [rsp+arg_8], rsi
0x1800197de  push    rdi
0x1800197df  sub     rsp, 20h
0x1800197e3  mov     rdi, rdx
0x1800197e6  mov     rbx, rcx
0x1800197e9  mov     rdx, [rcx+10h]
0x1800197ed  cmp     rdi, rdx
0x1800197f0  jbe     loc_1800198B6
0x1800197f6  cmp     qword ptr [rbx], 0
0x1800197fa  movsxd  rcx, dword ptr [rcx+18h]
0x1800197fe  jnz     short loc_180019828
0x180019800  cmp     rcx, rdi
0x180019803  mov     edx, 10h; Size
0x180019808  cmova   rdi, rcx
0x18001980c  mov     rcx, rdi; Count
0x18001980f  call    cs:__imp_calloc
0x180019816  nop     dword ptr [rax+rax+00h]
0x18001981b  mov     [rbx], rax
0x18001981e  test    rax, rax
0x180019821  jz      short loc_180019867
0x180019823  jmp     loc_1800198B2
0x180019828  test    rcx, rcx
0x18001982b  jnz     short loc_180019840
0x18001982d  mov     rcx, rdx
0x180019830  mov     rax, rdi
0x180019833  shr     rcx, 1
0x180019836  sub     rax, rdx
0x180019839  cmp     rax, rcx
0x18001983c  cmova   rcx, rax
0x180019840  lea     rax, [rdx+rcx]
0x180019844  mov     edx, 10h; Size
0x180019849  cmp     rdi, rax
0x18001984c  cmovb   rdi, rax
0x180019850  mov     rcx, rdi; Count
0x180019853  call    cs:__imp_calloc
0x18001985a  nop     dword ptr [rax+rax+00h]
0x18001985f  mov     rsi, rax
0x180019862  test    rax, rax
0x180019865  jnz     short loc_18001986B
0x180019867  xor     al, al
0x180019869  jmp     short loc_1800198B8
0x18001986b  mov     rdx, [rbx+8]
0x18001986f  mov     rcx, rsi; Destination
0x180019872  mov     r8, [rbx]; Source
0x180019875  shl     rdx, 4; DestinationSize
0x180019879  mov     r9, rdx; SourceSize
0x18001987c  call    cs:__imp_memmove_s
0x180019883  nop     dword ptr [rax+rax+00h]
0x180019888  test    eax, eax
0x18001988a  jz      short loc_1800198A0
0x18001988c  cmp     eax, 0Ch
0x18001988f  jz      short loc_1800198DF
0x180019891  cmp     eax, 16h
0x180019894  jz      short loc_1800198D4
0x180019896  cmp     eax, 22h ; '"'
0x180019899  jz      short loc_1800198D4
0x18001989b  cmp     eax, 50h ; 'P'
0x18001989e  jnz     short loc_1800198C9
0x1800198a0  mov     rcx, [rbx]; Block
0x1800198a3  call    cs:__imp_free
0x1800198aa  nop     dword ptr [rax+rax+00h]
0x1800198af  mov     [rbx], rsi
0x1800198b2  mov     [rbx+10h], rdi
0x1800198b6  mov     al, 1
0x1800198b8  mov     rbx, [rsp+28h+arg_0]
0x1800198bd  mov     rsi, [rsp+28h+arg_8]
0x1800198c2  add     rsp, 20h
0x1800198c6  pop     rdi
0x1800198c7  retn
0x1800198c9  mov     ecx, 80004005h; int
0x1800198ce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800198d4  mov     ecx, 80070057h; int
0x1800198d9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800198df  mov     ecx, 8007000Eh; int
0x1800198e4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
