# ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::GrowBuffer(unsigned __int64)

- ea: `0x180019580`
- end: `0x180019676`
- name: `?GrowBuffer@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@AEAA_N_K@Z`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180013fc4`
- `0x18001ede0`

## callees

- `0x1800066cc`
- `0x180019580`

## import_xrefs

- `msvcrt!calloc` at `0x1800195bb`
- `msvcrt!calloc` at `0x1800195f6`
- `msvcrt!calloc` at `0x1800195bb`
- `msvcrt!calloc` at `0x1800195f6`
- `msvcrt!memmove_s` at `0x180019615`
- `msvcrt!memmove_s` at `0x180019615`
- `msvcrt!free` at `0x180019636`
- `msvcrt!free` at `0x180019636`

## pseudocode

```c
char __fastcall ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::GrowBuffer(__int64 a1, size_t a2)
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
    v7 = calloc(a2, 1u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, *(_QWORD *)(a1 + 8), *(const void *const *)a1, *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 1u);
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
0x180019580  mov     [rsp+arg_0], rbx
0x180019585  mov     [rsp+arg_8], rsi
0x18001958a  push    rdi
0x18001958b  sub     rsp, 20h
0x18001958f  mov     rdi, rdx
0x180019592  mov     rbx, rcx
0x180019595  mov     rdx, [rcx+10h]
0x180019599  cmp     rdi, rdx
0x18001959c  jbe     loc_180019643
0x1800195a2  cmp     qword ptr [rbx], 0
0x1800195a6  movsxd  rcx, dword ptr [rcx+18h]
0x1800195aa  jnz     short loc_1800195CB
0x1800195ac  cmp     rcx, rdi
0x1800195af  mov     edx, 1; Size
0x1800195b4  cmova   rdi, rcx
0x1800195b8  mov     rcx, rdi; Count
0x1800195bb  call    cs:__imp_calloc
0x1800195c1  mov     [rbx], rax
0x1800195c4  test    rax, rax
0x1800195c7  jz      short loc_180019604
0x1800195c9  jmp     short loc_18001963F
0x1800195cb  test    rcx, rcx
0x1800195ce  jnz     short loc_1800195E3
0x1800195d0  mov     rcx, rdx
0x1800195d3  mov     rax, rdi
0x1800195d6  shr     rcx, 1
0x1800195d9  sub     rax, rdx
0x1800195dc  cmp     rax, rcx
0x1800195df  cmova   rcx, rax
0x1800195e3  lea     rax, [rdx+rcx]
0x1800195e7  mov     edx, 1; Size
0x1800195ec  cmp     rdi, rax
0x1800195ef  cmovb   rdi, rax
0x1800195f3  mov     rcx, rdi; Count
0x1800195f6  call    cs:__imp_calloc
0x1800195fc  mov     rsi, rax
0x1800195ff  test    rax, rax
0x180019602  jnz     short loc_180019608
0x180019604  xor     al, al
0x180019606  jmp     short loc_180019645
0x180019608  mov     rdx, [rbx+8]; DestinationSize
0x18001960c  mov     rcx, rsi; Destination
0x18001960f  mov     r8, [rbx]; Source
0x180019612  mov     r9, rdx; SourceSize
0x180019615  call    cs:__imp_memmove_s
0x18001961b  test    eax, eax
0x18001961d  jz      short loc_180019633
0x18001961f  cmp     eax, 0Ch
0x180019622  jz      short loc_18001966B
0x180019624  cmp     eax, 16h
0x180019627  jz      short loc_180019660
0x180019629  cmp     eax, 22h ; '"'
0x18001962c  jz      short loc_180019660
0x18001962e  cmp     eax, 50h ; 'P'
0x180019631  jnz     short loc_180019655
0x180019633  mov     rcx, [rbx]; Block
0x180019636  call    cs:__imp_free
0x18001963c  mov     [rbx], rsi
0x18001963f  mov     [rbx+10h], rdi
0x180019643  mov     al, 1
0x180019645  mov     rbx, [rsp+28h+arg_0]
0x18001964a  mov     rsi, [rsp+28h+arg_8]
0x18001964f  add     rsp, 20h
0x180019653  pop     rdi
0x180019654  retn
0x180019655  mov     ecx, 80004005h; int
0x18001965a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019660  mov     ecx, 80070057h; int
0x180019665  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001966b  mov     ecx, 8007000Eh; int
0x180019670  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
