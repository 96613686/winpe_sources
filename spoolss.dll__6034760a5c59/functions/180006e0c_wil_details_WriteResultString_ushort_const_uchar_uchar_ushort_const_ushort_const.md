# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180006e0c`
- end: `0x180006e73`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a8e0`
- `0x18000aa1c`

## callees

- `0x180006e0c`
- `0x18000a2ec`
- `0x18000f1d8`

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
0x180006e0c  push    rbx
0x180006e0e  push    rbp
0x180006e0f  push    rsi
0x180006e10  push    rdi
0x180006e11  sub     rsp, 28h
0x180006e15  xor     ebp, ebp
0x180006e17  mov     rbx, r9
0x180006e1a  mov     r10, rdx
0x180006e1d  mov     rdi, rcx
0x180006e20  cmp     rcx, rdx
0x180006e23  jz      short loc_180006E5F
0x180006e25  test    r8, r8
0x180006e28  jz      short loc_180006E5F
0x180006e2a  cmp     [r8], bp
0x180006e2e  jz      short loc_180006E5F
0x180006e30  mov     rcx, r8; this
0x180006e33  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006e38  sub     r10, rdi
0x180006e3b  mov     rsi, rax
0x180006e3e  cmp     r10, rax
0x180006e41  jb      short loc_180006E5F
0x180006e43  mov     r9, rax; SourceSize
0x180006e46  mov     rdx, r10; DestinationSize
0x180006e49  mov     rcx, rdi; Destination
0x180006e4c  call    memcpy_s
0x180006e51  test    rbx, rbx
0x180006e54  jz      short loc_180006E59
0x180006e56  mov     [rbx], rdi
0x180006e59  lea     rax, [rsi+rdi]
0x180006e5d  jmp     short loc_180006E6A
0x180006e5f  test    rbx, rbx
0x180006e62  jz      short loc_180006E67
0x180006e64  mov     [r9], rbp
0x180006e67  mov     rax, rdi
0x180006e6a  add     rsp, 28h
0x180006e6e  pop     rdi
0x180006e6f  pop     rsi
0x180006e70  pop     rbp
0x180006e71  pop     rbx
0x180006e72  retn
```
