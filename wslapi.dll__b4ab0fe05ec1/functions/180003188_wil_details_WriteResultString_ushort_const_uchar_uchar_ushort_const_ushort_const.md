# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003188`
- end: `0x1800031ef`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000503c`
- `0x180005178`

## callees

- `0x180003188`
- `0x180004f78`
- `0x180005d30`

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
0x180003188  push    rbx
0x18000318a  push    rbp
0x18000318b  push    rsi
0x18000318c  push    rdi
0x18000318d  sub     rsp, 28h
0x180003191  xor     ebp, ebp
0x180003193  mov     rbx, r9
0x180003196  mov     r10, rdx
0x180003199  mov     rdi, rcx
0x18000319c  cmp     rcx, rdx
0x18000319f  jz      short loc_1800031DB
0x1800031a1  test    r8, r8
0x1800031a4  jz      short loc_1800031DB
0x1800031a6  cmp     [r8], bp
0x1800031aa  jz      short loc_1800031DB
0x1800031ac  mov     rcx, r8; this
0x1800031af  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800031b4  sub     r10, rdi
0x1800031b7  mov     rsi, rax
0x1800031ba  cmp     r10, rax
0x1800031bd  jb      short loc_1800031DB
0x1800031bf  mov     r9, rax; SourceSize
0x1800031c2  mov     rdx, r10; DestinationSize
0x1800031c5  mov     rcx, rdi; Destination
0x1800031c8  call    memcpy_s
0x1800031cd  test    rbx, rbx
0x1800031d0  jz      short loc_1800031D5
0x1800031d2  mov     [rbx], rdi
0x1800031d5  lea     rax, [rsi+rdi]
0x1800031d9  jmp     short loc_1800031E6
0x1800031db  test    rbx, rbx
0x1800031de  jz      short loc_1800031E3
0x1800031e0  mov     [r9], rbp
0x1800031e3  mov     rax, rdi
0x1800031e6  add     rsp, 28h
0x1800031ea  pop     rdi
0x1800031eb  pop     rsi
0x1800031ec  pop     rbp
0x1800031ed  pop     rbx
0x1800031ee  retn
```
