# IPM_MESSAGE_PIPE::IPM_MESSAGE_PIPE(IPM_MESSAGE_PIPE const &)

- ea: `0x1800029f0`
- end: `0x180002a5e`
- name: `??0IPM_MESSAGE_PIPE@@QEAA@AEBV0@@Z`
- size: `110`
- prototype: `IPM_MESSAGE_PIPE *__fastcall(IPM_MESSAGE_PIPE *__hidden this, const struct IPM_MESSAGE_PIPE *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@AEBV0@@Z` at `0x180002a12`
- `iisutil!??0CReaderWriterLock3@@QEAA@AEBV0@@Z` at `0x180002a12`

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
0x1800029f0  mov     [rsp+arg_0], rbx
0x1800029f5  push    rdi
0x1800029f6  sub     rsp, 20h
0x1800029fa  lea     rax, ??_7IPM_MESSAGE_PIPE@@6B@; const IPM_MESSAGE_PIPE::`vftable'
0x180002a01  mov     rbx, rdx
0x180002a04  mov     [rcx], rax
0x180002a07  mov     rdi, rcx
0x180002a0a  add     rcx, 8
0x180002a0e  add     rdx, 8
0x180002a12  call    cs:__imp_??0CReaderWriterLock3@@QEAA@AEBV0@@Z; CReaderWriterLock3::CReaderWriterLock3(CReaderWriterLock3 const &)
0x180002a19  nop     dword ptr [rax+rax+00h]
0x180002a1e  mov     rax, [rbx+10h]
0x180002a22  mov     [rdi+10h], rax
0x180002a26  mov     rax, [rbx+18h]
0x180002a2a  mov     [rdi+18h], rax
0x180002a2e  mov     eax, [rbx+20h]
0x180002a31  mov     [rdi+20h], eax
0x180002a34  mov     eax, [rbx+24h]
0x180002a37  mov     [rdi+24h], eax
0x180002a3a  movups  xmm0, xmmword ptr [rbx+28h]
0x180002a3e  movdqu  xmmword ptr [rdi+28h], xmm0
0x180002a43  mov     eax, [rbx+38h]
0x180002a46  mov     [rdi+38h], eax
0x180002a49  mov     eax, [rbx+3Ch]
0x180002a4c  mov     rbx, [rsp+28h+arg_0]
0x180002a51  mov     [rdi+3Ch], eax
0x180002a54  mov     rax, rdi
0x180002a57  add     rsp, 20h
0x180002a5b  pop     rdi
0x180002a5c  retn
```
