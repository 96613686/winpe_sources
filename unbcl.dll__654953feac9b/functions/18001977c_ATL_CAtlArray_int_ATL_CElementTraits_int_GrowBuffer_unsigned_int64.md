# ATL::CAtlArray<int,ATL::CElementTraits<int>>::GrowBuffer(unsigned __int64)

- ea: `0x18001977c`
- end: `0x180019876`
- name: `?GrowBuffer@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800140d4`
- `0x18001eed8`

## callees

- `0x1800066cc`
- `0x18001977c`

## import_xrefs

- `msvcrt!calloc` at `0x1800197b7`
- `msvcrt!calloc` at `0x1800197f2`
- `msvcrt!calloc` at `0x1800197b7`
- `msvcrt!calloc` at `0x1800197f2`
- `msvcrt!memmove_s` at `0x180019815`
- `msvcrt!memmove_s` at `0x180019815`
- `msvcrt!free` at `0x180019836`
- `msvcrt!free` at `0x180019836`

## pseudocode

```c
char __fastcall ATL::CAtlArray<int,ATL::CElementTraits<int>>::GrowBuffer(__int64 a1, size_t a2)
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
    v7 = calloc(a2, 4u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 4LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 4LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 4u);
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
0x18001977c  mov     [rsp+arg_0], rbx
0x180019781  mov     [rsp+arg_8], rsi
0x180019786  push    rdi
0x180019787  sub     rsp, 20h
0x18001978b  mov     rdi, rdx
0x18001978e  mov     rbx, rcx
0x180019791  mov     rdx, [rcx+10h]
0x180019795  cmp     rdi, rdx
0x180019798  jbe     loc_180019843
0x18001979e  cmp     qword ptr [rbx], 0
0x1800197a2  movsxd  rcx, dword ptr [rcx+18h]
0x1800197a6  jnz     short loc_1800197C7
0x1800197a8  cmp     rcx, rdi
0x1800197ab  mov     edx, 4; Size
0x1800197b0  cmova   rdi, rcx
0x1800197b4  mov     rcx, rdi; Count
0x1800197b7  call    cs:__imp_calloc
0x1800197bd  mov     [rbx], rax
0x1800197c0  test    rax, rax
0x1800197c3  jz      short loc_180019800
0x1800197c5  jmp     short loc_18001983F
0x1800197c7  test    rcx, rcx
0x1800197ca  jnz     short loc_1800197DF
0x1800197cc  mov     rcx, rdx
0x1800197cf  mov     rax, rdi
0x1800197d2  shr     rcx, 1
0x1800197d5  sub     rax, rdx
0x1800197d8  cmp     rax, rcx
0x1800197db  cmova   rcx, rax
0x1800197df  lea     rax, [rdx+rcx]
0x1800197e3  mov     edx, 4; Size
0x1800197e8  cmp     rdi, rax
0x1800197eb  cmovb   rdi, rax
0x1800197ef  mov     rcx, rdi; Count
0x1800197f2  call    cs:__imp_calloc
0x1800197f8  mov     rsi, rax
0x1800197fb  test    rax, rax
0x1800197fe  jnz     short loc_180019804
0x180019800  xor     al, al
0x180019802  jmp     short loc_180019845
0x180019804  mov     rdx, [rbx+8]
0x180019808  mov     rcx, rsi; Destination
0x18001980b  mov     r8, [rbx]; Source
0x18001980e  shl     rdx, 2; DestinationSize
0x180019812  mov     r9, rdx; SourceSize
0x180019815  call    cs:__imp_memmove_s
0x18001981b  test    eax, eax
0x18001981d  jz      short loc_180019833
0x18001981f  cmp     eax, 0Ch
0x180019822  jz      short loc_18001986B
0x180019824  cmp     eax, 16h
0x180019827  jz      short loc_180019860
0x180019829  cmp     eax, 22h ; '"'
0x18001982c  jz      short loc_180019860
0x18001982e  cmp     eax, 50h ; 'P'
0x180019831  jnz     short loc_180019855
0x180019833  mov     rcx, [rbx]; Block
0x180019836  call    cs:__imp_free
0x18001983c  mov     [rbx], rsi
0x18001983f  mov     [rbx+10h], rdi
0x180019843  mov     al, 1
0x180019845  mov     rbx, [rsp+28h+arg_0]
0x18001984a  mov     rsi, [rsp+28h+arg_8]
0x18001984f  add     rsp, 20h
0x180019853  pop     rdi
0x180019854  retn
0x180019855  mov     ecx, 80004005h; int
0x18001985a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019860  mov     ecx, 80070057h; int
0x180019865  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001986b  mov     ecx, 8007000Eh; int
0x180019870  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
