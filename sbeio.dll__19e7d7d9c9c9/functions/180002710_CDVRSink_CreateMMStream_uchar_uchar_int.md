# CDVRSink::CreateMMStream(uchar,uchar,int)

- ea: `0x180002710`
- end: `0x180002771`
- name: `?CreateMMStream@CDVRSink@@MEAAPEAVCASFMMStream@@EEH@Z`
- size: `97`
- prototype: `struct CASFMMStream *(CDVRSink *__hidden this, unsigned __int8, unsigned __int8, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011a0`
- `0x180002710`
- `0x1800119f4`

## pseudocode

```c
struct CASFMMStream *__fastcall CDVRSink::CreateMMStream(
        CDVRSink *this,
        unsigned __int8 a2,
        unsigned __int8 a3,
        int a4)
{
  CASFMMStream *v7; // rax
  CASFMMStream *v8; // rbx

  v7 = (CASFMMStream *)operator new(0x568u);
  v8 = v7;
  if ( !v7 )
    return 0;
  CASFMMStream::CASFMMStream(v7, a2, a3, a4);
  *(_QWORD *)v8 = &CDVRASFMMStream::`vftable';
  *((_QWORD *)v8 + 171) = -1;
  *((_QWORD *)v8 + 172) = -1;
  return v8;
}

```

## disassembly

```asm
0x180002710  push    rbx
0x180002712  push    rbp
0x180002713  push    rsi
0x180002714  push    rdi
0x180002715  sub     rsp, 28h
0x180002719  mov     ecx, 568h; Size
0x18000271e  mov     edi, r9d
0x180002721  mov     sil, r8b
0x180002724  mov     bpl, dl
0x180002727  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000272c  mov     rbx, rax
0x18000272f  test    rax, rax
0x180002732  jz      short loc_180002763
0x180002734  mov     r9d, edi; int
0x180002737  mov     r8b, sil; unsigned __int8
0x18000273a  mov     dl, bpl; unsigned __int8
0x18000273d  mov     rcx, rax; this
0x180002740  call    ??0CASFMMStream@@QEAA@EEH@Z; CASFMMStream::CASFMMStream(uchar,uchar,int)
0x180002745  lea     rax, ??_7CDVRASFMMStream@@6B@; const CDVRASFMMStream::`vftable'
0x18000274c  mov     [rbx], rax
0x18000274f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002753  mov     [rbx+558h], rax
0x18000275a  mov     [rbx+560h], rax
0x180002761  jmp     short loc_180002765
0x180002763  xor     ebx, ebx
0x180002765  mov     rax, rbx
0x180002768  add     rsp, 28h
0x18000276c  pop     rdi
0x18000276d  pop     rsi
0x18000276e  pop     rbp
0x18000276f  pop     rbx
0x180002770  retn
```
