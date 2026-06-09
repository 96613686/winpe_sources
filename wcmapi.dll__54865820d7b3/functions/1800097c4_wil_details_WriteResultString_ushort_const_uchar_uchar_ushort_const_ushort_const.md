# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800097c4`
- end: `0x18000982c`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a3b4`
- `0x18000fde8`

## callees

- `0x1800097c4`
- `0x18000a2dc`
- `0x18000aaf4`

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
0x1800097c4  push    rbx
0x1800097c6  push    rbp
0x1800097c7  push    rsi
0x1800097c8  push    rdi
0x1800097c9  sub     rsp, 28h
0x1800097cd  xor     ebp, ebp
0x1800097cf  mov     rbx, r9
0x1800097d2  mov     r10, rdx
0x1800097d5  mov     rdi, rcx
0x1800097d8  cmp     rcx, rdx
0x1800097db  jz      short loc_180009817
0x1800097dd  test    r8, r8
0x1800097e0  jz      short loc_180009817
0x1800097e2  cmp     [r8], bp
0x1800097e6  jz      short loc_180009817
0x1800097e8  mov     rcx, r8; this
0x1800097eb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800097f0  sub     r10, rdi
0x1800097f3  mov     rsi, rax
0x1800097f6  cmp     r10, rax
0x1800097f9  jb      short loc_180009817
0x1800097fb  mov     r9, rax; SourceSize
0x1800097fe  mov     rdx, r10; DestinationSize
0x180009801  mov     rcx, rdi; Destination
0x180009804  call    memcpy_s
0x180009809  test    rbx, rbx
0x18000980c  jz      short loc_180009811
0x18000980e  mov     [rbx], rdi
0x180009811  lea     rax, [rsi+rdi]
0x180009815  jmp     short loc_180009822
0x180009817  test    rbx, rbx
0x18000981a  jz      short loc_18000981F
0x18000981c  mov     [r9], rbp
0x18000981f  mov     rax, rdi
0x180009822  add     rsp, 28h
0x180009826  pop     rdi
0x180009827  pop     rsi
0x180009828  pop     rbp
0x180009829  pop     rbx
0x18000982a  retn
```
