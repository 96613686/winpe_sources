# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180004fec`
- end: `0x180005053`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800086d4`
- `0x180008810`

## callees

- `0x180004fec`
- `0x1800085b0`
- `0x180009b1c`

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
0x180004fec  push    rbx
0x180004fee  push    rbp
0x180004fef  push    rsi
0x180004ff0  push    rdi
0x180004ff1  sub     rsp, 28h
0x180004ff5  xor     ebp, ebp
0x180004ff7  mov     rbx, r9
0x180004ffa  mov     r10, rdx
0x180004ffd  mov     rdi, rcx
0x180005000  cmp     rcx, rdx
0x180005003  jz      short loc_18000503F
0x180005005  test    r8, r8
0x180005008  jz      short loc_18000503F
0x18000500a  cmp     [r8], bp
0x18000500e  jz      short loc_18000503F
0x180005010  mov     rcx, r8; this
0x180005013  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180005018  sub     r10, rdi
0x18000501b  mov     rsi, rax
0x18000501e  cmp     r10, rax
0x180005021  jb      short loc_18000503F
0x180005023  mov     r9, rax; SourceSize
0x180005026  mov     rdx, r10; DestinationSize
0x180005029  mov     rcx, rdi; Destination
0x18000502c  call    memcpy_s
0x180005031  test    rbx, rbx
0x180005034  jz      short loc_180005039
0x180005036  mov     [rbx], rdi
0x180005039  lea     rax, [rsi+rdi]
0x18000503d  jmp     short loc_18000504A
0x18000503f  test    rbx, rbx
0x180005042  jz      short loc_180005047
0x180005044  mov     [r9], rbp
0x180005047  mov     rax, rdi
0x18000504a  add     rsp, 28h
0x18000504e  pop     rdi
0x18000504f  pop     rsi
0x180005050  pop     rbp
0x180005051  pop     rbx
0x180005052  retn
```
