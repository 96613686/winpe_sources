# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800033e8`
- end: `0x18000344f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000521c`
- `0x180005358`

## callees

- `0x1800033e8`
- `0x180005158`
- `0x180005f70`

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
0x1800033e8  push    rbx
0x1800033ea  push    rbp
0x1800033eb  push    rsi
0x1800033ec  push    rdi
0x1800033ed  sub     rsp, 28h
0x1800033f1  xor     ebp, ebp
0x1800033f3  mov     rbx, r9
0x1800033f6  mov     r10, rdx
0x1800033f9  mov     rdi, rcx
0x1800033fc  cmp     rcx, rdx
0x1800033ff  jz      short loc_18000343B
0x180003401  test    r8, r8
0x180003404  jz      short loc_18000343B
0x180003406  cmp     [r8], bp
0x18000340a  jz      short loc_18000343B
0x18000340c  mov     rcx, r8; this
0x18000340f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003414  sub     r10, rdi
0x180003417  mov     rsi, rax
0x18000341a  cmp     r10, rax
0x18000341d  jb      short loc_18000343B
0x18000341f  mov     r9, rax; SourceSize
0x180003422  mov     rdx, r10; DestinationSize
0x180003425  mov     rcx, rdi; Destination
0x180003428  call    memcpy_s
0x18000342d  test    rbx, rbx
0x180003430  jz      short loc_180003435
0x180003432  mov     [rbx], rdi
0x180003435  lea     rax, [rsi+rdi]
0x180003439  jmp     short loc_180003446
0x18000343b  test    rbx, rbx
0x18000343e  jz      short loc_180003443
0x180003440  mov     [r9], rbp
0x180003443  mov     rax, rdi
0x180003446  add     rsp, 28h
0x18000344a  pop     rdi
0x18000344b  pop     rsi
0x18000344c  pop     rbp
0x18000344d  pop     rbx
0x18000344e  retn
```
