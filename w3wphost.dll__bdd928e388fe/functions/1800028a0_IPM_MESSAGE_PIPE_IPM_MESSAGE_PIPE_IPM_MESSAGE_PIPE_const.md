# IPM_MESSAGE_PIPE::IPM_MESSAGE_PIPE(IPM_MESSAGE_PIPE const &)

- ea: `0x1800028a0`
- end: `0x180002907`
- name: `??0IPM_MESSAGE_PIPE@@QEAA@AEBV0@@Z`
- size: `103`
- prototype: `IPM_MESSAGE_PIPE *__fastcall(IPM_MESSAGE_PIPE *__hidden this, const struct IPM_MESSAGE_PIPE *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@AEBV0@@Z` at `0x1800028c2`
- `iisutil!??0CReaderWriterLock3@@QEAA@AEBV0@@Z` at `0x1800028c2`

## pseudocode

```c
IPM_MESSAGE_PIPE *__fastcall IPM_MESSAGE_PIPE::IPM_MESSAGE_PIPE(
        IPM_MESSAGE_PIPE *this,
        const struct IPM_MESSAGE_PIPE *a2)
{
  *(_QWORD *)this = &IPM_MESSAGE_PIPE::`vftable';
  CReaderWriterLock3::CReaderWriterLock3(
    (IPM_MESSAGE_PIPE *)((char *)this + 8),
    (const struct IPM_MESSAGE_PIPE *)((char *)a2 + 8));
  *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 3) = *((_QWORD *)a2 + 3);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  *((_DWORD *)this + 9) = *((_DWORD *)a2 + 9);
  *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)a2 + 40);
  *((_DWORD *)this + 14) = *((_DWORD *)a2 + 14);
  *((_DWORD *)this + 15) = *((_DWORD *)a2 + 15);
  return this;
}

```

## disassembly

```asm
0x1800028a0  mov     [rsp+arg_0], rbx
0x1800028a5  push    rdi
0x1800028a6  sub     rsp, 20h
0x1800028aa  lea     rax, ??_7IPM_MESSAGE_PIPE@@6B@; const IPM_MESSAGE_PIPE::`vftable'
0x1800028b1  mov     rbx, rdx
0x1800028b4  mov     [rcx], rax
0x1800028b7  mov     rdi, rcx
0x1800028ba  add     rcx, 8
0x1800028be  add     rdx, 8
0x1800028c2  call    cs:__imp_??0CReaderWriterLock3@@QEAA@AEBV0@@Z; CReaderWriterLock3::CReaderWriterLock3(CReaderWriterLock3 const &)
0x1800028c8  mov     rax, [rbx+10h]
0x1800028cc  mov     [rdi+10h], rax
0x1800028d0  mov     rax, [rbx+18h]
0x1800028d4  mov     [rdi+18h], rax
0x1800028d8  mov     eax, [rbx+20h]
0x1800028db  mov     [rdi+20h], eax
0x1800028de  mov     eax, [rbx+24h]
0x1800028e1  mov     [rdi+24h], eax
0x1800028e4  movups  xmm0, xmmword ptr [rbx+28h]
0x1800028e8  movdqu  xmmword ptr [rdi+28h], xmm0
0x1800028ed  mov     eax, [rbx+38h]
0x1800028f0  mov     [rdi+38h], eax
0x1800028f3  mov     eax, [rbx+3Ch]
0x1800028f6  mov     rbx, [rsp+28h+arg_0]
0x1800028fb  mov     [rdi+3Ch], eax
0x1800028fe  mov     rax, rdi
0x180002901  add     rsp, 20h
0x180002905  pop     rdi
0x180002906  retn
```
