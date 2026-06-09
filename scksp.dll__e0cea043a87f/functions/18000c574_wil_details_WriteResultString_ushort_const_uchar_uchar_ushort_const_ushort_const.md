# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000c574`
- end: `0x18000c5dc`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d30`
- `0x180010f5c`

## callees

- `0x18000c574`
- `0x180010bc8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c5b4`
- `msvcrt!memcpy_s` at `0x18000c5b4`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x18000c574  push    rbx
0x18000c576  push    rbp
0x18000c577  push    rsi
0x18000c578  push    rdi
0x18000c579  sub     rsp, 28h
0x18000c57d  xor     ebp, ebp
0x18000c57f  mov     rbx, r9
0x18000c582  mov     r10, rdx
0x18000c585  mov     rdi, rcx
0x18000c588  cmp     rcx, rdx
0x18000c58b  jz      short loc_18000C5C8
0x18000c58d  test    r8, r8
0x18000c590  jz      short loc_18000C5C8
0x18000c592  cmp     [r8], bp
0x18000c596  jz      short loc_18000C5C8
0x18000c598  mov     rcx, r8; this
0x18000c59b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000c5a0  sub     r10, rdi
0x18000c5a3  mov     rsi, rax
0x18000c5a6  cmp     r10, rax
0x18000c5a9  jb      short loc_18000C5C8
0x18000c5ab  mov     r9, rax; SourceSize
0x18000c5ae  mov     rdx, r10; DestinationSize
0x18000c5b1  mov     rcx, rdi; Destination
0x18000c5b4  call    cs:__imp_memcpy_s
0x18000c5ba  test    rbx, rbx
0x18000c5bd  jz      short loc_18000C5C2
0x18000c5bf  mov     [rbx], rdi
0x18000c5c2  lea     rax, [rsi+rdi]
0x18000c5c6  jmp     short loc_18000C5D3
0x18000c5c8  test    rbx, rbx
0x18000c5cb  jz      short loc_18000C5D0
0x18000c5cd  mov     [r9], rbp
0x18000c5d0  mov     rax, rdi
0x18000c5d3  add     rsp, 28h
0x18000c5d7  pop     rdi
0x18000c5d8  pop     rsi
0x18000c5d9  pop     rbp
0x18000c5da  pop     rbx
0x18000c5db  retn
```
