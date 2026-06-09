# ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::GrowBuffer(unsigned __int64)

- ea: `0x180044b70`
- end: `0x180044c6a`
- name: `?GrowBuffer@?$CAtlArray@VStringPtr@UnBCL@@V?$CElementTraits@VStringPtr@UnBCL@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180042c74`
- `0x1800461e8`

## callees

- `0x1800066cc`
- `0x180044b70`

## import_xrefs

- `msvcrt!calloc` at `0x180044bab`
- `msvcrt!calloc` at `0x180044be6`
- `msvcrt!calloc` at `0x180044bab`
- `msvcrt!calloc` at `0x180044be6`
- `msvcrt!memmove_s` at `0x180044c09`
- `msvcrt!memmove_s` at `0x180044c09`
- `msvcrt!free` at `0x180044c2a`
- `msvcrt!free` at `0x180044c2a`

## pseudocode

```c
char __fastcall ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::GrowBuffer(
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
    v7 = calloc(a2, 0x20u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 32LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 32LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 0x20u);
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
0x180044b70  mov     [rsp+arg_0], rbx
0x180044b75  mov     [rsp+arg_8], rsi
0x180044b7a  push    rdi
0x180044b7b  sub     rsp, 20h
0x180044b7f  mov     rdi, rdx
0x180044b82  mov     rbx, rcx
0x180044b85  mov     rdx, [rcx+10h]
0x180044b89  cmp     rdi, rdx
0x180044b8c  jbe     loc_180044C37
0x180044b92  cmp     qword ptr [rbx], 0
0x180044b96  movsxd  rcx, dword ptr [rcx+18h]
0x180044b9a  jnz     short loc_180044BBB
0x180044b9c  cmp     rcx, rdi
0x180044b9f  mov     edx, 20h ; ' '; Size
0x180044ba4  cmova   rdi, rcx
0x180044ba8  mov     rcx, rdi; Count
0x180044bab  call    cs:__imp_calloc
0x180044bb1  mov     [rbx], rax
0x180044bb4  test    rax, rax
0x180044bb7  jz      short loc_180044BF4
0x180044bb9  jmp     short loc_180044C33
0x180044bbb  test    rcx, rcx
0x180044bbe  jnz     short loc_180044BD3
0x180044bc0  mov     rcx, rdx
0x180044bc3  mov     rax, rdi
0x180044bc6  shr     rcx, 1
0x180044bc9  sub     rax, rdx
0x180044bcc  cmp     rax, rcx
0x180044bcf  cmova   rcx, rax
0x180044bd3  lea     rax, [rdx+rcx]
0x180044bd7  mov     edx, 20h ; ' '; Size
0x180044bdc  cmp     rdi, rax
0x180044bdf  cmovb   rdi, rax
0x180044be3  mov     rcx, rdi; Count
0x180044be6  call    cs:__imp_calloc
0x180044bec  mov     rsi, rax
0x180044bef  test    rax, rax
0x180044bf2  jnz     short loc_180044BF8
0x180044bf4  xor     al, al
0x180044bf6  jmp     short loc_180044C39
0x180044bf8  mov     rdx, [rbx+8]
0x180044bfc  mov     rcx, rsi; Destination
0x180044bff  mov     r8, [rbx]; Source
0x180044c02  shl     rdx, 5; DestinationSize
0x180044c06  mov     r9, rdx; SourceSize
0x180044c09  call    cs:__imp_memmove_s
0x180044c0f  test    eax, eax
0x180044c11  jz      short loc_180044C27
0x180044c13  cmp     eax, 0Ch
0x180044c16  jz      short loc_180044C5F
0x180044c18  cmp     eax, 16h
0x180044c1b  jz      short loc_180044C54
0x180044c1d  cmp     eax, 22h ; '"'
0x180044c20  jz      short loc_180044C54
0x180044c22  cmp     eax, 50h ; 'P'
0x180044c25  jnz     short loc_180044C49
0x180044c27  mov     rcx, [rbx]; Block
0x180044c2a  call    cs:__imp_free
0x180044c30  mov     [rbx], rsi
0x180044c33  mov     [rbx+10h], rdi
0x180044c37  mov     al, 1
0x180044c39  mov     rbx, [rsp+28h+arg_0]
0x180044c3e  mov     rsi, [rsp+28h+arg_8]
0x180044c43  add     rsp, 20h
0x180044c47  pop     rdi
0x180044c48  retn
0x180044c49  mov     ecx, 80004005h; int
0x180044c4e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180044c54  mov     ecx, 80070057h; int
0x180044c59  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180044c5f  mov     ecx, 8007000Eh; int
0x180044c64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
