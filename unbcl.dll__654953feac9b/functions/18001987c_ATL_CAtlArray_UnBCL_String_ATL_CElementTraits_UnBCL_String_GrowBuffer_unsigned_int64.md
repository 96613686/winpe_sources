# ATL::CAtlArray<UnBCL::String *,ATL::CElementTraits<UnBCL::String *>>::GrowBuffer(unsigned __int64)

- ea: `0x18001987c`
- end: `0x180019976`
- name: `?GrowBuffer@?$CAtlArray@PEAVString@UnBCL@@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014160`
- `0x18001ef54`

## callees

- `0x1800066cc`
- `0x18001987c`

## import_xrefs

- `msvcrt!calloc` at `0x1800198b7`
- `msvcrt!calloc` at `0x1800198f2`
- `msvcrt!calloc` at `0x1800198b7`
- `msvcrt!calloc` at `0x1800198f2`
- `msvcrt!memmove_s` at `0x180019915`
- `msvcrt!memmove_s` at `0x180019915`
- `msvcrt!free` at `0x180019936`
- `msvcrt!free` at `0x180019936`

## pseudocode

```c
char __fastcall ATL::CAtlArray<UnBCL::String *,ATL::CElementTraits<UnBCL::String *>>::GrowBuffer(__int64 a1, size_t a2)
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
0x18001987c  mov     [rsp+arg_0], rbx
0x180019881  mov     [rsp+arg_8], rsi
0x180019886  push    rdi
0x180019887  sub     rsp, 20h
0x18001988b  mov     rdi, rdx
0x18001988e  mov     rbx, rcx
0x180019891  mov     rdx, [rcx+10h]
0x180019895  cmp     rdi, rdx
0x180019898  jbe     loc_180019943
0x18001989e  cmp     qword ptr [rbx], 0
0x1800198a2  movsxd  rcx, dword ptr [rcx+18h]
0x1800198a6  jnz     short loc_1800198C7
0x1800198a8  cmp     rcx, rdi
0x1800198ab  mov     edx, 8; Size
0x1800198b0  cmova   rdi, rcx
0x1800198b4  mov     rcx, rdi; Count
0x1800198b7  call    cs:__imp_calloc
0x1800198bd  mov     [rbx], rax
0x1800198c0  test    rax, rax
0x1800198c3  jz      short loc_180019900
0x1800198c5  jmp     short loc_18001993F
0x1800198c7  test    rcx, rcx
0x1800198ca  jnz     short loc_1800198DF
0x1800198cc  mov     rcx, rdx
0x1800198cf  mov     rax, rdi
0x1800198d2  shr     rcx, 1
0x1800198d5  sub     rax, rdx
0x1800198d8  cmp     rax, rcx
0x1800198db  cmova   rcx, rax
0x1800198df  lea     rax, [rdx+rcx]
0x1800198e3  mov     edx, 8; Size
0x1800198e8  cmp     rdi, rax
0x1800198eb  cmovb   rdi, rax
0x1800198ef  mov     rcx, rdi; Count
0x1800198f2  call    cs:__imp_calloc
0x1800198f8  mov     rsi, rax
0x1800198fb  test    rax, rax
0x1800198fe  jnz     short loc_180019904
0x180019900  xor     al, al
0x180019902  jmp     short loc_180019945
0x180019904  mov     rdx, [rbx+8]
0x180019908  mov     rcx, rsi; Destination
0x18001990b  mov     r8, [rbx]; Source
0x18001990e  shl     rdx, 3; DestinationSize
0x180019912  mov     r9, rdx; SourceSize
0x180019915  call    cs:__imp_memmove_s
0x18001991b  test    eax, eax
0x18001991d  jz      short loc_180019933
0x18001991f  cmp     eax, 0Ch
0x180019922  jz      short loc_18001996B
0x180019924  cmp     eax, 16h
0x180019927  jz      short loc_180019960
0x180019929  cmp     eax, 22h ; '"'
0x18001992c  jz      short loc_180019960
0x18001992e  cmp     eax, 50h ; 'P'
0x180019931  jnz     short loc_180019955
0x180019933  mov     rcx, [rbx]; Block
0x180019936  call    cs:__imp_free
0x18001993c  mov     [rbx], rsi
0x18001993f  mov     [rbx+10h], rdi
0x180019943  mov     al, 1
0x180019945  mov     rbx, [rsp+28h+arg_0]
0x18001994a  mov     rsi, [rsp+28h+arg_8]
0x18001994f  add     rsp, 20h
0x180019953  pop     rdi
0x180019954  retn
0x180019955  mov     ecx, 80004005h; int
0x18001995a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019960  mov     ecx, 80070057h; int
0x180019965  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001996b  mov     ecx, 8007000Eh; int
0x180019970  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
