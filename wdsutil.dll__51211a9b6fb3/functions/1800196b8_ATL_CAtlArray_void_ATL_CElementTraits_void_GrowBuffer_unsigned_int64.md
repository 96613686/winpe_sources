# ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)

- ea: `0x1800196b8`
- end: `0x1800197ce`
- name: `?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z`
- size: `278`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001486c`
- `0x18001c8f4`
- `0x18001e334`

## callees

- `0x1800085b8`
- `0x1800196b8`

## import_xrefs

- `msvcrt!memmove_s` at `0x180019760`
- `msvcrt!memmove_s` at `0x180019760`
- `msvcrt!free` at `0x180019787`
- `msvcrt!free` at `0x180019787`
- `msvcrt!calloc` at `0x1800196f3`
- `msvcrt!calloc` at `0x180019737`
- `msvcrt!calloc` at `0x1800196f3`
- `msvcrt!calloc` at `0x180019737`

## pseudocode

```c
char __fastcall ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(__int64 a1, size_t a2)
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
    v7 = calloc(a2, 8u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 8u);
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
0x1800196b8  mov     [rsp+arg_0], rbx
0x1800196bd  mov     [rsp+arg_8], rsi
0x1800196c2  push    rdi
0x1800196c3  sub     rsp, 20h
0x1800196c7  mov     rdi, rdx
0x1800196ca  mov     rbx, rcx
0x1800196cd  mov     rdx, [rcx+10h]
0x1800196d1  cmp     rdi, rdx
0x1800196d4  jbe     loc_18001979A
0x1800196da  cmp     qword ptr [rbx], 0
0x1800196de  movsxd  rcx, dword ptr [rcx+18h]
0x1800196e2  jnz     short loc_18001970C
0x1800196e4  cmp     rcx, rdi
0x1800196e7  mov     edx, 8; Size
0x1800196ec  cmova   rdi, rcx
0x1800196f0  mov     rcx, rdi; Count
0x1800196f3  call    cs:__imp_calloc
0x1800196fa  nop     dword ptr [rax+rax+00h]
0x1800196ff  mov     [rbx], rax
0x180019702  test    rax, rax
0x180019705  jz      short loc_18001974B
0x180019707  jmp     loc_180019796
0x18001970c  test    rcx, rcx
0x18001970f  jnz     short loc_180019724
0x180019711  mov     rcx, rdx
0x180019714  mov     rax, rdi
0x180019717  shr     rcx, 1
0x18001971a  sub     rax, rdx
0x18001971d  cmp     rax, rcx
0x180019720  cmova   rcx, rax
0x180019724  lea     rax, [rdx+rcx]
0x180019728  mov     edx, 8; Size
0x18001972d  cmp     rdi, rax
0x180019730  cmovb   rdi, rax
0x180019734  mov     rcx, rdi; Count
0x180019737  call    cs:__imp_calloc
0x18001973e  nop     dword ptr [rax+rax+00h]
0x180019743  mov     rsi, rax
0x180019746  test    rax, rax
0x180019749  jnz     short loc_18001974F
0x18001974b  xor     al, al
0x18001974d  jmp     short loc_18001979C
0x18001974f  mov     rdx, [rbx+8]
0x180019753  mov     rcx, rsi; Destination
0x180019756  mov     r8, [rbx]; Source
0x180019759  shl     rdx, 3; DestinationSize
0x18001975d  mov     r9, rdx; SourceSize
0x180019760  call    cs:__imp_memmove_s
0x180019767  nop     dword ptr [rax+rax+00h]
0x18001976c  test    eax, eax
0x18001976e  jz      short loc_180019784
0x180019770  cmp     eax, 0Ch
0x180019773  jz      short loc_1800197C3
0x180019775  cmp     eax, 16h
0x180019778  jz      short loc_1800197B8
0x18001977a  cmp     eax, 22h ; '"'
0x18001977d  jz      short loc_1800197B8
0x18001977f  cmp     eax, 50h ; 'P'
0x180019782  jnz     short loc_1800197AD
0x180019784  mov     rcx, [rbx]; Block
0x180019787  call    cs:__imp_free
0x18001978e  nop     dword ptr [rax+rax+00h]
0x180019793  mov     [rbx], rsi
0x180019796  mov     [rbx+10h], rdi
0x18001979a  mov     al, 1
0x18001979c  mov     rbx, [rsp+28h+arg_0]
0x1800197a1  mov     rsi, [rsp+28h+arg_8]
0x1800197a6  add     rsp, 20h
0x1800197aa  pop     rdi
0x1800197ab  retn
0x1800197ad  mov     ecx, 80004005h; int
0x1800197b2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800197b8  mov     ecx, 80070057h; int
0x1800197bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800197c3  mov     ecx, 8007000Eh; int
0x1800197c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
