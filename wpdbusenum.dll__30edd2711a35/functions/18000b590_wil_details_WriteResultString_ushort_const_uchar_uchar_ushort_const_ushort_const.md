# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000b590`
- end: `0x18000b5f7`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cebc`
- `0x18000cff8`

## callees

- `0x180008854`
- `0x18000b590`
- `0x18000cdf8`

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
0x18000b590  push    rbx
0x18000b592  push    rbp
0x18000b593  push    rsi
0x18000b594  push    rdi
0x18000b595  sub     rsp, 28h
0x18000b599  xor     ebp, ebp
0x18000b59b  mov     rbx, r9
0x18000b59e  mov     r10, rdx
0x18000b5a1  mov     rdi, rcx
0x18000b5a4  cmp     rcx, rdx
0x18000b5a7  jz      short loc_18000B5E3
0x18000b5a9  test    r8, r8
0x18000b5ac  jz      short loc_18000B5E3
0x18000b5ae  cmp     [r8], bp
0x18000b5b2  jz      short loc_18000B5E3
0x18000b5b4  mov     rcx, r8; this
0x18000b5b7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b5bc  sub     r10, rdi
0x18000b5bf  mov     rsi, rax
0x18000b5c2  cmp     r10, rax
0x18000b5c5  jb      short loc_18000B5E3
0x18000b5c7  mov     r9, rax; SourceSize
0x18000b5ca  mov     rdx, r10; DestinationSize
0x18000b5cd  mov     rcx, rdi; Destination
0x18000b5d0  call    memcpy_s
0x18000b5d5  test    rbx, rbx
0x18000b5d8  jz      short loc_18000B5DD
0x18000b5da  mov     [rbx], rdi
0x18000b5dd  lea     rax, [rsi+rdi]
0x18000b5e1  jmp     short loc_18000B5EE
0x18000b5e3  test    rbx, rbx
0x18000b5e6  jz      short loc_18000B5EB
0x18000b5e8  mov     [r9], rbp
0x18000b5eb  mov     rax, rdi
0x18000b5ee  add     rsp, 28h
0x18000b5f2  pop     rdi
0x18000b5f3  pop     rsi
0x18000b5f4  pop     rbp
0x18000b5f5  pop     rbx
0x18000b5f6  retn
```
