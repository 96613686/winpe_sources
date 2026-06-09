# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800073a0`
- end: `0x180007407`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800090fc`
- `0x180009238`

## callees

- `0x1800073a0`
- `0x180009038`
- `0x180009dfc`

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
0x1800073a0  push    rbx
0x1800073a2  push    rbp
0x1800073a3  push    rsi
0x1800073a4  push    rdi
0x1800073a5  sub     rsp, 28h
0x1800073a9  xor     ebp, ebp
0x1800073ab  mov     rbx, r9
0x1800073ae  mov     r10, rdx
0x1800073b1  mov     rdi, rcx
0x1800073b4  cmp     rcx, rdx
0x1800073b7  jz      short loc_1800073F3
0x1800073b9  test    r8, r8
0x1800073bc  jz      short loc_1800073F3
0x1800073be  cmp     [r8], bp
0x1800073c2  jz      short loc_1800073F3
0x1800073c4  mov     rcx, r8; this
0x1800073c7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800073cc  sub     r10, rdi
0x1800073cf  mov     rsi, rax
0x1800073d2  cmp     r10, rax
0x1800073d5  jb      short loc_1800073F3
0x1800073d7  mov     r9, rax; SourceSize
0x1800073da  mov     rdx, r10; DestinationSize
0x1800073dd  mov     rcx, rdi; Destination
0x1800073e0  call    memcpy_s
0x1800073e5  test    rbx, rbx
0x1800073e8  jz      short loc_1800073ED
0x1800073ea  mov     [rbx], rdi
0x1800073ed  lea     rax, [rsi+rdi]
0x1800073f1  jmp     short loc_1800073FE
0x1800073f3  test    rbx, rbx
0x1800073f6  jz      short loc_1800073FB
0x1800073f8  mov     [r9], rbp
0x1800073fb  mov     rax, rdi
0x1800073fe  add     rsp, 28h
0x180007402  pop     rdi
0x180007403  pop     rsi
0x180007404  pop     rbp
0x180007405  pop     rbx
0x180007406  retn
```
