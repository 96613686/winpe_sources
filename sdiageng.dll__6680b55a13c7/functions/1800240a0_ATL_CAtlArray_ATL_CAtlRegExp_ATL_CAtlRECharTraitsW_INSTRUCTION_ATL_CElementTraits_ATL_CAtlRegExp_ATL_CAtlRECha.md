# ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(unsigned __int64)

- ea: `0x1800240a0`
- end: `0x18002419a`
- name: `?GrowBuffer@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800261dc`

## callees

- `0x180023e08`
- `0x1800240a0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180024139`
- `msvcrt!memmove_s` at `0x180024139`
- `msvcrt!free` at `0x18002415a`
- `msvcrt!free` at `0x18002415a`
- `msvcrt!calloc` at `0x1800240db`
- `msvcrt!calloc` at `0x180024116`
- `msvcrt!calloc` at `0x1800240db`
- `msvcrt!calloc` at `0x180024116`

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
0x1800240a0  mov     [rsp+arg_0], rbx
0x1800240a5  mov     [rsp+arg_8], rsi
0x1800240aa  push    rdi
0x1800240ab  sub     rsp, 20h
0x1800240af  mov     rdi, rdx
0x1800240b2  mov     rbx, rcx
0x1800240b5  mov     rdx, [rcx+10h]
0x1800240b9  cmp     rdi, rdx
0x1800240bc  jbe     loc_180024167
0x1800240c2  cmp     qword ptr [rbx], 0
0x1800240c6  movsxd  rcx, dword ptr [rcx+18h]
0x1800240ca  jnz     short loc_1800240EB
0x1800240cc  cmp     rcx, rdi
0x1800240cf  mov     edx, 10h; Size
0x1800240d4  cmova   rdi, rcx
0x1800240d8  mov     rcx, rdi; Count
0x1800240db  call    cs:__imp_calloc
0x1800240e1  mov     [rbx], rax
0x1800240e4  test    rax, rax
0x1800240e7  jz      short loc_180024124
0x1800240e9  jmp     short loc_180024163
0x1800240eb  test    rcx, rcx
0x1800240ee  jnz     short loc_180024103
0x1800240f0  mov     rcx, rdx
0x1800240f3  mov     rax, rdi
0x1800240f6  shr     rcx, 1
0x1800240f9  sub     rax, rdx
0x1800240fc  cmp     rax, rcx
0x1800240ff  cmova   rcx, rax
0x180024103  lea     rax, [rdx+rcx]
0x180024107  mov     edx, 10h; Size
0x18002410c  cmp     rdi, rax
0x18002410f  cmovb   rdi, rax
0x180024113  mov     rcx, rdi; Count
0x180024116  call    cs:__imp_calloc
0x18002411c  mov     rsi, rax
0x18002411f  test    rax, rax
0x180024122  jnz     short loc_180024128
0x180024124  xor     al, al
0x180024126  jmp     short loc_180024169
0x180024128  mov     rdx, [rbx+8]
0x18002412c  mov     rcx, rsi; Destination
0x18002412f  mov     r8, [rbx]; Source
0x180024132  shl     rdx, 4; DestinationSize
0x180024136  mov     r9, rdx; SourceSize
0x180024139  call    cs:__imp_memmove_s
0x18002413f  test    eax, eax
0x180024141  jz      short loc_180024157
0x180024143  cmp     eax, 0Ch
0x180024146  jz      short loc_18002418F
0x180024148  cmp     eax, 16h
0x18002414b  jz      short loc_180024184
0x18002414d  cmp     eax, 22h ; '"'
0x180024150  jz      short loc_180024184
0x180024152  cmp     eax, 50h ; 'P'
0x180024155  jnz     short loc_180024179
0x180024157  mov     rcx, [rbx]; Block
0x18002415a  call    cs:__imp_free
0x180024160  mov     [rbx], rsi
0x180024163  mov     [rbx+10h], rdi
0x180024167  mov     al, 1
0x180024169  mov     rbx, [rsp+28h+arg_0]
0x18002416e  mov     rsi, [rsp+28h+arg_8]
0x180024173  add     rsp, 20h
0x180024177  pop     rdi
0x180024178  retn
0x180024179  mov     ecx, 80004005h; int
0x18002417e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024184  mov     ecx, 80070057h; int
0x180024189  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002418f  mov     ecx, 8007000Eh; int
0x180024194  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
