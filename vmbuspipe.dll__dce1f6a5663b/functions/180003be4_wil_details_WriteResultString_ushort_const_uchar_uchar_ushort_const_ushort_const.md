# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003be4`
- end: `0x180003c4b`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ea0`
- `0x180005fdc`

## callees

- `0x180003be4`
- `0x180005d58`
- `0x1800074c8`

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
0x180003be4  push    rbx
0x180003be6  push    rbp
0x180003be7  push    rsi
0x180003be8  push    rdi
0x180003be9  sub     rsp, 28h
0x180003bed  xor     ebp, ebp
0x180003bef  mov     rbx, r9
0x180003bf2  mov     r10, rdx
0x180003bf5  mov     rdi, rcx
0x180003bf8  cmp     rcx, rdx
0x180003bfb  jz      short loc_180003C37
0x180003bfd  test    r8, r8
0x180003c00  jz      short loc_180003C37
0x180003c02  cmp     [r8], bp
0x180003c06  jz      short loc_180003C37
0x180003c08  mov     rcx, r8; this
0x180003c0b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003c10  sub     r10, rdi
0x180003c13  mov     rsi, rax
0x180003c16  cmp     r10, rax
0x180003c19  jb      short loc_180003C37
0x180003c1b  mov     r9, rax; SourceSize
0x180003c1e  mov     rdx, r10; DestinationSize
0x180003c21  mov     rcx, rdi; Destination
0x180003c24  call    memcpy_s
0x180003c29  test    rbx, rbx
0x180003c2c  jz      short loc_180003C31
0x180003c2e  mov     [rbx], rdi
0x180003c31  lea     rax, [rsi+rdi]
0x180003c35  jmp     short loc_180003C42
0x180003c37  test    rbx, rbx
0x180003c3a  jz      short loc_180003C3F
0x180003c3c  mov     [r9], rbp
0x180003c3f  mov     rax, rdi
0x180003c42  add     rsp, 28h
0x180003c46  pop     rdi
0x180003c47  pop     rsi
0x180003c48  pop     rbp
0x180003c49  pop     rbx
0x180003c4a  retn
```
