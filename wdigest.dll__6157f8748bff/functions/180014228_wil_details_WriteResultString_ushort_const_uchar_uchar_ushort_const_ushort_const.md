# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180014228`
- end: `0x18001428f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016198`
- `0x180033cc4`

## callees

- `0x18000f770`
- `0x180014228`
- `0x180016078`

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
0x180014228  push    rbx
0x18001422a  push    rbp
0x18001422b  push    rsi
0x18001422c  push    rdi
0x18001422d  sub     rsp, 28h
0x180014231  xor     ebp, ebp
0x180014233  mov     rbx, r9
0x180014236  mov     r10, rdx
0x180014239  mov     rdi, rcx
0x18001423c  cmp     rcx, rdx
0x18001423f  jz      short loc_18001427B
0x180014241  test    r8, r8
0x180014244  jz      short loc_18001427B
0x180014246  cmp     [r8], bp
0x18001424a  jz      short loc_18001427B
0x18001424c  mov     rcx, r8; this
0x18001424f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180014254  sub     r10, rdi
0x180014257  mov     rsi, rax
0x18001425a  cmp     r10, rax
0x18001425d  jb      short loc_18001427B
0x18001425f  mov     r9, rax; SourceSize
0x180014262  mov     rdx, r10; DestinationSize
0x180014265  mov     rcx, rdi; Destination
0x180014268  call    memcpy_s
0x18001426d  test    rbx, rbx
0x180014270  jz      short loc_180014275
0x180014272  mov     [rbx], rdi
0x180014275  lea     rax, [rsi+rdi]
0x180014279  jmp     short loc_180014286
0x18001427b  test    rbx, rbx
0x18001427e  jz      short loc_180014283
0x180014280  mov     [r9], rbp
0x180014283  mov     rax, rdi
0x180014286  add     rsp, 28h
0x18001428a  pop     rdi
0x18001428b  pop     rsi
0x18001428c  pop     rbp
0x18001428d  pop     rbx
0x18001428e  retn
```
