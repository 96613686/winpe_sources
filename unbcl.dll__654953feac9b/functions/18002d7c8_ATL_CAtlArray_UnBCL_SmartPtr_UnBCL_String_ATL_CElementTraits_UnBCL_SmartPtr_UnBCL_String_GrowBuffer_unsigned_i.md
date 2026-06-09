# ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::GrowBuffer(unsigned __int64)

- ea: `0x18002d7c8`
- end: `0x18002d8c2`
- name: `?GrowBuffer@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180027a84`
- `0x18002fec8`

## callees

- `0x1800066cc`
- `0x18002d7c8`

## import_xrefs

- `msvcrt!calloc` at `0x18002d803`
- `msvcrt!calloc` at `0x18002d83e`
- `msvcrt!calloc` at `0x18002d803`
- `msvcrt!calloc` at `0x18002d83e`
- `msvcrt!memmove_s` at `0x18002d861`
- `msvcrt!memmove_s` at `0x18002d861`
- `msvcrt!free` at `0x18002d882`
- `msvcrt!free` at `0x18002d882`

## pseudocode

```c
char __fastcall ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::GrowBuffer(
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
0x18002d7c8  mov     [rsp+arg_0], rbx
0x18002d7cd  mov     [rsp+arg_8], rsi
0x18002d7d2  push    rdi
0x18002d7d3  sub     rsp, 20h
0x18002d7d7  mov     rdi, rdx
0x18002d7da  mov     rbx, rcx
0x18002d7dd  mov     rdx, [rcx+10h]
0x18002d7e1  cmp     rdi, rdx
0x18002d7e4  jbe     loc_18002D88F
0x18002d7ea  cmp     qword ptr [rbx], 0
0x18002d7ee  movsxd  rcx, dword ptr [rcx+18h]
0x18002d7f2  jnz     short loc_18002D813
0x18002d7f4  cmp     rcx, rdi
0x18002d7f7  mov     edx, 10h; Size
0x18002d7fc  cmova   rdi, rcx
0x18002d800  mov     rcx, rdi; Count
0x18002d803  call    cs:__imp_calloc
0x18002d809  mov     [rbx], rax
0x18002d80c  test    rax, rax
0x18002d80f  jz      short loc_18002D84C
0x18002d811  jmp     short loc_18002D88B
0x18002d813  test    rcx, rcx
0x18002d816  jnz     short loc_18002D82B
0x18002d818  mov     rcx, rdx
0x18002d81b  mov     rax, rdi
0x18002d81e  shr     rcx, 1
0x18002d821  sub     rax, rdx
0x18002d824  cmp     rax, rcx
0x18002d827  cmova   rcx, rax
0x18002d82b  lea     rax, [rdx+rcx]
0x18002d82f  mov     edx, 10h; Size
0x18002d834  cmp     rdi, rax
0x18002d837  cmovb   rdi, rax
0x18002d83b  mov     rcx, rdi; Count
0x18002d83e  call    cs:__imp_calloc
0x18002d844  mov     rsi, rax
0x18002d847  test    rax, rax
0x18002d84a  jnz     short loc_18002D850
0x18002d84c  xor     al, al
0x18002d84e  jmp     short loc_18002D891
0x18002d850  mov     rdx, [rbx+8]
0x18002d854  mov     rcx, rsi; Destination
0x18002d857  mov     r8, [rbx]; Source
0x18002d85a  shl     rdx, 4; DestinationSize
0x18002d85e  mov     r9, rdx; SourceSize
0x18002d861  call    cs:__imp_memmove_s
0x18002d867  test    eax, eax
0x18002d869  jz      short loc_18002D87F
0x18002d86b  cmp     eax, 0Ch
0x18002d86e  jz      short loc_18002D8B7
0x18002d870  cmp     eax, 16h
0x18002d873  jz      short loc_18002D8AC
0x18002d875  cmp     eax, 22h ; '"'
0x18002d878  jz      short loc_18002D8AC
0x18002d87a  cmp     eax, 50h ; 'P'
0x18002d87d  jnz     short loc_18002D8A1
0x18002d87f  mov     rcx, [rbx]; Block
0x18002d882  call    cs:__imp_free
0x18002d888  mov     [rbx], rsi
0x18002d88b  mov     [rbx+10h], rdi
0x18002d88f  mov     al, 1
0x18002d891  mov     rbx, [rsp+28h+arg_0]
0x18002d896  mov     rsi, [rsp+28h+arg_8]
0x18002d89b  add     rsp, 20h
0x18002d89f  pop     rdi
0x18002d8a0  retn
0x18002d8a1  mov     ecx, 80004005h; int
0x18002d8a6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002d8ac  mov     ecx, 80070057h; int
0x18002d8b1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002d8b7  mov     ecx, 8007000Eh; int
0x18002d8bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
