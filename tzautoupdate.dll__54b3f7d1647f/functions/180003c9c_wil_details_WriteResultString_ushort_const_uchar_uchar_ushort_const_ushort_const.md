# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003c9c`
- end: `0x180003d04`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008954`
- `0x180008b80`

## callees

- `0x180003c9c`
- `0x180008790`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003cdc`
- `msvcrt!memcpy_s` at `0x180003cdc`

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
0x180003c9c  push    rbx
0x180003c9e  push    rbp
0x180003c9f  push    rsi
0x180003ca0  push    rdi
0x180003ca1  sub     rsp, 28h
0x180003ca5  xor     ebp, ebp
0x180003ca7  mov     rbx, r9
0x180003caa  mov     r10, rdx
0x180003cad  mov     rdi, rcx
0x180003cb0  cmp     rcx, rdx
0x180003cb3  jz      short loc_180003CF0
0x180003cb5  test    r8, r8
0x180003cb8  jz      short loc_180003CF0
0x180003cba  cmp     [r8], bp
0x180003cbe  jz      short loc_180003CF0
0x180003cc0  mov     rcx, r8; this
0x180003cc3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003cc8  sub     r10, rdi
0x180003ccb  mov     rsi, rax
0x180003cce  cmp     r10, rax
0x180003cd1  jb      short loc_180003CF0
0x180003cd3  mov     r9, rax; SourceSize
0x180003cd6  mov     rdx, r10; DestinationSize
0x180003cd9  mov     rcx, rdi; Destination
0x180003cdc  call    cs:__imp_memcpy_s
0x180003ce2  test    rbx, rbx
0x180003ce5  jz      short loc_180003CEA
0x180003ce7  mov     [rbx], rdi
0x180003cea  lea     rax, [rsi+rdi]
0x180003cee  jmp     short loc_180003CFB
0x180003cf0  test    rbx, rbx
0x180003cf3  jz      short loc_180003CF8
0x180003cf5  mov     [r9], rbp
0x180003cf8  mov     rax, rdi
0x180003cfb  add     rsp, 28h
0x180003cff  pop     rdi
0x180003d00  pop     rsi
0x180003d01  pop     rbp
0x180003d02  pop     rbx
0x180003d03  retn
```
