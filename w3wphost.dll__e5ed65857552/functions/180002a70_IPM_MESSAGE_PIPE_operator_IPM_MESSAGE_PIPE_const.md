# IPM_MESSAGE_PIPE::operator=(IPM_MESSAGE_PIPE const &)

- ea: `0x180002a70`
- end: `0x180002ad4`
- name: `??4IPM_MESSAGE_PIPE@@QEAAAEAV0@AEBV0@@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??4CReaderWriterLock3@@QEAAAEAV0@AEBV0@@Z` at `0x180002a88`
- `iisutil!??4CReaderWriterLock3@@QEAAAEAV0@AEBV0@@Z` at `0x180002a88`

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
0x180002a70  mov     [rsp+arg_0], rbx
0x180002a75  push    rdi
0x180002a76  sub     rsp, 20h
0x180002a7a  mov     rbx, rdx
0x180002a7d  mov     rdi, rcx
0x180002a80  add     rdx, 8
0x180002a84  add     rcx, 8
0x180002a88  call    cs:__imp_??4CReaderWriterLock3@@QEAAAEAV0@AEBV0@@Z; CReaderWriterLock3::operator=(CReaderWriterLock3 const &)
0x180002a8f  nop     dword ptr [rax+rax+00h]
0x180002a94  mov     rax, [rbx+10h]
0x180002a98  mov     [rdi+10h], rax
0x180002a9c  mov     rax, [rbx+18h]
0x180002aa0  mov     [rdi+18h], rax
0x180002aa4  mov     eax, [rbx+20h]
0x180002aa7  mov     [rdi+20h], eax
0x180002aaa  mov     eax, [rbx+24h]
0x180002aad  mov     [rdi+24h], eax
0x180002ab0  movups  xmm0, xmmword ptr [rbx+28h]
0x180002ab4  movdqu  xmmword ptr [rdi+28h], xmm0
0x180002ab9  mov     eax, [rbx+38h]
0x180002abc  mov     [rdi+38h], eax
0x180002abf  mov     eax, [rbx+3Ch]
0x180002ac2  mov     rbx, [rsp+28h+arg_0]
0x180002ac7  mov     [rdi+3Ch], eax
0x180002aca  mov     rax, rdi
0x180002acd  add     rsp, 20h
0x180002ad1  pop     rdi
0x180002ad2  retn
```
