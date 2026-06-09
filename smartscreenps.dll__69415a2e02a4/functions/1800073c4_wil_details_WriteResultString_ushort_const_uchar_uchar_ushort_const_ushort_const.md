# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800073c4`
- end: `0x18000742c`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000926c`
- `0x1800093b8`

## callees

- `0x1800073c4`
- `0x18000919c`
- `0x18000a028`

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
0x1800073c4  push    rbx
0x1800073c6  push    rbp
0x1800073c7  push    rsi
0x1800073c8  push    rdi
0x1800073c9  sub     rsp, 28h
0x1800073cd  xor     ebp, ebp
0x1800073cf  mov     rbx, r9
0x1800073d2  mov     r10, rdx
0x1800073d5  mov     rdi, rcx
0x1800073d8  cmp     rcx, rdx
0x1800073db  jz      short loc_180007417
0x1800073dd  test    r8, r8
0x1800073e0  jz      short loc_180007417
0x1800073e2  cmp     [r8], bp
0x1800073e6  jz      short loc_180007417
0x1800073e8  mov     rcx, r8; this
0x1800073eb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800073f0  sub     r10, rdi
0x1800073f3  mov     rsi, rax
0x1800073f6  cmp     r10, rax
0x1800073f9  jb      short loc_180007417
0x1800073fb  mov     r9, rax; SourceSize
0x1800073fe  mov     rdx, r10; DestinationSize
0x180007401  mov     rcx, rdi; Destination
0x180007404  call    memcpy_s
0x180007409  test    rbx, rbx
0x18000740c  jz      short loc_180007411
0x18000740e  mov     [rbx], rdi
0x180007411  lea     rax, [rsi+rdi]
0x180007415  jmp     short loc_180007422
0x180007417  test    rbx, rbx
0x18000741a  jz      short loc_18000741F
0x18000741c  mov     [r9], rbp
0x18000741f  mov     rax, rdi
0x180007422  add     rsp, 28h
0x180007426  pop     rdi
0x180007427  pop     rsi
0x180007428  pop     rbp
0x180007429  pop     rbx
0x18000742a  retn
```
