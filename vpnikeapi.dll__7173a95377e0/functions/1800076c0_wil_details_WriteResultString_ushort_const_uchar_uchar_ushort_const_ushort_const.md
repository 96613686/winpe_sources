# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800076c0`
- end: `0x180007728`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae54`

## callees

- `0x1800076c0`
- `0x18000acf8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007700`
- `msvcrt!memcpy_s` at `0x180007700`

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
0x1800076c0  push    rbx
0x1800076c2  push    rbp
0x1800076c3  push    rsi
0x1800076c4  push    rdi
0x1800076c5  sub     rsp, 28h
0x1800076c9  xor     ebp, ebp
0x1800076cb  mov     rbx, r9
0x1800076ce  mov     r10, rdx
0x1800076d1  mov     rdi, rcx
0x1800076d4  cmp     rcx, rdx
0x1800076d7  jz      short loc_180007714
0x1800076d9  test    r8, r8
0x1800076dc  jz      short loc_180007714
0x1800076de  cmp     [r8], bp
0x1800076e2  jz      short loc_180007714
0x1800076e4  mov     rcx, r8; this
0x1800076e7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800076ec  sub     r10, rdi
0x1800076ef  mov     rsi, rax
0x1800076f2  cmp     r10, rax
0x1800076f5  jb      short loc_180007714
0x1800076f7  mov     r9, rax; SourceSize
0x1800076fa  mov     rdx, r10; DestinationSize
0x1800076fd  mov     rcx, rdi; Destination
0x180007700  call    cs:__imp_memcpy_s
0x180007706  test    rbx, rbx
0x180007709  jz      short loc_18000770E
0x18000770b  mov     [rbx], rdi
0x18000770e  lea     rax, [rsi+rdi]
0x180007712  jmp     short loc_18000771F
0x180007714  test    rbx, rbx
0x180007717  jz      short loc_18000771C
0x180007719  mov     [r9], rbp
0x18000771c  mov     rax, rdi
0x18000771f  add     rsp, 28h
0x180007723  pop     rdi
0x180007724  pop     rsi
0x180007725  pop     rbp
0x180007726  pop     rbx
0x180007727  retn
```
