# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180004a5c`
- end: `0x180004ac4`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054bc`
- `0x180016364`

## callees

- `0x180004a5c`
- `0x180005434`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004a9c`
- `msvcrt!memcpy_s` at `0x180004a9c`

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
0x180004a5c  push    rbx
0x180004a5e  push    rbp
0x180004a5f  push    rsi
0x180004a60  push    rdi
0x180004a61  sub     rsp, 28h
0x180004a65  xor     ebp, ebp
0x180004a67  mov     rbx, r9
0x180004a6a  mov     r10, rdx
0x180004a6d  mov     rdi, rcx
0x180004a70  cmp     rcx, rdx
0x180004a73  jz      short loc_180004AB0
0x180004a75  test    r8, r8
0x180004a78  jz      short loc_180004AB0
0x180004a7a  cmp     [r8], bp
0x180004a7e  jz      short loc_180004AB0
0x180004a80  mov     rcx, r8; this
0x180004a83  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004a88  sub     r10, rdi
0x180004a8b  mov     rsi, rax
0x180004a8e  cmp     r10, rax
0x180004a91  jb      short loc_180004AB0
0x180004a93  mov     r9, rax; SourceSize
0x180004a96  mov     rdx, r10; DestinationSize
0x180004a99  mov     rcx, rdi; Destination
0x180004a9c  call    cs:__imp_memcpy_s
0x180004aa2  test    rbx, rbx
0x180004aa5  jz      short loc_180004AAA
0x180004aa7  mov     [rbx], rdi
0x180004aaa  lea     rax, [rsi+rdi]
0x180004aae  jmp     short loc_180004ABB
0x180004ab0  test    rbx, rbx
0x180004ab3  jz      short loc_180004AB8
0x180004ab5  mov     [r9], rbp
0x180004ab8  mov     rax, rdi
0x180004abb  add     rsp, 28h
0x180004abf  pop     rdi
0x180004ac0  pop     rsi
0x180004ac1  pop     rbp
0x180004ac2  pop     rbx
0x180004ac3  retn
```
