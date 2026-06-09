# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180013788`
- end: `0x1800137ef`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015afc`
- `0x180015c38`

## callees

- `0x180013788`
- `0x180015a38`
- `0x180016a74`

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
0x180013788  push    rbx
0x18001378a  push    rbp
0x18001378b  push    rsi
0x18001378c  push    rdi
0x18001378d  sub     rsp, 28h
0x180013791  xor     ebp, ebp
0x180013793  mov     rbx, r9
0x180013796  mov     r10, rdx
0x180013799  mov     rdi, rcx
0x18001379c  cmp     rcx, rdx
0x18001379f  jz      short loc_1800137DB
0x1800137a1  test    r8, r8
0x1800137a4  jz      short loc_1800137DB
0x1800137a6  cmp     [r8], bp
0x1800137aa  jz      short loc_1800137DB
0x1800137ac  mov     rcx, r8; this
0x1800137af  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800137b4  sub     r10, rdi
0x1800137b7  mov     rsi, rax
0x1800137ba  cmp     r10, rax
0x1800137bd  jb      short loc_1800137DB
0x1800137bf  mov     r9, rax; SourceSize
0x1800137c2  mov     rdx, r10; DestinationSize
0x1800137c5  mov     rcx, rdi; Destination
0x1800137c8  call    memcpy_s
0x1800137cd  test    rbx, rbx
0x1800137d0  jz      short loc_1800137D5
0x1800137d2  mov     [rbx], rdi
0x1800137d5  lea     rax, [rsi+rdi]
0x1800137d9  jmp     short loc_1800137E6
0x1800137db  test    rbx, rbx
0x1800137de  jz      short loc_1800137E3
0x1800137e0  mov     [r9], rbp
0x1800137e3  mov     rax, rdi
0x1800137e6  add     rsp, 28h
0x1800137ea  pop     rdi
0x1800137eb  pop     rsi
0x1800137ec  pop     rbp
0x1800137ed  pop     rbx
0x1800137ee  retn
```
