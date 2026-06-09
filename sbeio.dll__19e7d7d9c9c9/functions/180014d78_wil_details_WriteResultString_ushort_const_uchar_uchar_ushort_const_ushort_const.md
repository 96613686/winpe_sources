# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180014d78`
- end: `0x180014ddf`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800244ac`

## callees

- `0x180014d78`
- `0x180024404`
- `0x180027394`

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
0x180014d78  push    rbx
0x180014d7a  push    rbp
0x180014d7b  push    rsi
0x180014d7c  push    rdi
0x180014d7d  sub     rsp, 28h
0x180014d81  xor     ebp, ebp
0x180014d83  mov     rbx, r9
0x180014d86  mov     r10, rdx
0x180014d89  mov     rdi, rcx
0x180014d8c  cmp     rcx, rdx
0x180014d8f  jz      short loc_180014DCB
0x180014d91  test    r8, r8
0x180014d94  jz      short loc_180014DCB
0x180014d96  cmp     [r8], bp
0x180014d9a  jz      short loc_180014DCB
0x180014d9c  mov     rcx, r8; this
0x180014d9f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180014da4  sub     r10, rdi
0x180014da7  mov     rsi, rax
0x180014daa  cmp     r10, rax
0x180014dad  jb      short loc_180014DCB
0x180014daf  mov     r9, rax; SourceSize
0x180014db2  mov     rdx, r10; DestinationSize
0x180014db5  mov     rcx, rdi; Destination
0x180014db8  call    memcpy_s
0x180014dbd  test    rbx, rbx
0x180014dc0  jz      short loc_180014DC5
0x180014dc2  mov     [rbx], rdi
0x180014dc5  lea     rax, [rsi+rdi]
0x180014dc9  jmp     short loc_180014DD6
0x180014dcb  test    rbx, rbx
0x180014dce  jz      short loc_180014DD3
0x180014dd0  mov     [r9], rbp
0x180014dd3  mov     rax, rdi
0x180014dd6  add     rsp, 28h
0x180014dda  pop     rdi
0x180014ddb  pop     rsi
0x180014ddc  pop     rbp
0x180014ddd  pop     rbx
0x180014dde  retn
```
