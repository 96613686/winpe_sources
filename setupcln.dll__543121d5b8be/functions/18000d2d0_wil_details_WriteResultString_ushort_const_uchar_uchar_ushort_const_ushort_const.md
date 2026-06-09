# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000d2d0`
- end: `0x18000d338`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d80`
- `0x180010fac`

## callees

- `0x18000d2d0`
- `0x180010c18`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d310`
- `msvcrt!memcpy_s` at `0x18000d310`

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
0x18000d2d0  push    rbx
0x18000d2d2  push    rbp
0x18000d2d3  push    rsi
0x18000d2d4  push    rdi
0x18000d2d5  sub     rsp, 28h
0x18000d2d9  xor     ebp, ebp
0x18000d2db  mov     rbx, r9
0x18000d2de  mov     r10, rdx
0x18000d2e1  mov     rdi, rcx
0x18000d2e4  cmp     rcx, rdx
0x18000d2e7  jz      short loc_18000D324
0x18000d2e9  test    r8, r8
0x18000d2ec  jz      short loc_18000D324
0x18000d2ee  cmp     [r8], bp
0x18000d2f2  jz      short loc_18000D324
0x18000d2f4  mov     rcx, r8; this
0x18000d2f7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000d2fc  sub     r10, rdi
0x18000d2ff  mov     rsi, rax
0x18000d302  cmp     r10, rax
0x18000d305  jb      short loc_18000D324
0x18000d307  mov     r9, rax; SourceSize
0x18000d30a  mov     rdx, r10; DestinationSize
0x18000d30d  mov     rcx, rdi; Destination
0x18000d310  call    cs:__imp_memcpy_s
0x18000d316  test    rbx, rbx
0x18000d319  jz      short loc_18000D31E
0x18000d31b  mov     [rbx], rdi
0x18000d31e  lea     rax, [rsi+rdi]
0x18000d322  jmp     short loc_18000D32F
0x18000d324  test    rbx, rbx
0x18000d327  jz      short loc_18000D32C
0x18000d329  mov     [r9], rbp
0x18000d32c  mov     rax, rdi
0x18000d32f  add     rsp, 28h
0x18000d333  pop     rdi
0x18000d334  pop     rsi
0x18000d335  pop     rbp
0x18000d336  pop     rbx
0x18000d337  retn
```
