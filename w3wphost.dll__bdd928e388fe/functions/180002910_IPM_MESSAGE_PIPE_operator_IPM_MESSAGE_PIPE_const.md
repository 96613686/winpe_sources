# IPM_MESSAGE_PIPE::operator=(IPM_MESSAGE_PIPE const &)

- ea: `0x180002910`
- end: `0x18000296d`
- name: `??4IPM_MESSAGE_PIPE@@QEAAAEAV0@AEBV0@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??4CReaderWriterLock3@@QEAAAEAV0@AEBV0@@Z` at `0x180002928`
- `iisutil!??4CReaderWriterLock3@@QEAAAEAV0@AEBV0@@Z` at `0x180002928`

## pseudocode

```c
__int64 __fastcall IPM_MESSAGE_PIPE::operator=(__int64 a1, __int64 a2)
{
  CReaderWriterLock3::operator=(a1 + 8, a2 + 8);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(a1 + 24) = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 32);
  *(_DWORD *)(a1 + 36) = *(_DWORD *)(a2 + 36);
  *(_OWORD *)(a1 + 40) = *(_OWORD *)(a2 + 40);
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 56);
  *(_DWORD *)(a1 + 60) = *(_DWORD *)(a2 + 60);
  return a1;
}

```

## disassembly

```asm
0x180002910  mov     [rsp+arg_0], rbx
0x180002915  push    rdi
0x180002916  sub     rsp, 20h
0x18000291a  mov     rbx, rdx
0x18000291d  mov     rdi, rcx
0x180002920  add     rdx, 8
0x180002924  add     rcx, 8
0x180002928  call    cs:__imp_??4CReaderWriterLock3@@QEAAAEAV0@AEBV0@@Z; CReaderWriterLock3::operator=(CReaderWriterLock3 const &)
0x18000292e  mov     rax, [rbx+10h]
0x180002932  mov     [rdi+10h], rax
0x180002936  mov     rax, [rbx+18h]
0x18000293a  mov     [rdi+18h], rax
0x18000293e  mov     eax, [rbx+20h]
0x180002941  mov     [rdi+20h], eax
0x180002944  mov     eax, [rbx+24h]
0x180002947  mov     [rdi+24h], eax
0x18000294a  movups  xmm0, xmmword ptr [rbx+28h]
0x18000294e  movdqu  xmmword ptr [rdi+28h], xmm0
0x180002953  mov     eax, [rbx+38h]
0x180002956  mov     [rdi+38h], eax
0x180002959  mov     eax, [rbx+3Ch]
0x18000295c  mov     rbx, [rsp+28h+arg_0]
0x180002961  mov     [rdi+3Ch], eax
0x180002964  mov     rax, rdi
0x180002967  add     rsp, 20h
0x18000296b  pop     rdi
0x18000296c  retn
```
