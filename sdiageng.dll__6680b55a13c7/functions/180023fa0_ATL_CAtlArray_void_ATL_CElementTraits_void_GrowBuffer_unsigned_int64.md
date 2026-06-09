# ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)

- ea: `0x180023fa0`
- end: `0x18002409a`
- name: `?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180026174`
- `0x180026250`

## callees

- `0x180023e08`
- `0x180023fa0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180024039`
- `msvcrt!memmove_s` at `0x180024039`
- `msvcrt!free` at `0x18002405a`
- `msvcrt!free` at `0x18002405a`
- `msvcrt!calloc` at `0x180023fdb`
- `msvcrt!calloc` at `0x180024016`
- `msvcrt!calloc` at `0x180023fdb`
- `msvcrt!calloc` at `0x180024016`

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
0x180023fa0  mov     [rsp+arg_0], rbx
0x180023fa5  mov     [rsp+arg_8], rsi
0x180023faa  push    rdi
0x180023fab  sub     rsp, 20h
0x180023faf  mov     rdi, rdx
0x180023fb2  mov     rbx, rcx
0x180023fb5  mov     rdx, [rcx+10h]
0x180023fb9  cmp     rdi, rdx
0x180023fbc  jbe     loc_180024067
0x180023fc2  cmp     qword ptr [rbx], 0
0x180023fc6  movsxd  rcx, dword ptr [rcx+18h]
0x180023fca  jnz     short loc_180023FEB
0x180023fcc  cmp     rcx, rdi
0x180023fcf  mov     edx, 8; Size
0x180023fd4  cmova   rdi, rcx
0x180023fd8  mov     rcx, rdi; Count
0x180023fdb  call    cs:__imp_calloc
0x180023fe1  mov     [rbx], rax
0x180023fe4  test    rax, rax
0x180023fe7  jz      short loc_180024024
0x180023fe9  jmp     short loc_180024063
0x180023feb  test    rcx, rcx
0x180023fee  jnz     short loc_180024003
0x180023ff0  mov     rcx, rdx
0x180023ff3  mov     rax, rdi
0x180023ff6  shr     rcx, 1
0x180023ff9  sub     rax, rdx
0x180023ffc  cmp     rax, rcx
0x180023fff  cmova   rcx, rax
0x180024003  lea     rax, [rdx+rcx]
0x180024007  mov     edx, 8; Size
0x18002400c  cmp     rdi, rax
0x18002400f  cmovb   rdi, rax
0x180024013  mov     rcx, rdi; Count
0x180024016  call    cs:__imp_calloc
0x18002401c  mov     rsi, rax
0x18002401f  test    rax, rax
0x180024022  jnz     short loc_180024028
0x180024024  xor     al, al
0x180024026  jmp     short loc_180024069
0x180024028  mov     rdx, [rbx+8]
0x18002402c  mov     rcx, rsi; Destination
0x18002402f  mov     r8, [rbx]; Source
0x180024032  shl     rdx, 3; DestinationSize
0x180024036  mov     r9, rdx; SourceSize
0x180024039  call    cs:__imp_memmove_s
0x18002403f  test    eax, eax
0x180024041  jz      short loc_180024057
0x180024043  cmp     eax, 0Ch
0x180024046  jz      short loc_18002408F
0x180024048  cmp     eax, 16h
0x18002404b  jz      short loc_180024084
0x18002404d  cmp     eax, 22h ; '"'
0x180024050  jz      short loc_180024084
0x180024052  cmp     eax, 50h ; 'P'
0x180024055  jnz     short loc_180024079
0x180024057  mov     rcx, [rbx]; Block
0x18002405a  call    cs:__imp_free
0x180024060  mov     [rbx], rsi
0x180024063  mov     [rbx+10h], rdi
0x180024067  mov     al, 1
0x180024069  mov     rbx, [rsp+28h+arg_0]
0x18002406e  mov     rsi, [rsp+28h+arg_8]
0x180024073  add     rsp, 20h
0x180024077  pop     rdi
0x180024078  retn
0x180024079  mov     ecx, 80004005h; int
0x18002407e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024084  mov     ecx, 80070057h; int
0x180024089  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002408f  mov     ecx, 8007000Eh; int
0x180024094  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
